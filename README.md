# TP 2 — Préparation des données avec Python

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/Pandas-Latest-green.svg)](https://pandas.pydata.org/)
[![Tableau](https://img.shields.io/badge/Tableau-Public-orange.svg)](https://public.tableau.com/)

> Projet de nettoyage et préparation de données sur les catastrophes naturelles mondiales  
> **Auteur** : ANTON NELCON Steve - M1 IBD Paris 8
---

##  Description

Ce projet présente un  nettoyage et de préparation de données pour l'analyse de catastrophes naturelles à travers le monde. Le notebook Python traite un dataset brut contenant des informations sur divers types de catastrophes (inondations, tremblements de terre, épidémies, etc.) et le transforme en un dataset propre et exploitable pour la visualisation dans Tableau.

---

##  Objectifs

- Explorer et diagnostiquer les problèmes de qualité des données
- Nettoyer et standardiser les données (valeurs manquantes, doublons, incohérences)
- Enrichir le dataset avec de nouvelles variables calculées
- Préparer les données pour une visualisation efficace dans Tableau
- Garantir la cohérence et la fiabilité des données

##  Dataset

### Source
- **Fichier d'entrée** : `catnat_dirty.csv` (17 510 lignes)
- **Fichier de sortie** : `catnat_clean.csv` (16 949 lignes après nettoyage)

### Variables principales
- **Identifiants** : DisNo., Country, Region, Subregion
- **Type de catastrophe** : Disaster Type, Disaster Subtype, Disaster Subgroup
- **Temporalité** : Start Year, Start Month
- **Impact humain** : Total Deaths, No. Injured, Total Affected, No. Homeless
- **Impact économique** : Total Damage ('000 US$)
- **Localisation** : Latitude, Longitude
- **Magnitude** : Pour les événements sismiques

##  Technologies utilisées

- **Python 3.9+**
- **Pandas** : Manipulation et nettoyage des données
- **NumPy** : Calculs numériques
- **Jupyter Notebook** : Environnement de développement
- **Tableau Public** : Visualisation des données

---


##  Exercices réalisés

### Exercice 1 — Exploration et diagnostic
- Analyse de la structure du dataset (shape, dtypes, info)
- Détection des valeurs manquantes
- Identification des doublons
- Analyse des valeurs aberrantes

### Exercice 2 — Gestion des valeurs manquantes
- Remplacement des NaN dans `Total Deaths` par 0
- Imputation des valeurs manquantes dans `Event_Name` par "Non nommé"
- Stratégies de gestion pour les autres colonnes

### Exercice 3 — Suppression des doublons
- Identification et suppression des lignes dupliquées (561 doublons trouvés)
- Vérification post-nettoyage

### Exercice 4 — Harmonisation des types de catastrophes
- Standardisation de la casse (majuscules/minuscules)
- Correction des incohérences (ex: "storm" → "Storm")

### Exercice 5 — Correction des noms de pays
- Uniformisation des noms (ex: "USA" → "United States Of America")
- Correction des variantes orthographiques

### Exercice 6 — Nettoyage des régions
- Standardisation des noms de régions
- Consolidation des variantes (ex: "Asia", "asia" → "Asia")

### Exercice 7 — Enrichissement des données
- Création de la variable `Decennie` (décennie de l'événement)
- Création de la variable booléenne `Has_Deaths` (présence/absence de décès)

### Exercice 8 — Renommage et export
- Renommage des colonnes pour plus de clarté
- Suppression des espaces et caractères spéciaux
- Export vers `catnat_clean.csv`

### Exercice 9 — Vérification dans Tableau
- Import du fichier nettoyé dans Tableau Public
- Validation des types de données
- Création de visualisations de contrôle qualité
- Vérification de la géolocalisation des pays

---
##  Utilisation

### Prérequis
```bash
pip install pandas numpy jupyter
```

### Exécution
1. Cloner le repository
2. Placer le fichier `catnat_dirty.csv` dans le répertoire de travail
3. Ouvrir le notebook Jupyter :
```bash
jupyter notebook TP2.ipynb
```
4. Exécuter toutes les cellules séquentiellement
5. Récupérer le fichier `catnat_clean.csv` généré

##  Résultats

### Statistiques du nettoyage
- **Lignes initiales** : 17 510
- **Doublons supprimés** : 561
- **Lignes finales** : 16 949
- **Taux de conservation** : ~96.8%

### Qualité des données
- Types de données cohérents et adaptés
- Valeurs manquantes documentées et gérées
- Doublons éliminés
- Nomenclature standardisée
- Variables enrichies pour l'analyse

### Nouvelles variables
- `Decennie` : Permet l'analyse temporelle par décennie
- `Has_Deaths` : Facilite le filtrage des événements mortels

##  Visualisations

Consultez les visualisations interactives créées avec le dataset nettoyé :

**[Tableau Public Dashboard](https://public.tableau.com/app/profile/steve.anton.nelcon/viz/TP1-M1IBD/Catastrophe?showOnboarding=true)**

Les visualisations incluent :
- Distribution des types de catastrophes
- Impact par région géographique
- Cartographie mondiale des événements
- Évolution temporelle des catastrophes

##  Structure du projet

```
.
├── TP2.ipynb              # Notebook principal avec tous les exercices
├── catnat_dirty.csv       # Dataset brut (non inclus)
├── catnat_clean.csv       # Dataset nettoyé (généré)
└── README.md              # Ce fichier
```

##  Contexte académique

Ce travail pratique fait partie du cursus de Master 1 Informatique et  Data à l'Université Paris 8. Il illustre les compétences en :
- Nettoyage et préparation de données
- Manipulation de DataFrames avec Pandas
- Gestion de la qualité des données
- Préparation pour la visualisation
- Documentation et reproductibilité

##  Licence

Ce projet est réalisé dans un cadre académique.

##  Contact

**ANTON NELCON Steve**  
---

*Dernière mise à jour : 13 Février 2025*
