# Module 3 : Gouvernance, FinOps & Souveraineté du Cloud

**Durée estimée :** 1h30 de cours/débat + 2h de cas pratique / jeu de rôle  
**Public :** Étudiants Master 2 (Futurs managers, consultants, directeurs de projet)  
**Intervenant :** Data Manager – Marine Nationale

---

## 🎯 Pourquoi ce module est vital pour des M2 ?

Un ingénieur sait comment allumer un serveur ou écrire un pipeline de données.  
**Un manager, lui, doit répondre à 3 questions stratégiques :**
1. **Combien ça coûte et comment éviter la faillite ?** (La démarche **FinOps**)
2. **Nos données sont-elles protégées contre l'espionnage et les lois étrangères ?** (La **Souveraineté** & **SecNumCloud**)
3. **À qui appartiennent les données et qui a le droit de les voir ?** (La **Gouvernance**)

---

## 💸 1. Le FinOps : Quand le Cloud dérape

### L'Histoire vraie qui fait réfléchir :
Dans une grande entreprise de logistique, un stagiaire a écrit une boucle automatisée qui exécutait une requête `SELECT *` sur une table de 15 To toutes les 30 secondes pour actualiser un graphique.  
À 5 dollars le Teraoctet analysé sur BigQuery/Athena :
- Chaque requête coûtait : 15 To × 5 $ = 75 $.
- En 1 heure (120 requêtes) : **9 000 $**.
- Au bout du week-end (48 heures) : **432 000 $** de facture imprévue !

### Qu'est-ce que le FinOps ?
Le **FinOps** (*Financial Operations*) est la pratique de gestion financière appliquée au Cloud.  
C'est la collaboration permanente entre les équipes **Techniques (Data/Dev)**, **Finance (Contrôle de gestion)** et **Métier (Opérations)**.

### Les 4 réflexes d'un bon Data Manager :
1. **Bannir le `SELECT *`** : Toujours sélectionner uniquement les colonnes utiles (BigQuery est une base colonnaire : moins vous lisez de colonnes, moins vous payez).
2. **Mettre en place des alertes de budget (Budget Alerts & Quotas)** : Si la consommation dépasse 80% du budget mensuel, le système envoie une alerte automatique ou coupe les calculs non critiques.
3. **Partitionner les données par date** : Si on cherche les navires du 15 août, le moteur ne doit scanner que la journée du 15 août, pas les 10 dernières années de données.
4. **La hiérarchisation du stockage (Storage Tiering)** :
   - *Stockage Chaud (Hot)* : Données en temps réel (accessibles en 10 millisecondes, tarif standard).
   - *Stockage Froid (Cold / Glacier / Archive)* : Historiques vieux de 3 ans (accessibles en quelques heures, coût divisé par 10).

---

## 🛡️ 2. Souveraineté & Défense : Peut-on tout mettre dans le Cloud ?

En tant que membre de la Marine Nationale et du Ministère des Armées, la question de la souveraineté est centrale.

### A. Le risque géopolitique : Le *Cloud Act* américain (2018)
- Le **Cloud Act** (*Clarifying Lawful Overseas Use of Data Act*) permet aux agences de renseignement et à la justice américaines d'exiger des entreprises technologiques américaines (Microsoft, Amazon, Google) l'accès aux données stockées sur leurs serveurs, **même si ces serveurs sont situés physiquement en France ou en Europe**.
- *Conséquence pour la défense et les entreprises stratégiques :* On ne peut pas confier les plans des sous-marins nucléaires ou les positions tactiques des frégates à un cloud public américain standard.

### B. La réponse française : Le label SecNumCloud de l'ANSSI
L'**ANSSI** (Agence Nationale de la Sécurité des Systèmes d'Information) a créé le label de sécurité le plus exigeant au monde : **SecNumCloud**.
Pour être certifié SecNumCloud :
- Les données et métadonnées doivent être hébergées en Union Européenne.
- L'opérateur doit être protégé contre toute législation extraterritoriale (actionnariat européen, personnel habilité).
- Sécurité physique et logique de niveau militaire.

### C. La doctrine "Cloud au Centre" de l'État :
Pour les ministères et les services publics :
1. **Données peu sensibles / Grand public** (ex: météo marine ouverte, données de transport public) : Cloud public commercial (GCP, AWS, Azure, OVH).
2. **Données sensibles / Opérations de l'État** : Cloud de confiance certifié SecNumCloud (ex: **OVHcloud**, **3DS Outscale**, ou les co-entreprises souveraines **Bleu** [Orange/Capgemini/Microsoft] et **S3NS** [Thales/Google]).
3. **Données Secret Défense** : Cloud interne souverain et étanche ("On-Premise" militaire déconnecté d'Internet).

---

## 🧭 3. La Gouvernance des Données : De la Donnée brute à la Décision fiable

### La règle d'or : "Garbage In, Garbage Out"
Si vos données d'entrée sont fausses, incomplètes ou corrompues, votre meilleur algorithme d'Intelligence Artificielle prendra des décisions catastrophiques.

### Les 3 piliers de la gouvernance :
1. **Le Catalogue de Données (Data Catalog & Dictionnaire)** : Savoir ce qu'on possède. Que signifie la colonne `SOG` ? Quelle est son unité (nœuds marins ou km/h) ? Qui est le responsable de cette donnée ?
2. **La Traçabilité (Data Lineage)** : Être capable de remonter à la source. *"D'où provient ce chiffre de 45 navires en zone de pêche interdite ? Est-ce un signal AIS, un radar sémaphore ou un survol d'avion de patrouille ?"*
3. **Le Contrôle d'Accès (RBAC - Role Based Access Control)** : Le principe du **moindre privilège**. Un analyste débutant n'a pas accès aux données nominatives des officiers de bord ; un commandant de zone a la vue tactique globale.

---

## 🤖 4. Ouverture : L'IA Générative et le Futur du Cloud Data

Aujourd'hui, le Cloud permet d'interconnecter directement le Data Warehouse aux modèles d'IA (LLMs) :
- **Text-to-SQL** : L'officier de quart tape en français : *"Alerte-moi si un pétrolier a coupé son AIS pendant plus de 2 heures au large de Brest"*, et le Cloud génère et exécute automatiquement la requête SQL.
- **Synthèse automatisée** : Génération en un clic du rapport de situation maritime quotidien pour l'état-major.
