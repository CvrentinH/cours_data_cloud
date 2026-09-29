# Dictionnaire des Données – TP 2 (Missions & Logistique de la Flotte)

Ce jeu de données est **spécifique et exclusif au TP 2**. Il est **totalement indépendant du TP 1** afin de garantir une évaluation autonome et équitable pour chaque étudiant.

---

## 📋 Tableau descriptif des colonnes

| Nom de la colonne | Type Cloud (BigQuery) | Définition métier | Exemple de valeur |
| :--- | :--- | :--- | :--- |
| `id_mission` | `STRING` | Identifiant militaire unique de la mission opérationnelle | `MIS-2026-042` |
| `nom_batiment` | `STRING` | Nom du bâtiment de la Marine Nationale | `FS AQUITAINE`, `FS DIXMUDE`, `ABEILLE BOURBON` |
| `type_batiment` | `STRING` | Classe du navire de guerre ou de soutien | `Frégate multi-missions`, `Porte-hélicoptères amphibie`, `Patrouilleur` |
| `port_attache` | `STRING` | Base navale d'affectation | `Brest`, `Toulon`, `Cherbourg`, `Fort-de-France`, `Nouméa` |
| `zone_operationnelle`| `STRING` | Théâtre d'engagement maritime | `Méditerranée Occidentale`, `Atlantique Nord`, `Golfe de Guinée`, `Océan Indien` |
| `latitude_theatre` | `FLOAT` | Coordonnée géographique Nord de la zone d'opération | `41.5201` |
| `longitude_theatre`| `FLOAT` | Coordonnée géographique Est/Ouest de la zone d'opération | `6.2304` |
| `type_mission` | `STRING` | Nature de l'opération menée | `Surveillance ZEE & Souveraineté`, `Lutte contre le narcotrafic`, `Sauvetage en mer (SECMAR)` |
| `date_depart` | `DATE` | Date d'appareillage du port | `2026-03-15` |
| `duree_jours` | `INTEGER` | Nombre de jours de mer de la mission | `35` |
| `statut_mission` | `STRING` | État actuel du déploiement | `Terminée`, `En cours`, `En préparation` |
| `interventions_succes`| `INTEGER` | Nombre d'actions concrètes réussies (personnes secourues, saisies de stupéfiants, navires arraisonnés) | `6` |
| `carburant_consomme_tonnes` | `FLOAT` | Quantité de carburant consommée (en tonnes métriques) | `450.5` |
| `cout_total_euros` | `INTEGER` | Coût logistique global estimé de la mission (en €) | `850000` |
| `bilan_operationnel`| `STRING` | Appréciation du commandement à l'issue de l'opération | `Objectifs atteints à 100%`, `Opération active` |

---

## 🎯 Intérêt pour l'évaluation de Data Visualisation (TP 2)
1. **Multi-dimensionnel** : Permet de combiner des cartes mondiales (Antilles, Méditerranée, Océan Indien, Atlantique), des séries temporelles, des indicateurs financiers (coûts, carburant) et des KPIs de succès opérationnels.
2. **Autonomie totale** : Les étudiants importent ce fichier en 2 minutes au début de la Session 3. Même si un étudiant a rencontré des difficultés sur les requêtes SQL du TP 1, il démarre le TP 2 avec un score vierge et des données propres.
