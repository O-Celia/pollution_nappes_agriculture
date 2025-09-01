# Pollution des nappes phréatiques et agriculture intensive en France

## Analyse croisée : nitrates, pesticides et pratiques agricoles  
### Cas d’étude : Région Bretagne

---

## Objectifs du projet

Ce projet vise à analyser l’impact des pratiques agricoles intensives (engrais, pesticides) sur la pollution des nappes phréatiques en France. Il s’appuie sur un cas d’étude en Bretagne, région fortement concernée par ces enjeux environnementaux.

Les objectifs principaux sont :

- Identifier les **régions les plus contaminées** (nitrates, produits phytosanitaires)
- Analyser l’**évolution temporelle** des pollutions
- Étudier les **corrélations** entre usage agricole et contamination
- Localiser les **zones à risques** pour l’approvisionnement en eau potable
- Proposer un **modèle prédictif** des zones à surveiller
- Construire un **dashboard interactif** via Power BI

---

## Données utilisées

| Domaine | Source | Lien |
|--------|--------|------|
| Pollution des eaux souterraines | ADES / BRGM | https://ades.eaufrance.fr, https://data.ofb.fr/catalogue/data-eaufrance/ |
| Utilisation d’engrais | Agreste | https://agreste.agriculture.gouv.fr |
| Pesticides (ventes) | BNVD | https://ventes-produits-phytopharmaceutiques.eaufrance.fr/ |
| Surfaces agricoles / types de cultures | RPG (Registre parcellaire graphique) | https://data.gouv.fr |
| Données géographiques | Géoportail / IGN / DRAAF | https://www.geoportail.gouv.fr |

---

## Outils techniques

- **Langage** : Python 3.11
- **Librairies** : `pandas`, `geopandas`, `matplotlib`, `seaborn`, `scikit-learn`
- **Visualisation** : Power BI
- **IDE** : VSCode

---

## Étapes du projet

1. **Collecte et exploration des données**
2. **Nettoyage et préparation**
   - Harmonisation des noms de colonnes
   - Normalisation
   - Traitement des valeurs manquantes, doublons
   - Conversion des dates, formats géographiques
   - Création de GeoDataFrames pour la cartographie
3. **Analyse statistique**
   - Statistiques sur les concentrations en nitrates/pesticides
   - Moyennes, médianes, boxplots par zones
   - Histogrammes de distribution
   - Séries temporelles (évolution annuelle)
4. **Cartographie avec GeoPandas**
   - Localisation des nappes contaminées
   - Cartes des concentrations choroplèthes
   - Visualisation de l’évolution spatio-temporelle
   - Superposition avec zones agricoles
5. **Corrélations**
   - Regroupement des données par commune / département
   - Calcul de corrélations entre usage d’engrais/pesticides et pollution
   - Représentations croisées : scatterplots, heatmaps
6. **Modélisation : Identifier les zones à risque via un modèle de classification ou de régression**
   - Sélection des variables explicatives (usage agricole, climat, type de sol…)
   - Entraînement (Random Forest / KMeans)
   - Validation croisée
   - Cartographie des résultats (zones prédictivement à risque)
7. **Dashboard Power BI**
   - Cartes par concentration
   - Filtres dynamiques (année, région, type de culture)
   - Évolution dans le temps
   - Zones à risque
   - Intégration des résultats ML

---

## Structure du dépôt

```bash
pollution_nappes_agriculture/
├── data/                   # Données brutes (CSV, SHP, GeoJSON, etc.)
├── scripts/                # Scripts Python organisés par étape
│   ├── 01_clean_data.py
│   ├── 02_analyse_statistique.py
│   ├── 03_cartographie.py
│   ├── 04_correlation_agriculture.py
│   └── 05_modelisation_ml.py          
├── exports/                # Données nettoyées et visuels
├── dashboard/              # Fichier Power BI (.pbix)
├── images/                 # Cartes & visualisations générées
├── requirements.txt        # Liste des dépendances Python

└── README.md               # Ce fichier
