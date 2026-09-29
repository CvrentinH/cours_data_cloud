# TP 2 : Du Cloud à la Décision – Créer le Tableau de Bord Opérationnel de la Marine (Looker Studio)

**Durée :** 3h30 (Jour 2 - Matin)  
**Modalité :** En binôme  
**Outil :** Google Looker Studio (100% gratuit, 100% sans code, directement relié à BigQuery)  
**Rôle des étudiants :** Data Manager & Analyste Opérationnel au Centre des Opérations Maritimes (COM)

---

## 🎯 Objectifs Pédagogiques

1. Comprendre le rôle de la **Business Intelligence (BI)** dans le Cloud : rendre la donnée intelligible pour les décideurs.
2. Éviter le piège du "rapport statique PDF" : créer un outil interactif, filtrable en direct.
3. Construire une cartographie maritime dynamique et des indicateurs d'alerte (KPIs) en quelques clics sans écrire une seule ligne de code.
4. Pitcher son tableau de bord lors d'une simulation de **Briefing Opérationnel d'État-Major**.

---

## 🚀 Étape 1 : Connecter BigQuery à Looker Studio en 1 Clic (10 minutes)

Il existe deux manières simples d'interconnecter les deux outils :

### Méthode Directe depuis BigQuery :
1. Dans votre console BigQuery, ouvrez votre table `positions_ais`.
2. Cliquez sur le bouton **"Explorer les données"** (en haut au centre), puis sur **"Explorer avec Looker Studio"**.
3. Une nouvelle page Looker Studio s'ouvre automatiquement : votre entrepôt Cloud est déjà branché !

### Ou Méthode depuis Looker Studio :
1. Rendez-vous sur : [https://lookerstudio.google.com](https://lookerstudio.google.com)
2. Cliquez sur **Créer** > **Rapport**.
3. Dans la liste des connecteurs Google, choisissez **BigQuery**.
4. Sélectionnez : **Mes projets** > Votre projet (`marine-data-m2`) > `marine_nationale` > `positions_ais` > Cliquez sur **Ajouter**.

---

## 🎨 Étape 2 : Le Cahier des Charges de l'Amiral (Design & Ergonomie)

Un bon tableau de bord pour un décideur doit respecter la règle des **5 secondes** : en un coup d'œil, le commandant doit savoir si la situation est sous contrôle ou si une alerte requiert son attention.

### Palette recommandée ("Aéronavale & Marine") :
- **Arrière-plan** : Bleu nuit profond ou gris ardoise épuré.
- **Accents d'alerte** : Rouge vif ou ambre pour les anomalies (`alerte_anomalie = 1`).
- **Couleurs de flotte** : Cyan/Bleu pour les civils, Vert pour les alliés/militaires.

---

## 🛠️ Étape 3 : Construction pas-à-pas du Cockpit (1h15)

### 1. Le Titre & L'En-tête
- Insérez une zone de texte en haut de la page :
  `CENTRE DES OPÉRATIONS MARITIMES – SITUATION DE SURFACE ET DÉTECTION D'ANOMALIES`
- Sous-titre : `Source : Flux AIS Cloud - Actualisation automatique BigQuery`

### 2. Les Cartes de Score (KPIs Décisionnels)
Dans la barre d'outils, cliquez sur **Ajouter un graphique** > **Zone de texte chiffrée (Scorecard)** :
- **Scorecard 1 - Volume de la Flotte** :
  - Métrique : `nom_navire` (définie sur `Nombre d'éléments distincts` / Count Distinct).
  - Libellé : `Navires Actifs Détectés`.
- **Scorecard 2 - Alertes Prioritaires** :
  - Métrique : `alerte_anomalie` (Somme).
  - Libellé : `Anomalies / Suspects`.
  - Style : Chiffre en rouge vif.
- **Scorecard 3 - Vitesse Moyenne** :
  - Métrique : `vitesse_noeuds` (définie sur `Moyenne`).
  - Libellé : `Vitesse Flotte (Nœuds)`.

### 3. La Carte Géographique Interactive (Le clou du spectacle !)
1. Cliquez sur **Ajouter un graphique** > **Carte géographique** (Google Maps / Bulle).
2. Dans le panneau de configuration à droite :
   - **Champ de localisation** : Faites glisser `latitude` ou créez un champ combiné, ou utilisez simplement le type géographique de Looker Studio.
   - *(Astuce simplissime : vous pouvez aussi utiliser la "Carte à bulles" avec `latitude` en latitude et `longitude` en longitude).*
   - **Taille de la bulle** : `longueur_metres` (les gros porte-conteneurs apparaissent plus grands que les chalutiers).
   - **Couleur** : `type_navire` ou `type_anomalie`.
   - **Info-bulle (Tooltip)** : `nom_navire`, `pavillon`, `vitesse_noeuds`, `destination`.

### 4. Les Menus Déroulants (Filtres Interactifs)
Permettez à l'amiral de filtrer la carte selon ses besoins :
1. Cliquez sur **Ajouter une commande** > **Liste déroulante**.
   - Champ de contrôle 1 : `zone_maritime` (Manche, Brest, Toulon...).
2. Ajoutez une deuxième liste déroulante :
   - Champ de contrôle 2 : `type_navire` (Cargo, Pétrolier, Militaire...).
3. Ajoutez une troisième commande :
   - Champ de contrôle 3 : `alerte_anomalie` (pour isoler instantanément les menaces).

### 5. La Table Tactique des Alertes
En bas du tableau de bord, ajoutez un **Tableau** pour lister les navires suspects :
- Dimensions : `nom_navire`, `pavillon`, `zone_maritime`, `vitesse_noeuds`, `type_anomalie`.
- Filtre du graphique : `alerte_anomalie = 1`.

---

## 🎙️ Étape 4 : L'Exercice "Briefing Opérationnel d'État-Major" (45 minutes)

Chaque binôme prépare un briefing de **3 minutes chrono** face à la promotion :

### Scénario :
> *"Vous êtes l'officier data de quart. L'Amiral entre dans la salle de crise à 08h00. Vous devez lui présenter la situation maritime en Manche et en Méditerranée à l'aide de votre tableau de bord Looker Studio."*

### Grille d'évaluation du briefing :
1. **Clarté de la synthèse** : Les chiffres clés sont-ils annoncés en 30 secondes ?
2. **Utilisation dynamique des filtres** : L'étudiant sait-il cliquer sur "Zone Méditerranée / Toulon" pour zoomer sur l'anomalie du navire russe à l'arrêt ?
3. **Recommandation managériale / opérationnelle** : L'étudiant ne se contente pas de lire des chiffres, il propose une décision (ex: *"Je préconise l'envoi d'un patrouilleur pour lever le doute"*).

---

## 🏆 Bilan de la session
Les étudiants ont accompli en moins de 24h ce que beaucoup pensaient réservé aux ingénieurs informaticiens :
- Importer des millions de données dans un Data Warehouse Cloud mondial.
- Les requêter en SQL.
- Livrer un outil de décision visuel professionnel et interactif.
