# TP 2 : Cockpit Opérationnel – Tableau de Bord Décisionnel de la Flotte Navale (Looker Studio)

**Durée :** 3h30 (Jour 2 - Matin)  
**Modalité :** En binôme (ou individuel)  
**Outil :** Google Looker Studio (100% gratuit, 100% sans code, dans le navigateur)  
**Données :** [`donnees_tp2_missions_flotte.csv`](../donnees/donnees_tp2_missions_flotte.csv)  
**Évaluation :** Noté sur 20 points (barème détaillé en fin de document)

> [!IMPORTANT]
> **Autonomie totale du TP 2 par rapport au TP 1 :**  
> Ce TP utilise un **jeu de données neuf et dédié** (`donnees_tp2_missions_flotte.csv`). Vous repartez sur une base saine et vierge : aucune manipulation du TP 1 n'est requise pour réussir ce sujet.

---

## 🎯 Objectifs Pédagogiques

1. Découvrir la **Business Intelligence (BI)** dans le Cloud : transformer des lignes de données brutes en un outil visuel d'aide à la décision.
2. Respecter les règles d'ergonomie d'un tableau de bord de direction (règle des 5 secondes, hiérarchie visuelle).
3. Concevoir une cartographie des déploiements navals mondiaux, des cartes de score (KPIs) et des filtres interactifs.
4. Présenter sa situation opérationnelle lors d'un **Briefing d'État-Major de 3 minutes**.

---

## 🚀 Étape 1 : Connexion des Données à Looker Studio (10 minutes)

Vous avez deux méthodes simples au choix pour charger votre jeu de données :

### Méthode A (Recommandée - Via BigQuery) :
1. Allez sur votre console [Google BigQuery](https://console.cloud.google.com/bigquery).
2. Dans votre projet, sous `marine_nationale`, cliquez sur les 3 points > **Créer une table**.
   - Source : **Importer (Upload)** > choisir `donnees_tp2_missions_flotte.csv`.
   - Nom de la table : `missions_flotte`.
   - Schéma : cocher **Détecter automatiquement**.
   - Cliquer sur **Créer la table**.
3. Cliquez sur **Explorer les données** > **Explorer avec Looker Studio**.

### Méthode B (Secours direct sans BigQuery) :
1. Rendez-vous directement sur [Looker Studio](https://lookerstudio.google.com).
2. Cliquez sur **Créer** > **Rapport**.
3. Dans la liste des connecteurs, choisissez **Importation de fichiers (File Upload)** et déposez directement le fichier `donnees_tp2_missions_flotte.csv`.

---

## 🧭 Étape 2 : Le Cahier des Charges de l'État-Major

Votre tableau de bord doit permettre à l'Amiral commandant les opérations maritimes de piloter les déploiements de la flotte navale française à travers le monde.

### 1. En-tête & Identité Visuelle
- Titre : `ÉTAT-MAJOR DE LA MARINE – TABLEAU DE BORD DU DÉPLOIEMENT OPÉRATIONNEL`
- Sous-titre : `Suivi mondial des missions, consommations et interventions en mer`
- Style sobre et professionnel : fond sombre (bleu marine / ardoise) ou clair épuré.

### 2. Les 4 Indicateurs Clés de Performance (Cartes de score / Scorecards)
Insérez 4 zones de texte chiffrées en haut de page :
1. **Missions Totales Déployées** : Comptage distinct de `id_mission`.
2. **Missions Actuellement en Mer** : Nombre de missions avec le statut `En cours`.
3. **Total des Interventions Réussies** : Somme de `interventions_succes` (sauvetages, arraisonnements narcotrafic).
4. **Jours de Mer Cumulés** : Somme de `duree_jours` (effort opérationnel global de la flotte).

### 3. La Carte Géographique Mondiale des Déploiements
Ajoutez un graphique de type **Carte à bulles (Google Maps)** :
- **Latitude** : champ `latitude_theatre`.
- **Longitude** : champ `longitude_theatre`.
- **Taille de la bulle** : métrique `duree_jours` (ou `cout_total_euros`).
- **Couleur de la bulle** : dimension `type_batiment` ou `statut_mission`.
- **Info-bulle (Tooltip)** : afficher `nom_batiment`, `type_mission` et `port_attache`.

### 4. Deux Graphiques Analytiques Complémentaires
- **Graphique 1 (Barres horizontales)** : *Nombre d'interventions réussies par type de mission* (permet de visualiser l'efficacité de la lutte narcotrafic vs sauvetage en mer).
- **Graphique 2 (Anneau / Donut)** : *Répartition des jours de mer par base navale d'attache* (`port_attache` : Brest, Toulon, Cherbourg, Outre-Mer).

### 5. Les Commandes de Filtrage Interactif (Menus Déroulants)
Ajoutez 3 filtres interactifs en haut ou sur le côté pour permettre au décideur de segmenter la vue :
- **Filtre 1** : `zone_operationnelle` (ex: Méditerranée, Golfe de Guinée, Océan Indien, Atlantique...).
- **Filtre 2** : `statut_mission` (Terminée, En cours, En préparation).
- **Filtre 3** : `type_batiment` (Frégate, Patrouilleur, Porte-hélicoptères...).

### 6. Le Tableau Récapitulatif Opérationnel
En bas de page, insérez un tableau listant les missions actives :
- Colonnes : `id_mission`, `nom_batiment`, `type_mission`, `zone_operationnelle`, `date_depart`, `statut_mission`.

---

## 🎙️ Étape 3 : Le Briefing Opérationnel de Restitution (45 minutes)

Chaque binôme présente son cockpit pendant **3 minutes chrono** face à l'Amiral (l'enseignant) :
1. **Minute 1** : Synthèse de la situation générale (lecture commentée des 4 KPIs).
2. **Minute 2** : Utilisation des filtres en direct pour faire un focus sur un théâtre chaud (ex: filtrer sur *Golfe de Guinée* ou *Océan Indien*).
3. **Minute 3** : Recommandation de gestion (arbitrage logistique ou redéploiement d'un bâtiment).

---

## 📊 Grille d'Évaluation & Barème de Notation (sur 20 points)

| Critère | Barème | Description des attentes |
| :--- | :---: | :--- |
| **Pertinence des KPIs & Métriques** | **/ 5 pts** | Les 4 cartes de score sont correctement calculées (comptage distinct, sommes justes, libellés clairs). |
| **Qualité & Précision de la Carte** | **/ 5 pts** | Les bulles sont bien géolocalisées sur le globe, les tailles et couleurs apportent une vraie valeur informative. |
| **Interactivité & Menus de Filtrage** | **/ 4 pts** | Les 3 filtres fonctionnent correctement et actualisent dynamiquement tous les visuels du dashboard. |
| **Ergonomie & Design Décisionnel** | **/ 3 pts** | Respect de la règle des 5 secondes : pas de surcharge visuelle, contrastes lisibles, alignement soigné. |
| **Briefing d'État-Major (Restitution orale)** | **/ 3 pts** | Synthèse claire, posture managériale, réponse fluide aux questions de l'Amiral. |
