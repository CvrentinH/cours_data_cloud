# TP 3 & Évaluation Finale : Le Jeu de Rôle du Comité d'Arbitrage Cloud

**Durée :** 2h00 (Jour 2 - Après-midi)  
**Modalité :** Équipes de 4 ou 5 étudiants  
**Format :** Jeu de rôle stratégique / Simulation de décision de comité de direction  
**Contexte :** Projet "SURMAR-DATA 2030" (Surveillance Maritime et Détection Augmentée)

---

## 🎯 Pourquoi ce format pour des étudiants M2 ?

Dans leur future vie professionnelle (qu'ils soient consultants chez Capgemini/Wavestone, chefs de projet, directeurs supply chain ou chargés de mission défense), ces étudiants ne passeront pas leur journée à taper du SQL.  
**Leur valeur ajoutée sera d'arbitrer entre des contraintes contradictoires :**
- L'efficacité opérationnelle (aller vite, avoir les meilleures IA).
- La maîtrise budgétaire (éviter la faillite FinOps).
- La souveraineté et la conformité légale (RGPD, Cloud Act, SecNumCloud).

---

## 🎬 Le Scénario de la Simulation

> **La situation :**  
> Le Ministère des Armées et l'État-Major de la Marine Nationale lancent la refonte du système d'information de surveillance maritime.  
> Les capteurs radars, drones côtiers, bouées acoustiques et flux satellites génèrent **500 Teraoctets de données par an**.  
> Le comité de direction doit choisir l'architecture Cloud pour les 10 prochaines années. Un budget initial de 5 millions d'euros est alloué.

---

## 🎭 Les Rôles au sein de chaque équipe (4 à 5 étudiants)

Chaque membre du groupe incarne un personnage avec ses propres objectifs et ses lignes rouges :

### 1. Le Chef des Opérations Maritimes (COM)
- **Sa devise :** *"La vitesse prime sur tout. Je veux que mes commandants en mer aient l'information en temps réel, peu importe la marque du serveur."*
- **Ses exigences :** Zéro temps de latence, connectivité mondiale sur tous les océans, intégration des derniers modèles d'IA générative pour détecter les menaces.
- **Son risque :** Ne regarde pas la facture et se moque de la réglementation.

### 2. Le Responsable Sécurité des SI & Souveraineté (RSSI / DGA / ANSSI)
- **Sa devise :** *"Plutôt le papier-crayon qu'un serveur américain soumis au Cloud Act."*
- **Ses exigences :** Certification **SecNumCloud**, données hébergées impérativement sur le sol français, chiffrement avec clés souveraines exclusives.
- **Son risque :** Bloquer l'innovation et proposer des solutions obsolètes ou trop lentes.

### 3. Le Directeur Financier / Responsable FinOps
- **Sa devise :** *"Le Cloud est un gouffre financier si personne ne surveille les robinets."*
- **Ses exigences :** Prévisibilité des coûts sur 5 ans, alertes de budget obligatoires, politique stricte de hiérarchisation du stockage (passage au stockage froid après 30 jours).
- **Son risque :** Sous-dimensionner l'infrastructure pour faire des économies de bouts de chandelle.

### 4. Le Data Manager & Architecte de Données (Votre rôle !)
- **Sa devise :** *"Mon travail est de réconcilier les trois autres sans compromettre la qualité de la donnée."*
- **Ses exigences :** Une architecture cohérente (Data Lake + Data Warehouse moderne), un catalogue de données clair, des accès cloisonnés (RBAC) et une gouvernance pérenne.

---

## 🏗️ Les 3 Options Technologiques sur la Table

Le groupe doit analyser et trancher entre 3 propositions :

| Option | Description | Avantages | Inconvénients majeurs |
| :--- | :--- | :--- | :--- |
| **Option A : Le Cloud Public Américain (AWS / Google Cloud)** | Utiliser directement les technologies de pointe de GCP ou AWS avec leurs services managés d'IA. | Puissance phénoménale, zéro maintenance, catalogues d'algorithmes les plus avancés du monde. | **Vulnérabilité légale au Cloud Act**, refus probable de l'ANSSI pour les données classifiées, risque de dérapage FinOps. |
| **Option B : Le 100% Souverain On-Premise (Serveurs Physiques dans les Bunkers de la Marine)** | Tout racheter et installer dans les salles serveurs militaires de Brest et Toulon. | Souveraineté totale, aucun accès extérieur, conformité militaire maximale. | **Coût d'investissement colossal (CAPEX)**, obsolescence rapide du matériel, impossibilité de scaler rapidement face à une crise maritime majeure. |
| **Option C : Le Cloud Hybride de Confiance (SecNumCloud type S3NS / Bleu / 3DS Outscale / OVHcloud)** | Architecture mixte : stockage des données ultra-sensibles en environnement qualifié SecNumCloud, et traitement des flux publics mondiaux (AIS commercial) sur le Cloud public. | Bon équilibre sécurité/innovation, conformité ANSSI, flexibilité. | Intégration plus complexe, coût unitaire parfois plus élevé que le cloud américain brut. |

---

## ⏱️ Déroulement de la séance (2h00)

1. **Phase de délibération interne (45 minutes)** :
   - Les étudiants débattent au sein de leur groupe.
   - Ils rédigent un document de synthèse d'**une seule page (ou 2 slides)** :
     - Quelle option choisissent-ils ? (Ou quelle combinaison hybride ?)
     - Comment rassurent-ils le RSSI sur la souveraineté ?
     - Quels garde-fous FinOps mettent-ils en place pour le Directeur Financier ?
     - Comment garantissent-ils aux Opérations la vitesse de détection ?
2. **Les "Pitchs de Direction" (45 minutes)** :
   - Chaque groupe passe à la tribune pendant **4 minutes chrono** pour présenter sa décision devant "l'État-Major" (joué par l'intervenant).
   - 2 minutes de questions déstabilisantes posées par l'intervenant (ex: *"Vous avez choisi l'Option A, que répondez-vous au Ministre si la justice américaine demande nos logs ?"* ou *"Vous avez choisi l'Option B, comment gérez-vous l'arrivée d'une crise en mer Rouge le mois prochain ?"*).
3. **Débriefing Général & Remise des Conclusions (30 minutes)** :
   - Analyse comparative des choix faits par chaque groupe.
   - Conclusion sur la réalité du terrain dans les grandes organisations françaises.

---

## 📊 Grille d'Évaluation Simple & Bienveillante

- **Compréhension des enjeux Cloud & FinOps (30%)** : Ont-ils compris les mécanismes de coûts et d'élasticité ?
- **Prise en compte de la Souveraineté & Réglementation (30%)** : Le rôle de SecNumCloud et du Cloud Act est-il maîtrisé ?
- **Cohérence managériale et argumentation (20%)** : Le compromis entre sécurité, budget et métier est-il réaliste ?
- **Aisance à l'oral & esprit d'équipe (20%)** : Chacun des rôles a-t-il pris la parole ?
