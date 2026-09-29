# Guide Pédagogique & Trame des Diapositives (Pour le Formateur)

Ce document est votre conducteur personnel pour animer les 14 heures de formation auprès des étudiants de Master 2.

---

## ⏱️ Déroulé Minute par Minute des 4 Sessions (14h)

### JOUR 1 – MATIN (Session 1 : 09h00 - 12h30 | 3h30)
**Thème : Démystifier le Cloud & Enjeux Maritimes**

| Horaire | Durée | Étape & Contenu | Ce que vous faites / dites |
| :--- | :--- | :--- | :--- |
| **09h00 - 09h30** | 30 min | **Tour de table & Icebreaker** | Présentation de votre rôle (Data Manager Marine Nationale). Demandez : *"Qui a déjà touché au Cloud ?"*, *"Qui a peur de coder ?"*. Rassurez immédiatement : 0 code barbare au programme. |
| **09h30 - 10h15** | 45 min | **Le choc de la donnée maritime** | Montrez MarineTraffic en direct. Chiffres clés (100k navires, millions de messages AIS/jour). Pourquoi Excel explose au bout de 10 min. |
| **10h15 - 10h30** | 15 min | *Pause Café* ☕ | Laissez décanter. |
| **10h30 - 11h30** | 60 min | **Les Concepts Clés sans jargon** | L'analogie de la pizza (On-Premise vs IaaS/PaaS/SaaS). L'élasticité. La séparation Stockage / Calcul. Le Serverless. |
| **11h30 - 12h00** | 30 min | **Quiz Interactif & Échanges** | Le mini-quiz du Module 1 (à main levée ou Wooclap). Discussion sur Edge vs Cloud en pleine mer. |
| **12h00 - 12h30** | 30 min | **Tour guidé en direct de la Console Cloud** | Vous partagez votre écran : vous ouvrez Google Cloud Console / BigQuery. Démystification visuelle de l'outil. |

---

### JOUR 1 – APRÈS-MIDI (Session 2 : 14h00 - 17h30 | 3h30)
**Thème : Atelier Pratique 1 – BigQuery Sandbox & Surveillance Maritime**

| Horaire | Durée | Étape & Contenu | Ce que vous faites / dites |
| :--- | :--- | :--- | :--- |
| **14h00 - 14h25** | 25 min | **Lancement du TP1 & Connexion** | Tout le monde ouvre BigQuery Sandbox dans son navigateur. Création du projet `marine-data-m2`. |
| **14h25 - 14h50** | 25 min | **Import du fichier CSV** | Téléchargement et import de `donnees_maritimes_ais_sample.csv`. Découverte des colonnes dans BigQuery. |
| **14h50 - 15h40** | 50 min | **Exercices 1, 2 et 3 (SQL guidé)** | `SELECT`, `COUNT`, `ORDER BY`, `GROUP BY`. Circulez dans les rangs pour débloquer les petites coquilles de frappe. |
| **15h40 - 15h55** | 15 min | *Pause Café* ☕ | |
| **15h55 - 16h50** | 55 min | **Exercice 4 (Détection d'anomalies)** | Analyse des navires suspects (`alerte_anomalie = 1`). Discussion tactique : que fait-on de cette information ? |
| **16h50 - 17h15** | 25 min | **Exercice 5 (Bonus BigQuery Public Data)** | Découverte des millions de lignes de données cyclones/météo sans rien installer. Effet "Whaou". |
| **17h15 - 17h30** | 15 min | **Débrief & Bilan FinOps** | Pointer l'indicateur d'octets scannés : *"Combien notre après-midi aurait-elle coûté si nous étions en entreprise ?"* (Réponse : quelques centimes). |

---

### JOUR 2 – MATIN (Session 3 : 09h00 - 12h30 | 3h30)
**Thème : Atelier Pratique 2 – Looker Studio & Cockpit Décisionnel**

| Horaire | Durée | Étape & Contenu | Ce que vous faites / dites |
| :--- | :--- | :--- | :--- |
| **09h00 - 09h30** | 30 min | **Introduction à la Business Intelligence** | Pourquoi un tableau de bord décisionnel ? Les règles d'un bon dashboard pour l'état-major. Présentation du sujet TP 2 et de ses données autonomes (`donnees_tp2_missions_flotte.csv`). |
| **09h30 - 10h30** | 60 min | **Construction du Dashboard (Partie 1)** | Chargement du CSV en 2 min dans BigQuery (ou direct Looker). Création des Scorecards (Missions actives, Interventions, Jours de mer) et filtres interactifs. |
| **10h30 - 10h45** | 15 min | *Pause Café* ☕ | |
| **10h45 - 11h45** | 60 min | **Construction du Dashboard (Partie 2)** | Création de la Carte mondiale Google Maps à bulles. Graphiques d'interventions et de bases navales. Tableau récapitulatif. |
| **11h45 - 12h30** | 45 min | **Briefings à l'Amiral (Restitution /3 pts)** | Chaque binôme passe 3 minutes chrono pour présenter sa situation opérationnelle en direct. |

---

### JOUR 2 – APRÈS-MIDI (Session 4 : 14h00 - 17h30 | 3h30)
**Thème : Gouvernance, Souveraineté & Jeu de Rôle Final**

| Horaire | Durée | Étape & Contenu | Ce que vous faites / dites |
| :--- | :--- | :--- | :--- |
| **14h00 - 15h15** | 75 min | **Cours stratégique : Les dessous du Cloud** | FinOps (le cas du stagiaire à 400k$), Cloud Act américain vs SecNumCloud français, RGPD, S3NS/Bleu/Outscale. |
| **15h15 - 15h30** | 15 min | *Pause Café* ☕ | Constitution des équipes de 4-5 étudiants pour la simulation finale. |
| **15h30 - 16h20** | 50 min | **Simulation : Comité SURMAR 2030** | Travail en équipe : Débat entre Opérations, RSSI, FinOps et Data Manager pour choisir l'architecture de la Marine. |
| **16h20 - 17h10** | 50 min | **Pitchs des Comités d'Arbitrage** | 4 minutes de pitch par équipe + 2 minutes de questions déstabilisantes de l'intervenant. |
| **17h10 - 17h30** | 20 min | **Conclusion générale & Conseils Carrière** | Synthèse des 2 journées. Comment valoriser cette compétence Cloud Data sur leur CV de M2. |

---

## 🖥️ Trame des Diapositives (Prête à être copiée dans vos slides)

### Bloc 1 : Introduction & Fondamentaux
- **Slide 1 :** Titre : *Du Cloud au Cockpit Opérationnel : Piloter la Data de la Marine Nationale* (Votre nom & fonction).
- **Slide 2 :** L'Océan de données : 100 000 navires, 864 millions de pings AIS par jour, capteurs satellites.
- **Slide 3 :** Le mur d'Excel et de l'ordinateur personnel : pourquoi les outils classiques s'effondrent.
- **Slide 4 :** Qu'est-ce que le Cloud ? (Définition simple, élasticité, paiement à l'usage).
- **Slide 5 :** La métaphore de la pizza : On-Premise vs IaaS vs PaaS vs SaaS.
- **Slide 6 :** L'architecture moderne : Data Lake (stocker tout) vs Data Warehouse (organiser pour décider).
- **Slide 7 :** Le concept révolutionnaire : Découplage Stockage / Calcul & le "Serverless".

