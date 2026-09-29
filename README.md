# Cours Cloud Data pour Master 2 (Non-Techniques)
## "Du Cloud au Cockpit Opérationnel : Piloter la Data comme dans la Marine Nationale"

- **Intervenant** : Data Manager – Marine Nationale
- **Public** : Étudiants de Master 2 (Profils non-techniques : Management, Supply Chain, Défense, Stratégie, Économie)
- **Durée totale** : 14 heures (4 sessions de 3h30 sur 2 journées de 7h)
- **Prérequis techniques** : Zéro code requis. Un simple navigateur web suffit et un compte Google personnel ou étudiant.
- **Guide de l'enseignant & conducteur de présentation** : [`cours/guide_pedagogique_et_slides.md`](cours/guide_pedagogique_et_slides.md)

---

## 🎯 Philosophie & Approche Pédagogique

### Le Piège à Éviter
Les étudiants M2 non-tech ont souvent peur du code, des terminaux en ligne de commande et des facturations imprévues sur le Cloud.

### La Clé du Succès
1. **L'analogie maritime comme fil rouge** : En tant que Data Manager de la Marine, vous apportez des cas réels (surveillance côtière, détection de navires suspects, maintenance de flotte).
2. **Le Cloud par l'usage managérial** : Comprendre la valeur business et opérationnelle, savoir poser les bonnes questions à la donnée et décider.
3. **Zéro friction technique** : Utilisation de **Google BigQuery Sandbox** (gratuit, sans carte bleue) et de **Looker Studio** (outil de dataviz no-code dans le navigateur).

---

## 📅 Découpage Précis des 14 Heures & Fichiers Associés

Chaque demi-journée a son fichier de cours et/ou son atelier dédié :

| Créneau | Objectifs de la session | Fichiers & Données utilisés |
| :--- | :--- | :--- |
| **JOUR 1 – MATIN**<br/>*(3h30)* | **Comprendre le Cloud sans jargon**<br/>• Qu'est-ce que le Cloud ? (élasticité, pay-as-you-go)<br/>• On-Premise vs Cloud : IaaS, PaaS, SaaS<br/>• Le Serverless et le découplage Stockage / Calcul<br/>• Pourquoi Excel sature face aux flux maritimes massifs | 📖 **Support de cours :**<br/>[`cours/01_introduction_cloud_data.md`](cours/01_introduction_cloud_data.md) |
| **JOUR 1 – APRÈS-MIDI**<br/>*(3h30)* | **Prise en main du Cloud & Requêtage maritime**<br/>• Intro express (20 min) : Comment marche l'AIS & les 4 mots du SQL<br/>• Atelier BigQuery Sandbox (zéro carte bleue)<br/>• Import des pings de navires & requêtes de surveillance<br/>• Détection des navires suspects (pétroliers rapides, arrêts anormaux) | 📖 **Support introductif :**<br/>[`cours/02_architecture_et_donnees_maritimes.md`](cours/02_architecture_et_donnees_maritimes.md)<br/><br/>🛠️ **Atelier pratique :**<br/>[`ateliers/TP1_BigQuery_Surveillance_Maritime.md`](ateliers/TP1_BigQuery_Surveillance_Maritime.md)<br/><br/>📊 **Données :**<br/>• [`donnees/donnees_maritimes_ais_sample.csv`](donnees/donnees_maritimes_ais_sample.csv)<br/>• [`donnees/dictionnaire_des_donnees.md`](donnees/dictionnaire_des_donnees.md) |
| **JOUR 2 – MATIN**<br/>*(3h30)* | **Du Data Warehouse à la Décision (Dataviz No-Code)**<br/>• **100% indépendant du TP 1** (évaluation autonome sur base saine)<br/>• Règles d'ergonomie d'un dashboard d'état-major<br/>• Connexion BigQuery ou directe ➔ Looker Studio en 1 clic<br/>• Création de la carte interactive des déploiements navals et des KPIs<br/>• Restitution : Briefing opérationnel de 3 min par binôme | 🛠️ **Atelier pratique (Noté /20) :**<br/>[`ateliers/TP2_Dashboard_Looker_Studio.md`](ateliers/TP2_Dashboard_Looker_Studio.md)<br/><br/>📊 **Données dédiées au TP 2 :**<br/>• [`donnees/donnees_tp2_missions_flotte.csv`](donnees/donnees_tp2_missions_flotte.csv)<br/>• [`donnees/dictionnaire_donnees_tp2.md`](donnees/dictionnaire_donnees_tp2.md) |
| **JOUR 2 – APRÈS-MIDI**<br/>*(3h30)* | **Gouvernance, FinOps, Souveraineté & Jeu de Rôle**<br/>• Cours stratégique (1h15) : FinOps (dérives de coûts), Cloud Act américain vs SecNumCloud français (ANSSI), gouvernance<br/>• Simulation finale (2h) : Comité d'arbitrage "SURMAR 2030"<br/>• Débat en équipes (Opérations vs RSSI vs FinOps vs Data Manager)<br/>• Pitch final de chaque groupe et bilan des 14h | 📖 **Support de cours :**<br/>[`cours/03_gouvernance_finops_souverainete.md`](cours/03_gouvernance_finops_souverainete.md)<br/><br/>🎭 **Jeu de rôle / Évaluation (Noté /20) :**<br/>[`ateliers/TP3_Jeu_de_Role_Comite_Arbitrage.md`](ateliers/TP3_Jeu_de_Role_Comite_Arbitrage.md) |

---

## 🗂️ Répertoire Complet des Fichiers du Projet

```text
cours_cloud_data/
├── README.md                                  <- Ce fichier de cadrage
├── cours/
│   ├── guide_pedagogique_et_slides.md         <- Conducteur enseignant (planning minute par minute + slides)
│   ├── 01_introduction_cloud_data.md          <- COURS J1 MATIN (Fondamentaux du Cloud)
│   ├── 02_architecture_et_donnees_maritimes.md <- COURS J1 APRÈS-MIDI (Intro Architecture, AIS & SQL)
│   └── 03_gouvernance_finops_souverainete.md  <- COURS J2 APRÈS-MIDI (FinOps, SecNumCloud, Souveraineté)
├── ateliers/
│   ├── TP1_BigQuery_Surveillance_Maritime.md  <- TP J1 APRÈS-MIDI (BigQuery Sandbox - Noté /20)
│   ├── TP2_Dashboard_Looker_Studio.md         <- TP J2 MATIN (Dashboard Looker Studio - Noté /20 - Indépendant)
│   └── TP3_Jeu_de_Role_Comite_Arbitrage.md    <- ÉVALUATION J2 APRÈS-MIDI (Comité stratégique - Noté /20)
└── donnees/
    ├── donnees_maritimes_ais_sample.csv       <- Données TP 1 (2 000 navires AIS + 31 anomalies)
    ├── dictionnaire_des_donnees.md            <- Dictionnaire des colonnes TP 1
    ├── donnees_tp2_missions_flotte.csv        <- Données TP 2 (400 missions navales mondiales)
    └── dictionnaire_donnees_tp2.md            <- Dictionnaire des colonnes TP 2
```
