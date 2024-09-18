
# Advanced Spatio-Temporal Trajectory Analysis Using Dynamic DBSCAN and Poisson Model for Bird Movement Tracking

## Overview

This project develops an advanced DBSCAN-based algorithm designed to identify and classify nonlinear spatial-temporal trajectories, with a focus on tracking bird movements. It introduces a dynamic sliding window approach to optimize clustering performance and enhance tracking accuracy using radar-based GIS data.

The algorithm is tested across four bird species datasets in three distinct settings:
1. **Dynamic EPS with Overlap**
2. **Static EPS with Overlap**
3. **Static EPS without Overlap (regular DBSCAN)**

The results show that the dynamic EPS with overlap outperforms other settings, particularly in clustering quality, species classification, and Poisson-based object estimation.

## Key Features

- **Sliding Window Dynamic DBSCAN**: Enhances cluster formation by dynamically adjusting the epsilon value based on local density, using the median Haversine distance as the baseline.
- **Poisson Model**: Utilized for estimating the number of objects within clusters, improving cluster purity and reducing misclassification rates.
- **Random Forest Classifier**: Evaluates clustering results by using kinematic features detached from space and time, allowing for unbiased species classification.

## Structure

- **2_clusters_with_kinematic_features_and_species_check.csv**: Kinematic features and species labels for cluster 2.
- **3clusters_with_kinematic_features_and_species_check.csv**: Kinematic features and species labels for cluster 3.
- **4_4Number of Records in Sliding Windows and Overlap Windows.png**: Number of records across sliding and overlap windows.
- **4_distributions_delta_epoch.png**: Time differences (delta epoch) distribution between consecutive points.
- **aggregated_kinematic_features_matching_percentages.csv**: Aggregated percentages of kinematic feature matches across species.
- **aggregated_kinematic_features_matching_percentages_with_adjusted_overall.csv**: Adjusted match percentages with overall success metric.
- **aggregated_kinematic_features_matching_percentages_with_overall.csv**: Similar to the previous file but with different calculations for overall success.
- **classification**: Directory containing classification results and outputs.
- **Classification - compare 3 settings.ipynb**: Notebook comparing classification results across 3 settings.
- **clusters1_static_no_overlap_with_kinematic_features.csv**, **clusters1_static_with_kinematic_features.csv**, **clusters1_with_kinematic_features.csv**: Cluster data for dataset 1 across different settings.
- **clusters2_static_no_overlap_with_kinematic_features.csv**, **clusters2_static_with_kinematic_features.csv**, **clusters2_with_kinematic_features.csv**: Cluster data for dataset 2 across different settings.
- **clusters3_static_no_overlap_with_kinematic_features.csv**, **clusters3_static_with_kinematic_features.csv**, **clusters3_with_kinematic_features.csv**: Cluster data for dataset 3 across different settings.
- **clusters4_static_no_overlap_with_kinematic_features.csv**, **clusters4_static_with_kinematic_features.csv**, **clusters4_with_kinematic_features.csv**: Cluster data for dataset 4 across different settings.
- **clusters_file1.csv**, **clusters_file1_no_overlap_static_eps.csv**, **clusters_file1_with_overlap_static_eps.csv**: Raw cluster data for dataset 1 across different settings.
- **clusters_file2.csv**, **clusters_file2_no_overlap_static_eps.csv**, **clusters_file2_with_overlap_static_eps.csv**: Raw cluster data for dataset 2.
- **clusters_file3.csv**, **clusters_file3_no_overlap_static_eps.csv**, **clusters_file3_with_overlap_static_eps.csv**: Raw cluster data for dataset 3.
- **clusters_file4.csv**, **clusters_file4_no_overlap_static_eps.csv**, **clusters_file4_with_overlap_static_eps.csv**: Raw cluster data for dataset 4.
- **combined_clusters_with_kinematic_features.csv**: Combined clusters with kinematic features across all datasets.
- **combined_kinematics_distributions.png**: Distribution of kinematic features across datasets.
- **Common_Kestrel_sample.csv**: Sample dataset for common kestrels.
- **Data Exploration-hdbscan-*.ipynb**: Notebooks exploring datasets using HDBSCAN.
- **different_values**: Directory storing results of various parameter values tested.
- **full_data**: Directory containing the full dataset.
- **Herring_gulls_sample.csv**: Sample dataset for herring gulls.
- **homing_pigeons_sample.csv**: Sample dataset for homing pigeons.
- **kinematic_features_matching_percentages_all_species.csv**: Kinematic feature match percentages across species.
- **median_distance_between_points.png**: Visualization of median distances between points across datasets.
- **Poisson Regression.ipynb**: Notebook demonstrating the Poisson regression application for cluster estimation.
- **poisson_regression_summary.csv**: Summary of Poisson regression results.
- **white_storks_sample.csv**: Sample dataset for white storks.

## Usage

1. Clone the repository to your local machine:
   ```
   git clone <repository-url>
   cd <repository-name>
   ```

2. Explore the provided Jupyter notebooks to run the analyses or classification tasks.

3. Modify the parameters in the clustering algorithm as needed to test the effects of different epsilon values or window sizes.

## Results Summary

The dynamic epsilon with overlap configuration was the most successful in identifying clusters that closely matched known bird species movement patterns. It reduced the number of orphan clusters and improved clustering metrics such as Silhouette Score, Davies-Bouldin Index, and Calinski-Harabasz Score. Additionally, the kinematic features extracted from the clusters allowed for a high degree of accuracy in species classification.

## Future Work

Future research could focus on refining the algorithm by incorporating additional data sources, such as weather data, to further enhance clustering performance. Additional suggestions include extending the analysis to other datasets, applying probabilistic models to reduce orphan clusters, and expanding the scope to include UAV (Unmanned Aerial Vehicle) tracking data.
