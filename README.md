# Korean Drama Dominance vs. Thai and Japanese Drama
## Data Cleaning, Transformation, and Preparation for Weka

## Project Overview

This project focuses on the **extraction, cleaning, transformation, and preparation of data** from the dataset *“Korean Drama Dominance vs. Thai and Japanese Drama”* in order to feed Machine Learning algorithms implemented in **Weka**. The dataset contains information about dramas from **South Korea, Japan, and Thailand**, including structural attributes, genres, audience reception, and popularity metrics.

The project was initially developed as part of an academic integrative assignment. However, it is designed following **Data Science best practices**, making it suitable as a **portfolio project** and as supporting material for **graduate-level applications in Data Science**.

Rather than focusing on model performance alone, this repository emphasizes the **ELT (Extract, Load, Transform) stage of the Data Science lifecycle**, highlighting how raw data is systematically prepared to meet the assumptions and input requirements of different Machine Learning techniques.

## Business Context and Analytical Perspective

For the purpose of this project, the role of a company specialized in the entertainment industry is assumed. This company seeks to enter the **East and Southeast Asian drama market** and aims to identify which characteristics of audiovisual content are most strongly associated with **audience engagement and market success**.

Key Performance Indicators (KPIs) considered in this analysis include popularity level, average user score, number of viewers, and content duration, measured through episode count and episode length. These indicators allow the organization to evaluate both **commercial performance** and **audience reception** across different countries and genres.

Based on this context, the analytical objective is to determine which combinations of attributes are most significantly associated with **high-performing dramas**, and to evaluate whether these patterns differ between **Korean, Japanese, and Thai productions**.

## Analytical Techniques

### Classification

Classification is used to answer the following question:

**Based on the characteristics of a drama, can we predict whether it will have high or low popularity?**

- **Algorithm:** Logistic Regression (Weka)
- **Target attribute:**
  - Popularity (encoded as *High* and *Low*)
- **Input attributes:**
  - Genre (multi-label, encoded)
  - Number of episodes
  - Average episode duration
  - Content rating
  - Country of origin (encoded)

The goal is to build a supervised learning dataset that allows Weka to learn patterns linking structural and categorical attributes to popularity outcomes.

### Clustering

Clustering is applied to identify patterns that are not immediately visible by grouping dramas based on similarities in their structural and reception-related attributes. The objective is to discover **natural groupings** that may represent different drama formats or audience segments across regions.

- **Algorithm:** k-means (Weka)
- **Input attributes:**
  - Country of origin (encoded)
  - Number of episodes
  - Average episode duration
  - Average user score
  - Genre (encoded)

This technique is used in an exploratory manner to reveal latent structures within the data without predefined labels.

### Association

Association rule mining is used to explore relationships between content characteristics and popularity, addressing questions such as:

**Which genres and countries of origin are most frequently associated with high popularity?**

- **Algorithm:** Apriori (Weka)
- **Input attributes:**
  - Genre
  - Country of origin
  - Popularity (High / Low)

The focus of this technique is to uncover frequent and interpretable patterns that link categorical attributes to performance outcomes.

## Project Structure and Roadmap

The repository is organized around **separate preprocessing pipelines**, one for each Machine Learning technique. Each notebook produces a clean dataset specifically designed to meet the assumptions and input requirements of the corresponding algorithm in Weka.

### 1. Dataset Integration

**Notebook:** `01_merge_datasets.ipynb`

### 2. Data Cleaning for Classification

**Notebook:** `02_clean_classification_data.ipynb`

### 3. Data Cleaning for Clustering

**Notebook:** `03_clean_clustering_data.ipynb`

### 4. Data Cleaning for Association

**Notebook:** `04_clean_association_data.ipynb`

## Project Status

This repository currently focuses on the **ELT and data preparation stages** of the Data Science workflow. Model training, evaluation, and interpretation using Weka constitute a subsequent phase of the project.

Future updates may include:
- Weka experiment configurations
- Model evaluation summaries
- Screenshots and interpretations of results
- Business-oriented insights derived from classification, clustering, and association outputs

## Tools and Technologies

- Python (pandas, scikitlearn) for data cleaning and feature engineering
- Jupyter Notebook for reproducible preprocessing workflows  
- Weka for classification, clustering, and association rule mining  

## Final Remarks

This project highlights the importance of tailoring data preprocessing to the specific requirements of each Machine Learning technique. By separating the cleaning and transformation steps for classification, clustering and association, the project ensures **methodological clarity**, **reproducibility**, and a strong connection between **business objectives** and **data-driven decision-making**.
