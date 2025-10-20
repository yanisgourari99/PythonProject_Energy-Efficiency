# Energy Load Prediction

## Description
Ce projet utilise des modèles de régression pour prédire la **charge de chauffage** (`heating_load`) et la **charge de refroidissement** (`cooling_load`) des bâtiments à partir de leurs caractéristiques géométriques et physiques.  
Le workflow comprend l'**analyse exploratoire (EDA)**, la **préparation des données**, la **modélisation avec Linear, Ridge et Lasso Regression**, et la **visualisation des performances**.

## Dataset
Le dataset utilisé est `ENB2012_data.csv` (Energy Efficiency Data Set).  
Il contient des variables comme :
- `relative_compactness`
- `surface_area`
- `wall_area`
- `roof_area`
- `overall_height`
- `orientation`
- `glazing_area`
- `glazing_area_distribution`
- `heating_load`
- `cooling_load`

## Étapes du projet
1. **Importation et nettoyage des données**
   - Suppression des colonnes inutiles
   - Gestion des valeurs manquantes
   - Renommage des colonnes
2. **Analyse exploratoire**
   - Statistiques descriptives
   - Corrélations entre features et cibles
   - Histogrammes et boxplots pour détecter les distributions et outliers
3. **Préparation des données**
   - Séparation features (`X`) et targets (`Y`)
   - Standardisation des variables
   - Split en train/test (80%/20%)
4. **Modélisation**
   - Linear Regression
   - Ridge Regression
   - Lasso Regression
   - Évaluation avec R² et MSE
5. **Visualisation**
   - Comparaison des modèles (barplots pour R² et MSE)
   - Comparaison des valeurs réelles vs prédites (scatterplots)

## Résultats
- Les modèles linéaires simples ont de bonnes performances, mais Ridge et Lasso aident à réduire l'overfitting.
- R² pour `heating_load` : ~0.91 (Linear), ~0.91 (Ridge/Lasso)
- R² pour `cooling_load` : ~0.89 (Linear), ~0.88 (Ridge/Lasso)

## Interprétation
- Les caractéristiques géométriques et physiques du bâtiment sont fortement corrélées avec la consommation énergétique.
- L'approche MultiOutputRegression permet de prédire simultanément `heating_load` et `cooling_load`.
- Les visualisations montrent que les prédictions suivent bien la tendance des valeurs réelles.

pip install -r requirements.txt  # si tu crées ce fichier avec les bibliothèques
python energy_load_prediction.py  # ou le notebook
