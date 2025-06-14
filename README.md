# Country Segmentation for Development Aid Allocation

## A Clustering Analysis of Socio-Economic and Health Factors

This project aims to categorize countries based on socio-economic and health factors to identify nations that are in the direst need of development aid, particularly for child support initiatives. By applying unsupervised clustering techniques, we group countries with similar developmental profiles.

---

### Table of Contents
1. [Project Goal](#project-goal)
2. [Dataset](#dataset)
3. [Methodology](#methodology)
    - [Data Exploration and Processing](#data-exploration-and-processing)
    - [Clustering Algorithms](#clustering-algorithms)
4. [Key Findings](#key-findings)
5. [How to Use](#how-to-use)

---

<a id="project-goal"></a>
### 1. Project Goal

The primary goal of this project is to categorize countries to help international organizations and NGOs strategically allocate financial resources and prioritize countries requiring immediate attention for development aid, especially concerning child support.

<a id="dataset"></a>
### 2. Dataset

The project uses the `Country-data.csv` dataset, which includes the following socio-economic and health indicators for 167 countries:

*   **country:** Name of the country.
*   **child_mort:** Death of children under 5 years of age per 1000 live births.
*   **exports:** Exports of goods and services as a percentage of the Total GDP.
*   **health:** Total health spending as a percentage of the Total GDP.
*   **imports:** Imports of goods and services as a percentage of the Total GDP.
*   **income:** Net income per person.
*   **inflation:** Consumer price inflation.
*   **life_expec:** The average number of years a newborn child would live if current mortality patterns remained the same.
*   **total_fer:** The number of children that would be born to each woman if current age-fertility rates remained the same.
*   **gdpp:** The GDP per capita.

<a id="methodology"></a>
### 3. Methodology

The project follows these main steps:

<a id="data-exploration-and-processing"></a>
#### Data Exploration and Processing
*   **Initial Analysis:** Loaded the dataset, examined its structure, data types, and basic statistics. Checked for missing values and duplicates.
*   **Geo-visualization:** Visualized the global distribution of key indicators like GDP per capita.
*   **Feature Distributions:** Analyzed the distribution of each numerical feature using histograms and box plots to identify skewness and outliers.
*   **Correlation Analysis:** Examined the relationships between different features using a correlation heatmap.
*   **Data Preprocessing:**
    *   **Outlier Capping:** Mitigated the influence of extreme outliers by capping numerical features at their 1st and 99th percentiles.
    *   **Feature Scaling:** Scaled numerical features using `StandardScaler` to have zero mean and unit variance.
    *   **Dimensionality Reduction:** Applied Principal Component Analysis (PCA) to reduce data dimensionality to 2 components for visualization.

<a id="clustering-algorithms"></a>
#### Clustering Algorithms
Two main clustering algorithms were employed:

1.  **K-Means Clustering:**
    *   Determined the optimal number of clusters (K) using the Elbow Method, Silhouette Score, and Davies-Bouldin Index. An optimal K of 3 was chosen.
    *   Implemented K-Means clustering and visualized the resulting clusters on the 2D PCA plot and a world map.
    *   Clusters were profiled and labeled as 'Low Development', 'Medium Development', and 'High Development'.

2.  **Hierarchical Clustering:**
    *   Generated a dendrogram to visualize the cluster hierarchy, which also suggested 3 clusters.
    *   Implemented Agglomerative Hierarchical Clustering and visualized the clusters.

<a id="key-findings"></a>
### 4. Key Findings

*   K-Means clustering (with K=3) effectively segmented countries into three distinct development categories:
    *   **Low Development Cluster:** Characterized by high child mortality, high total fertility rates, low income, low GDP per capita, and lower life expectancy. These countries are identified as being in the most dire need of aid.
    *   **Medium Development Cluster:** Countries with socio-economic and health indicators falling between the low and high development groups.
    *   **High Development Cluster:** Countries with low child mortality, low total fertility rates, high income, high GDP per capita, and high life expectancy.
*   The 'Low Development' cluster identified by K-Means consists of 47 countries that are primary candidates for development aid.
*   Hierarchical clustering also suggested three clusters, providing a comparative perspective.

<a id="how-to-use"></a>
### 5. How to Use

1.  Ensure you have Python installed with necessary libraries: pandas, numpy, matplotlib, seaborn, scikit-learn, and plotly.
2.  Place the `Country-data.csv` file in the same directory as the notebook.
3.  Open and run the `countries_clustering.ipynb` Jupyter Notebook to see the detailed analysis, code, and visualizations.

The notebook provides a step-by-step walkthrough of the data analysis, preprocessing, clustering, and interpretation of results.