### Bloc 2 : Données Maritimes & Outils
- **Slide 8 :** L'AIS maritime : De la balise VHF du navire au satellite de basse orbite.
- **Slide 9 :** Cas d'usage : Sécurité en mer, lutte contre les trafics, logistique portuaire.
- **Slide 10 :** Le SQL sans peur : SELECT, FROM, WHERE, GROUP BY expliqués en langage naturel.
- **Slide 11 :** Découverte de Google BigQuery Sandbox : Zéro coût, zéro carte bleue, puissance maximale.

### Bloc 3 : Data Visualisation & Prise de Décision
- **Slide 12 :** Pourquoi la Data Visualisation ? La règle des 5 secondes pour un état-major ou un comité de direction.
- **Slide 13 :** Le pont BigQuery <-> Looker Studio.
- **Slide 14 :** Anatomie d'un dashboard tactique : KPIs clés, cartographie dynamique, filtres opérationnels.

### Bloc 4 : Gouvernance, FinOps & Souveraineté
- **Slide 15 :** Le piège du Cloud : Comment une boucle de code a coûté 400 000 $ en un week-end.
- **Slide 16 :** La culture FinOps : Responsabilité financière partagée et surveillance des requêtes.
- **Slide 17 :** Géopolitique du Cloud : Le Cloud Act américain vs le RGPD européen.
- **Slide 18 :** La réponse de la France : Le label SecNumCloud de l'ANSSI et les clouds de confiance (S3NS, Bleu, OVHcloud, Outscale).
- **Slide 19 :** L'IA Générative dans le Cloud : Poser des questions à la base maritime en langage naturel.
- **Slide 20 :** Lancement du cas pratique final : Projet SURMAR-DATA 2030.

---

## 💡 Astuces & Conseils pour Gérer la Salle

1. **Si un étudiant est bloqué avec son compte Google :**
   - S'il utilise un compte Google étudiant géré par son université qui bloque l'accès à la Google Cloud Console, demandez-lui d'ouvrir un onglet en navigation privée avec un compte Gmail personnel standard.
2. **Si un étudiant a peur du SQL :**
   - Rappelez-lui qu'il s'agit d'un "copier-coller intelligent". Le but n'est pas d'apprendre la syntaxe par cœur, mais de comprendre ce que chaque bloc de commande accomplit.
3. **Valorisation sur le CV :**
   - À la fin du cours, encouragez-les à ajouter sur leur profil LinkedIn / CV :  
     *`Compétences : Cloud Data Analytics (Google BigQuery), Business Intelligence (Looker Studio), Sensibilisation FinOps & Souveraineté Numérique (SecNumCloud)`*.  
     Pour des profils non-ingénieurs (management/stratégie/supply chain), c'est un différenciateur énorme lors des entretiens d'embauche !
