# TP 1 : Surveillance Maritime dans le Cloud avec Google BigQuery Sandbox

**Durée :** 3h30 (Jour 1 - Après-midi)  
**Modalité :** En binôme ou individuel  
**Outil :** Google BigQuery Sandbox (100% gratuit, dans le navigateur, **sans carte bancaire**)  
**Données :** [`donnees_maritimes_ais_sample.csv`](../donnees/donnees_maritimes_ais_sample.csv)

---

## 🎯 Objectifs Pédagogiques

1. Découvrir la console d'un grand fournisseur Cloud sans aucune appréhension technique.
2. Comprendre le concept de **Data Warehouse Serverless** (zéro serveur à allumer, calcul instantané).
3. Écrire et exécuter ses premières requêtes SQL simples pour répondre à des questions opérationnelles.
4. Constater en direct le mécanisme de facturation du Cloud (l'estimateur d'octets scannés).

---

## 🚀 Étape 1 : Accéder à BigQuery Sandbox (10 minutes)

> [!NOTE]
> **Pourquoi le mode "Sandbox" ?**  
> Google propose un accès gratuit à BigQuery sans jamais demander de numéro de carte bleue. Vous disposez de **10 Go de stockage** et de **1 Teraoctet de requêtes gratuites par mois**.

1. Ouvrez votre navigateur web et rendez-vous sur : [https://console.cloud.google.com/bigquery](https://console.cloud.google.com/bigquery)
2. Connectez-vous avec votre compte Google standard (personnel ou étudiant).
3. Si vous n'avez pas encore de projet, cliquez sur le menu déroulant en haut à gauche et cliquez sur **"Nouveau projet"**.
   - Nom du projet : `marine-data-m2` (ou le nom de votre choix).
   - Cliquez sur **Créer**.
4. Vous arrivez sur l'interface BigQuery avec un bandeau discret indiquant : *"Vous utilisez la version Sandbox de BigQuery"*. Tout est prêt !

---

## 📥 Étape 2 : Importer le jeu de données maritime (15 minutes)

Nous allons créer notre table de données en 4 clics :

1. Dans le volet de gauche nommé **"Explorateur"**, repérez votre projet.
2. Cliquez sur les **3 petits points verticaux** à côté du nom de votre projet, puis cliquez sur **"Créer un ensemble de données" (Dataset)**.
   - **ID de l'ensemble de données** : tapez `marine_nationale`
   - **Emplacement des données** : choisissez `europe-west9 (Paris)` ou `EU (plusieurs régions dans l'Union européenne)` *(Rappelez aux étudiants l'enjeu RGPD et de localisation des données !)*.
   - Cliquez sur **Créer l'ensemble de données**.
3. Cliquez maintenant sur les 3 petits points à côté de `marine_nationale`, puis sur **"Créer une table"**.
   - **Créer une table à partir de** : sélectionnez **Importer** (Upload).
   - **Sélectionner un fichier** : choisissez le fichier `donnees_maritimes_ais_sample.csv`.
   - **Nom de la table** : tapez `positions_ais`
   - **Schéma** : cochez la case **"Détecter automatiquement" (Auto-detect)**. *(BigQuery analyse lui-même les colonnes de texte, nombres et dates).*
   - Cliquez sur **Créer la table**.

En moins de 10 secondes, votre table apparaît dans l'arborescence ! Cliquez dessus, puis sur l'onglet **"Aperçu"** pour voir les navires.

---

## 🔎 Étape 3 : Vos premières requêtes de surveillance maritime

Cliquez sur l'onglet **+ (Saisir une nouvelle requête)** au centre de l'écran.

### Observation FinOps importante :
Regardez en haut à droite de l'éditeur de texte. Dès que vous tapez du code, BigQuery affiche un petit indicateur vert :  
`Cette requête traitera XX Ko une fois exécutée.`  
C'est le principe du **FinOps** : vous savez exactement combien de données vous consommez avant même de dépenser un centime !

---

### Exercice 1 : La vue générale de la flotte
*Question opérationnelle : "Combien de messages avons-nous reçus et combien de navires distincts patrouillent actuellement ?"*

Copiez-collez cette requête et cliquez sur **Exécuter** :

```sql
SELECT 
    COUNT(*) AS total_messages_recus,
    COUNT(DISTINCT nom_navire) AS nombre_navires_uniques,
    COUNT(DISTINCT pavillon) AS nombre_pays_representes
FROM 
    `marine_nationale.positions_ais`;
```

> **À commenter avec les étudiants :**  
> Observez le temps d'exécution (souvent moins de 0.5 seconde). Dans le Cloud, que vous ayez 1 500 lignes ou 15 millions de lignes, le temps de réponse reste quasi instantané grâce aux milliers de processeurs mutualisés.

---

### Exercice 2 : Identification des navires les plus rapides
*Question opérationnelle : "Quels sont les 10 navires qui se déplacent le plus vite dans notre zone d'intérêt maritime ?"*

```sql
SELECT 
    nom_navire,
    type_navire,
    pavillon,
    zone_maritime,
    vitesse_noeuds
FROM 
    `marine_nationale.positions_ais`
ORDER BY 
    vitesse_noeuds DESC
LIMIT 10;
```

> **Question de réflexion pour les étudiants :**  
> Quels types de bateaux retrouve-t-on en tête de liste ? Est-ce normal qu'un patrouilleur militaire ou un ferry à passagers navigue à plus de 20 nœuds ? Serait-ce normal pour un cargo lourdement chargé ?

---

### Exercice 3 : Répartition de la flotte par type de bâtiment
*Question opérationnelle : "Quel est le volume de cargos par rapport aux pétroliers et aux navires militaires ?"*

```sql
SELECT 
    type_navire,
    COUNT(*) AS nombre_detections,
    ROUND(AVG(vitesse_noeuds), 1) AS vitesse_moyenne_noeuds,
    ROUND(AVG(longueur_metres), 0) AS longueur_moyenne_metres
FROM 
    `marine_nationale.positions_ais`
GROUP BY 
    type_navire
ORDER BY 
    nombre_detections DESC;
```

> **Notion clé abordée :** Le `GROUP BY`. C'est l'équivalent direct du Tableau Croisé Dynamique d'Excel, mais calculé à l'échelle du Teraoctet en quelques millisecondes.

---

### Exercice 4 : Détection d'anomalies de sécurité (Renseignement tactique)
*Question opérationnelle : "Le Centre d'Opérations Maritimes (COM) demande la liste immédiate de tous les navires suspects présentant une alerte."*

```sql
SELECT 
    timestamp,
    nom_navire,
    type_navire,
    pavillon,
    zone_maritime,
    vitesse_noeuds,
    type_anomalie
FROM 
    `marine_nationale.positions_ais`
WHERE 
    alerte_anomalie = 1
ORDER BY 
    timestamp DESC;
```

> **Travail d'analyse par les étudiants :**  
> 1. Quelles anomalies apparaissent ?  
> 2. Pourquoi un navire étranger à vitesse quasi-nulle dans la rade de Toulon ou à l'approche de Brest doit-il attirer l'attention de la Marine ?  
> 3. Quelle action opérationnelle recommanderiez-vous (envoi d'un sémaphore, patrouille d'un hélicoptère Panther ou d'un patrouilleur hauturier) ?

---

### Exercice 5 (Bonus Découverte) : Interroger des téraoctets de données publiques
Google BigQuery héberge des milliers de jeux de données publics mondiaux ouverts à tous.  
Ouvrez un nouvel onglet de requête et tapez :

```sql
SELECT 
    name, 
    iso, 
    latitude, 
    longitude, 
    wmo_wind AS vent_noeuds
FROM 
    `bigquery-public-data.noaa_hurricanes.hurricanes`
WHERE 
    wmo_wind > 100
ORDER BY 
    wmo_wind DESC
LIMIT 10;
```
> **Le choc visuel pour l'étudiant :**  
> Montrez l'estimateur de volume en haut à droite. BigQuery a parcouru une table de données météo historiques mondiales sans qu'on ait eu besoin de télécharger un seul fichier sur son ordinateur portable ! C'est cela, la puissance du Cloud Data.

---

## 🏁 Bilan du TP 1 (Débrief en plénière - 20 minutes)
1. Est-ce que le SQL vous a paru si difficile que cela ?
2. Quelle différence entre faire cela sur Excel et dans le Cloud ?
3. Dès demain matin, nous allons transformer ces requêtes textuelles en une véritable **carte de contrôle visuelle interactive** pour les commandants de bord !
