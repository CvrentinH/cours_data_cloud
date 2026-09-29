# Cours Cloud Data pour Master 2 (Non-Techniques)
## "Du Cloud au Cockpit Opérationnel : Piloter la Data comme dans la Marine Nationale"

- **Intervenant** : Data Manager – Marine Nationale
- **Public** : Étudiants de Master 2 (Profils non-techniques : Management, Supply Chain, Relations Internationales / Défense, Stratégie, Économie)
- **Durée totale** : 14 heures réparties en 4 sessions de 3h30 (2 journées de 7h)
- **Prérequis techniques** : Zéro code requis. Un simple navigateur web suffit (Google Chrome / Edge / Firefox) et un compte Google (perso ou universitaire).

---

## 🎯 Philosophie & Approche Pédagogique

### Le Piège à Éviter
Les étudiants M2 non-tech ont souvent peur de la data et du cloud (peur du code, des lignes de commande, de la carte bancaire sur AWS/Azure, des acronymes barbares IAM, VPC, Kubernetes).

### La Clé du Succès
1. **L'analogie maritime comme fil conducteur** : Vous êtes Data Manager dans la Marine Nationale. Utilisez votre quotidien ! Les navires, sémaphores, drones de surveillance côtière, la lutte contre les trafics et le suivi des flux maritimes mondiaux sont ultra-fédérateurs et très parlants pour comprendre le volume, la vitesse et la variété des données.
2. **Le Cloud par l'usage et la décision** : On n'apprend pas à créer des clusters de serveurs, on apprend à **comprendre la chaîne de valeur du Cloud** (Où dorment les données ? Comment les interroge-t-on sans serveur ? Comment les transformer en tableau de bord d'aide à la décision ?).
3. **Zéro barrière financière ni installation locale** :
   - **Google BigQuery Sandbox** : 100% gratuit, **SANS CARTE BANCAIRE**, directement dans le navigateur, 1 To de requêtage gratuit par mois.
   - **Looker Studio** : Outil de Data Visualisation gratuit, sans code, interconnecté en 1 clic à BigQuery.

---

## 📅 Découpage des 14 Heures (4 sessions de 3h30)

| Jour | Créneau | Module | Objectif Pédagogique | Modalité | Ressources & Fichiers mobilisés |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Jour 1** | **Matin (3h30)** | **Session 1 : Démystifier le Cloud Data & Enjeux Maritimes** | Comprendre ce qu'est le Cloud, pourquoi l'On-Premise sature, vocabulaire clé (SaaS/PaaS/IaaS, Data Lake vs Data Warehouse, Serverless) et le cas de la Marine. | Cours interactif, analogies concrètes, quiz d'ouverture | • [`cours/01_introduction_cloud_data.md`](cours/01_introduction_cloud_data.md)<br/>• [`cours/02_architecture_et_donnees_maritimes.md`](cours/02_architecture_et_donnees_maritimes.md)<br/>• [`cours/guide_pedagogique_et_slides.md`](cours/guide_pedagogique_et_slides.md) |
| **Jour 1** | **Après-midi (3h30)** | **Session 2 : Atelier Pratique 1 – Exploration de la Flotte avec BigQuery** | Prise en main de Google BigQuery Sandbox. Import et requêtage assisté d'un jeu de données maritimes (positions AIS de navires, anomalies de route). | Atelier guidé pas-à-pas en binôme | • [`ateliers/TP1_BigQuery_Surveillance_Maritime.md`](ateliers/TP1_BigQuery_Surveillance_Maritime.md)<br/>• [`donnees/donnees_maritimes_ais_sample.csv`](donnees/donnees_maritimes_ais_sample.csv)<br/>• [`donnees/dictionnaire_des_donnees.md`](donnees/dictionnaire_des_donnees.md)<br/>• Console Google BigQuery Sandbox |
| **Jour 2** | **Matin (3h30)** | **Session 3 : Atelier Pratique 2 – Du Cloud à la Décision (Dashboard Looker)** | Connecter le Data Warehouse à un outil décisionnel sans code. Construire une carte interactive de surveillance maritime et des KPIs d'alerte. | Atelier pratique de restitution visuelle | • [`ateliers/TP2_Dashboard_Looker_Studio.md`](ateliers/TP2_Dashboard_Looker_Studio.md)<br/>• Table BigQuery `marine_nationale.positions_ais`<br/>• Google Looker Studio |
| **Jour 2** | **Après-midi (3h30)** | **Session 4 : Gouvernance, FinOps, Souveraineté & Jeu de Rôle Final** | Comprendre les risques réels du Cloud (coûts cachés, Cloud Act américain vs SecNumCloud français, sécurité) + Mini-Hackathon / Jeu de rôle décisionnel. | Cours synthétique + Simulation d'un comité d'état-major | • [`cours/03_gouvernance_finops_souverainete.md`](cours/03_gouvernance_finops_souverainete.md)<br/>• [`ateliers/TP3_Jeu_de_Role_Comite_Arbitrage.md`](ateliers/TP3_Jeu_de_Role_Comite_Arbitrage.md) |

---

## 🗂️ Structure du Dossier

- **`cours/`** :
  - [`guide_pedagogique_et_slides.md`](cours/guide_pedagogique_et_slides.md) : Guide d'animation minute par minute et trame des diapositives.
  - [`01_introduction_cloud_data.md`](cours/01_introduction_cloud_data.md) : Les bases du Cloud sans jargon.
  - [`02_architecture_et_donnees_maritimes.md`](cours/02_architecture_et_donnees_maritimes.md) : Pourquoi la Marine utilise le Cloud (AIS, IoT marin, maintenance).
  - [`03_gouvernance_finops_souverainete.md`](cours/03_gouvernance_finops_souverainete.md) : FinOps, Cloud souverain (SecNumCloud) et sécurité.
- **`ateliers/`** :
  - [`TP1_BigQuery_Surveillance_Maritime.md`](ateliers/TP1_BigQuery_Surveillance_Maritime.md) : TP d'exploration de données AIS maritimes (avec requêtes fournies).
  - [`TP2_Dashboard_Looker_Studio.md`](ateliers/TP2_Dashboard_Looker_Studio.md) : TP de création d'un tableau de bord de surveillance maritime.
  - [`TP3_Jeu_de_Role_Comite_Arbitrage.md`](ateliers/TP3_Jeu_de_Role_Comite_Arbitrage.md) : Cas pratique final d'évaluation en équipe.
- **`donnees/`** :
  - [`donnees_maritimes_ais_sample.csv`](donnees/donnees_maritimes_ais_sample.csv) : Dataset maritime synthétique réaliste prêt à être importé.
  - [`dictionnaire_des_donnees.md`](donnees/dictionnaire_des_donnees.md) : Explication de chaque colonne pour les étudiants.
