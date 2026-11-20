# Country Development Clustering

Grouping **167 countries** into development levels using 9 socio-economic and health indicators (child mortality, income, GDP per capita, life expectancy, fertility, trade, health spending, inflation). Groups like these can help a humanitarian organization see which countries need support most.

## What I did
- **Exploration:** correlation heatmaps and scatter plots of strongly related variables
- **Preprocessing:** checked missing values, kept outliers on purpose (they are real countries, not errors), standardized all features
- **K-Means:** compared k = 2…10 with the elbow method and silhouette score
- **Hierarchical clustering (Ward):** dendrogram, chose a cut height, compared the groups with K-Means
- **PCA:** number of components needed for 80% / 95% of the variance, then K-Means on the reduced data

## Results
- **k = 5** clusters, with the highest silhouette score at k = 5
- Hierarchical clustering also gives 5 clusters with very similar groupings
- **4 components** keep ≥ 80% of the variance, **5 components** keep ≥ 95%
- The clusters separate low-income / high child-mortality countries from high-income / high life-expectancy countries, with intermediate groups in between

## Tech
Python · pandas · NumPy · scikit-learn · SciPy · matplotlib · seaborn

## Data
[Unsupervised Learning on Country Data (Kaggle)](https://www.kaggle.com/datasets/rohan0301/unsupervised-learning-on-country-data). Save the CSV as `data/country_data.csv`.

## Run
```bash
pip install -r requirements.txt
jupyter notebook country_clustering.ipynb
```

*Developed as part of a data science course (AIN214, Hacettepe University, Fall 2025).*
