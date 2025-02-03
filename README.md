# Automated Intern Group Assignment System Using Clustering Techniques for Nobel Learning PCB

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-v1.0+-orange.svg)](https://scikit-learn.org/)
[![MiniSom](https://img.shields.io/badge/MiniSom-v2.3-brightgreen.svg)](https://github.com/justheuristic/minisom)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Project Overview

This project addresses the challenge of optimally grouping incoming interns at Nobel Learning PCB to enhance their internship experience.  Feedback indicated that interns, particularly younger cohorts, highly value being grouped with peers, especially those from diverse backgrounds, and sharing common interests.  Manually creating these groups was a time-consuming and subjective process.

To address this, we developed an automated intern group assignment system leveraging Machine Learning clustering techniques. The system aims to create diverse and engaging intern groups by prioritizing the following factors:

* **Age Similarity (Primary):** Grouping interns within a close age range (ideally within 5 years) to foster peer connections and shared experiences.
* **Country Diversity (Secondary):** Maximizing the diversity of nationalities within each group to encourage cross-cultural interaction and broaden perspectives.
* **Starter Course Preferences (Tertiary):**  Considering interns' top three choices for starter courses (IWD, PIT, BIT) to align groups with shared learning interests.
* **Handling Missing Data:**  Robustly managing cases where interns haven't selected course preferences, ensuring all interns are assigned to a group.

The system was designed to be deployed with live data, providing a dynamic and efficient solution for intern group assignments.

## Methodology and Algorithms

This project explored several Machine Learning clustering algorithms to achieve optimal intern grouping. While Self-Organizing Maps (SOMs) were initially specified, we also investigated and implemented:

* **Self-Organizing Maps (SOM):**  Utilized for visualizing and clustering high-dimensional data in a lower-dimensional space, allowing for pattern recognition based on intern attributes.
* **Agglomerative Clustering:**  Explored for hierarchical clustering based on intern similarity, offering flexibility in cluster formation.
* **K-Means Clustering:**  Implemented for partitioning interns into a predefined number of clusters, optimized for minimizing within-cluster variance.
* **Weighted K-Means Clustering:**  Developed and employed to explicitly prioritize age similarity by assigning higher weights to age features during the clustering process. This allowed us to fine-tune the algorithm to meet the project's primary objective of age-based grouping.

**Weighting Strategy:**

The weighted K-Means model was crucial for achieving the desired grouping logic. The system prioritizes features as follows:

1. **Age:**  Given the highest weight to ensure age similarity within groups.
2. **Country:**  Assigned a secondary weight to encourage national diversity.
3. **Course Choice:**  Used as a tertiary factor, with lower weight, to consider course preferences when possible.

**Handling Missing Course Choices:**

For interns who did not specify course preferences, the system implemented a random assignment strategy to ensure complete group allocation while still optimizing for age and country criteria.

## Key Features

* **Automated Intern Group Assignment:**  Streamlines and automates the previously manual and subjective process of creating intern groups.
* **Prioritized Grouping Logic:**  Intelligently groups interns based on age similarity, country diversity, and course preferences, in order of importance.
* **Diversity-Focused:**  Actively promotes diversity within intern groups, fostering a richer and more inclusive internship experience.
* **Handles Incomplete Data:**  Gracefully manages cases with missing course preferences, ensuring all interns are assigned.
* **Deployed on AWS:**  Successfully deployed to Amazon Web Services (AWS) for immediate use with live data, demonstrating real-world applicability and scalability.
* **Exploration of Multiple Clustering Techniques:**  Showcases a comprehensive approach by evaluating and implementing various clustering algorithms, including SOM, Agglomerative Clustering, and K-Means, to identify the most effective solution.
* **Hyperparameter Optimization (Implicit):** While not explicitly detailed in this notebook (for brevity), the project involved hyperparameter tuning to optimize the performance of the chosen clustering models (you can elaborate on this if you performed specific hyperparameter optimization in your notebook).

## Results and Evaluation

The deployed system demonstrated a significant improvement in intern group formation, effectively grouping interns based on the prioritized criteria.  The model achieved the following error rates during testing:

* **Age Error Rate:** 7% (indicating high age similarity within groups)
* **Country Error Rate:** 11% (reflecting effective country diversity)
* **Course Choice Error Rate:** 16% (tertiary priority, acceptable trade-off for age and country optimization)
* **Overall Error Rate:** 11% (well within the acceptable threshold of 20%)

These results highlight the system's ability to create balanced and diverse intern groups while meeting the key objectives of age similarity and country diversity.  Feedback from initial deployments has been positive, indicating improved intern satisfaction with their group assignments.

## Technologies Used

* **Python:**  Primary programming language for development.
* **scikit-learn:**  Comprehensive Machine Learning library for clustering algorithms, preprocessing, and evaluation.
* **MiniSom:**  Library for implementing Self-Organizing Maps.
* **scipy:**  Library for scientific computing, including spatial distance calculations and optimization.
* **hyperopt:**  Library for hyperparameter optimization (if applicable - you can mention if you used it).
* **pandas:**  Data manipulation and analysis using DataFrames.
* **numpy:**  Numerical computing and array manipulation.
* **matplotlib:**  Data visualization and plotting.
* **Amazon Web Services (AWS):**  Cloud platform for deployment and hosting the system.

## Collaboration and Role

This project was a collaborative effort by a team of four interns at Nobel Learning PCB.  My primary role was focused on the **implementation and coding of the Machine Learning algorithms**.  This involved:

* **Translating algorithmic concepts into functional Python code.**
* **Developing and implementing the weighted K-Means clustering model with prioritized feature weighting.**
* **Exploring and coding alternative clustering algorithms (SOM, Agglomerative Clustering, K-Means).**
* **Assisting in algorithm selection and evaluation.**
* **Contributing to the overall codebase and notebook development.**

## Limitations and Future Work

* **Further Refinement of Weighting:** Exploring more sophisticated weighting schemes or dynamic weighting based on intern demographics or feedback.
* **Incorporating Additional Preferences:**  Expanding the model to consider other intern preferences or attributes beyond age, country, and course choice (e.g., skills, interests, time zones for virtual collaboration).
* **Dynamic Group Re-assignment:**  Investigating the feasibility of dynamic group adjustments or re-grouping based on intern feedback or project needs throughout the internship duration.
* **User Interface Development:** Creating a user-friendly interface for HR or program coordinators to manage and monitor intern group assignments.

## Disclaimer

**This Jupyter Notebook represents work done during an internship project at Nobel Learning PCB.**  The actual model and dataset used in the real-world application are proprietary and confidential to Nobel Learning PCB. This notebook is for demonstration purposes only and uses a simplified or potentially synthetic dataset to illustrate the methodology and techniques employed in the original project.  It does not include the trained model weights or any confidential information.

