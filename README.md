# US-Air-Hazards
Uncovering Hidden Air Pollution Patterns Across the United States

An Unsupervised Machine Learning Approach Using PCA and Clustering

## Overview

Air pollution is a persistent public health and environmental challenge in the United States, with pollution levels and sources varying widely across regions. Raw air quality measurements alone are often insufficient for understanding broader patterns or identifying why certain areas experience higher pollution than others. This project applies unsupervised machine learning techniques to transform large-scale pollution data into interpretable regional patterns that explain both pollution severity and its underlying causes.

This project was developed as part of the Discovering the World with Data course and demonstrates end-to-end data science skills, including data cleaning, feature engineering, dimensionality reduction, clustering, evaluation, and interpretation of results.

## Problem Statement

Different U.S. cities experience varying levels of air pollution due to distinct combinations of traffic density, industrial activity, geography, and environmental conditions. However, policymakers, public health officials, and residents often lack a clear, data-driven understanding of how cities compare to one another in terms of pollution profiles and what factors are driving those differences. This project addresses the need to systematically identify groups of U.S. cities with similar air pollution characteristics and explain why pollution is high or low in each group.

## Data

The analysis uses the U.S. Pollution Dataset (2000–2016), sourced from the U.S. Environmental Protection Agency (EPA). The dataset contains millions of daily air quality measurements across U.S. cities and monitoring stations. For this project, the data was cleaned, filtered, and aggregated to the city level.

The final dataset includes six pollutant features used as model inputs:
PM2.5, PM10, Nitrogen Dioxide (NO₂), Sulfur Dioxide (SO₂), Carbon Monoxide (CO), and Ozone (O₃).
Each city is represented by the average concentration of these pollutants over the study period, resulting in a compact and consistent feature matrix suitable for unsupervised learning.

## Approach

The project follows a structured machine learning workflow. First, extensive data cleaning was performed to handle missing values, remove irrelevant columns, and standardize pollutant measurements. Median imputation was used to preserve realistic pollutant distributions, and all features were normalized using z-score standardization to ensure fair comparison across pollutants with different units and scales.

To reduce complexity and improve interpretability, Principal Component Analysis (PCA) was applied to the standardized pollutant data. PCA transformed the six correlated pollution variables into a smaller set of uncorrelated components that capture the majority of variation across cities. The first two principal components alone explained approximately 75% of the total variance, enabling meaningful visualization of pollution patterns.

Next, K-Means clustering was used to group cities based on similarity in their pollution profiles. The optimal number of clusters was determined using the Elbow Method and Silhouette Score, ensuring well-separated and interpretable clusters. Hierarchical clustering was also performed as a validation step to confirm the stability of the identified groups.

## Results

The analysis revealed four distinct pollution clusters across U.S. cities. These clusters correspond to meaningful real-world pollution patterns rather than arbitrary groupings. One cluster was dominated by particulate matter (PM2.5 and PM10), commonly associated with wildfire-prone regions and geographic basins. Another cluster showed high NO₂ and CO levels, characteristic of dense, traffic-heavy urban centers. A third cluster exhibited elevated SO₂ levels, reflecting industrial and manufacturing zones. The final cluster consisted of cities with consistently low pollution across all measured pollutants, representing cleaner air regions.
<img width="500" height="500" alt="Screenshot 2026-01-02 at 9 33 26 AM" src="https://github.com/user-attachments/assets/759baec4-16ca-4fd2-bb03-12c0e2f5355c" />
<img width="500" height="500" alt="Screenshot 2025-12-03 at 11 43 41 AM" src="https://github.com/user-attachments/assets/ea94c77b-fa48-4e1f-a67c-0ef852b199c1" />
<img width="500" height="500" alt="Screenshot 2025-12-03 at 11 53 11 AM" src="https://github.com/user-attachments/assets/51ad6026-dcd5-473b-b325-ea372ca57492" />

PCA visualizations showed clear separation between clusters, confirming that pollution patterns vary systematically across cities. Quantitative validation metrics, including a strong silhouette score and a low Davies–Bouldin Index, indicated compact and well-defined clusters. Importantly, the results explain not only where pollution is concentrated, but also why different cities experience different pollution profiles.

<img width="500" height="500" alt="Screenshot 2026-01-02 at 9 35 14 AM" src="https://github.com/user-attachments/assets/bc2e9b55-0756-48c2-8d30-c0cd6dc512e1" />

<img width="500" height="500" alt="Screenshot 2026-01-02 at 9 36 18 AM" src="https://github.com/user-attachments/assets/10c23e20-a41c-4abd-9d86-8bdadd225d97" />

<img width="700" height="513" alt="Screenshot 2026-01-02 at 9 37 25 AM" src="https://github.com/user-attachments/assets/486290e2-cc2b-4254-bd2c-d5b01ba47dd8" />


## Impact and Usefulness

This project demonstrates how unsupervised machine learning can convert complex environmental data into actionable insights. By grouping cities based on pollution behavior rather than geography alone, the results enable targeted public health interventions, pollution mitigation strategies, and policy decisions. Healthcare systems can anticipate region-specific health risks, and policymakers can design interventions tailored to dominant pollution sources such as traffic, industry, or environmental conditions.

## Limitations

The analysis relies on aggregated historical data and does not explicitly model temporal changes or seasonal effects. Additional explanatory variables such as traffic volume, weather patterns, wildfire occurrences, and socioeconomic factors were not included but could further enhance interpretability. Despite these limitations, the clustering results remain robust and informative for regional pollution analysis.

## Future Work

Future extensions of this project could integrate weather and traffic data, apply deep learning models for pollution forecasting, and analyze temporal shifts in pollution clusters over time. Incorporating real-time EPA feeds and health outcome data could further strengthen the public health relevance of the findings.

## Repository Contents

This repository includes the full data processing pipeline, machine learning code, and visualizations. The Jupyter notebook contains all steps from raw data ingestion to final clustering results, ensuring full reproducibility of the analysis.

## Where to See the Project

All analysis and visualizations are available in the Jupyter Notebook included in this repository.
