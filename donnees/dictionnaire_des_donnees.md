# Dictionnaire des Données Maritimes (Dataset AIS)

Ce jeu de données représente un extrait de flux **AIS (Automatic Identification System)** de navires naviguant dans les zones d'intérêt maritime françaises et européennes (Manche, Iroise/Brest, Golfe de Gascogne, Méditerranée/Toulon).

---

## 📋 Tableau descriptif des colonnes

| Nom de la colonne | Type Cloud (BigQuery) | Définition métier | Exemple de valeur |
| :--- | :--- | :--- | :--- |
| `timestamp` | `TIMESTAMP` ou `STRING` | Date et heure précise d'émission du signal AIS | `2026-09-28 08:34:12` |
| `mmsi` | `INTEGER` | Maritime Mobile Service Identity (identifiant unique radio du navire, 9 chiffres) | `227189402` |
| `nom_navire` | `STRING` | Nom de baptême du navire | `CMA CGM ANTOINE`, `FS CHEVALIER PAUL` |
| `type_navire` | `STRING` | Catégorie du navire | `Cargo`, `Pétrolier`, `Militaire`, `Pêcheur`, `Passagers`, `Remorqueur` |
| `pavillon` | `STRING` | Pays d'immatriculation du navire (État du pavillon) | `France`, `Panama`, `Malte`, `Russie`, `Chine` |
| `zone_maritime` | `STRING` | Zone géographique d'observation | `Manche / Pas-de-Calais`, `Mer d Iroise / Brest`, `Méditerranée / Rade de Toulon` |
| `latitude` | `FLOAT` | Coordonnée géographique Nord (degré décimal) | `49.48201` |
| `longitude` | `FLOAT` | Coordonnée géographique Est/Ouest (degré décimal) | `-4.48120` |
| `vitesse_noeuds` | `FLOAT` | SOG (*Speed Over Ground*) : vitesse réelle par rapport au fond marin, en nœuds (1 nœud = 1,852 km/h) | `18.5` |
| `cap_degres` | `INTEGER` | COG (*Course Over Ground*) : cap suivi par le navire en degrés (de 0° à 359°) | `245` |
| `statut_navigation` | `STRING` | Statut déclaré par le bord | `En route au moteur`, `Au mouillage`, `Amarré` |
| `destination` | `STRING` | Port d'escale annoncé | `Le Havre`, `Rotterdam`, `Marseille`, `Brest` |
| `longueur_metres` | `FLOAT` | Longueur hors-tout du navire en mètres | `399.0` |
| `tirant_d_eau_metres`| `FLOAT` | Hauteur de la partie immergée du navire en mètres | `15.5` |
| `alerte_anomalie` | `INTEGER` | Indicateur de détection automatique d'anomalie (`0` = navigation normale, `1` = comportement suspect) | `0` ou `1` |
| `type_anomalie` | `STRING` | Motif de l'alerte de surveillance maritime | `Normale`, `Arret anormal en chenal de navigation`, `Stationnement suspect pres de base navale` |

---

## 🔍 Pourquoi ce jeu de données est idéal pour vos étudiants ?
1. **Intuitif** : Tout le monde visualise un bateau, son port de départ, sa destination et sa vitesse.
2. **Double enjeu civil & défense** : Permet à la fois de faire de la logistique commerciale (porte-conteneurs en route pour Le Havre) et de la surveillance régalienne (sécurité des approches de Brest et Toulon).
3. **Pédagogique pour le Cloud** : Taille optimale pour être importé en 15 secondes dans Google BigQuery Sandbox sans le moindre bug.
