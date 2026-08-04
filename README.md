# Gaming Player Profile EDA and Clustering

This project explores a gaming player behavior dataset through exploratory data analysis (EDA) and unsupervised clustering using DBScan Algorithm (Density-Based Spatial Clustering of Applications with Noise). The goal is to understand player characteristics, identify behavioral patterns, and group players into meaningful segments based on engagement and gameplay activity.

## Project Overview

The workflow in this repository is implemented in [gaming_player_Eda_DBSCAN.ipynb](gaming_player_Eda_DBSCAN.ipynb) and uses a structured machine learning pipeline to:

- load and inspect the gaming dataset,
- clean and preprocess the data,
- engineer new features,
- visualize player behavior patterns,
- train clustering models,
- evaluate cluster quality,
- and profile the resulting player segments.

## What This Project Does

The notebook performs the following tasks:

1. Data loading from the Excel workbook [gaming_player_profile_datasets.xlsx](gaming_player_profile_datasets.xlsx).
2. Initial data inspection using shape, column summaries, and data types.
3. Data cleaning by removing missing values and duplicate rows.
4. Feature engineering such as:
   - Play time per session
   - Achievements per player level
5. Outlier handling using percentile-based clipping.
6. Data transformation and normalization, including log transformation for skewed features.
7. Feature scaling using StandardScaler.
8. Encoding of categorical variables with one-hot encoding.
9. Exploratory data analysis with visualizations such as:
   - age distribution,
   - gender and location distribution,
   - gameplay genre analysis,
   - engagement-related scatter plots,
   - correlations and pair plots.
10. Clustering using DBSCAN (Density-Based Spatial Clustering of Applications with Noise) and evaluation with:
   - k-distance graph for epsilon ($\epsilon$) determination,
   - hyperparameter grid search ($\epsilon$ vs min_samples) with Silhouette Score heatmap,
   - cluster distribution analysis and noise/outlier detection (label -1),
   - silhouette score, Davies-Bouldin index, and Calinski-Harabasz score on non-noise samples,
   - PCA-based 2D cluster visualization.
11. Cluster interpretation by summarizing average behavior across groups and using feature importance from a Random Forest classifier.

## Files in This Project

- [gaming_player_Eda_DBSCAN.ipynb](gaming_player_Eda_DBSCAN.ipynb) – main notebook containing the full analysis and modeling workflow.
- [gaming_player_profile_datasets.xlsx](gaming_player_profile_datasets.xlsx) – source dataset workbook used in the notebook.
- [README.md](README.md) – project documentation.

## Dataset Description

The dataset contains gaming-related player behavior information, including fields such as:

- player age,
- gender,
- location,
- game genre,
- game difficulty,
- play time,
- session frequency,
- session duration,
- player level,
- in-game purchases,
- achievements unlocked,
- and engagement level.

These features are used to build a richer player profile and explore the structure of the data.

## Tools and Libraries

This project uses Python with the following libraries:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- openpyxl

## Installation

If you are running the notebook locally, install the dependencies with:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl jupyter
```

## How to Run

1. Open [gaming_player_Eda_DBSCAN.ipynb](gaming_player_Eda_DBSCAN.ipynb) in Jupyter Notebook or VS Code.
2. Make sure the Excel file [gaming_player_profile_datasets.xlsx](gaming_player_profile_datasets.xlsx) is in the same folder.
3. Run the notebook cells in order.
4. Review the generated plots and clustering metrics to interpret the player segments.

## Expected Output

After running the notebook, you should be able to observe:

- a cleaned and transformed player dataset,
- descriptive visualizations of player behavior,
- cluster assignments and noise/outlier detection for player groups,
- evaluation metrics for clustering performance,
- and a profile summary of each cluster.

## Notes

This notebook is primarily focused on exploratory analysis and unsupervised density-based clustering for player segmentation. The implementation uses DBSCAN as the primary clustering algorithm, identifying dense player clusters and detecting anomalous player behavior as noise (-1).

## Potential Next Steps

You can extend this project by:

- comparing DBSCAN performance against K-Means or Hierarchical Clustering,
- experimenting with HDBSCAN for hierarchical density-based clustering,
- adding domain-specific feature engineering (e.g. churn risk indicators, monetisation metrics),
- or building an interactive dashboard for player segmentation analysis.
