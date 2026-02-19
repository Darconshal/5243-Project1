# 5243-Project1：Spotify Songs Analysis

## Overview
This project focuses on acquiring, cleaning, preprocessing, and analyzing a large-scale Spotify songs dataset with Billboard Hot 100 hit information. The objective is to explore how musical audio features differ between hit and non-hit songs and to prepare the dataset for future predictive modeling.

The full workflow includes:

- Data acquisition from kaggle
- Data cleaning and inconsistency handling
- Exploratory Data Analysis (EDA)
- Data preprocessing and feature engineering

All steps are implemented in the Jupyter notebook:

Project1_Clean+EDA.ipynb

---
## How to Run the Code

### Requirements

Python 3.9 or higher

Required packages:

- pandas
- numpy
- matplotlib
- seaborn

### Running the Notebook

Step 1: Open Jupyter Notebook

Step 2: Open the notebook file

Project1_Clean+EDA.ipynb

Step 3: Run all cells

Run → Run All Cells

---
## Research Question

Question: How do Spotify audio features differ between hit and non-hit songs, and how have these patterns changed over time?

## Dataset Description

The dataset was obtained from Kaggle and contains both Spotify audio features and Billboard hit information.

Each observation represents one song and includes:

Audio features:
- danceability
- energy
- loudness
- tempo
- valence
- acousticness
- instrumentalness
- key
- mode
- time_signature

Metadata:
- year
- artist identifiers
- track identifiers

Target variable:
- hit (1 = Billboard Hot 100 hit, 0 = non-hit)

Initial dataset size:
- 455,908 observations
- 36 variables

The hit variable serves as a proxy for commercial success.

---

## Data Cleaning and Handling Inconsistencies

The following cleaning steps were performed:

Identifier validation:
- Checked uniqueness of track IDs
- Removed invalid duplicated IDs
- Generated pseudo-IDs for observations with missing identifiers to preserve valid records

Missing value handling:
- Removed variables with more than 95% missing values
- Applied median imputation for variables with low missing rates

Data consistency:
- Standardized binary variables (hit, explicit)
- Ensured correct data types
- Verified identifier uniqueness after cleaning

Outlier handling:
- Extreme values were retained because they reflect valid musical characteristics

---

## Exploratory Data Analysis (EDA)

EDA was conducted to examine differences between hit and non-hit songs.

Key analyses include:

Distribution comparison:
- Boxplots comparing acousticness between hit and non-hit songs
- Hit songs tend to have lower acousticness

Correlation analysis:
- Strong positive correlation between energy and loudness
- Negative correlation between energy and acousticness
- Weak correlation between key and time_signature with other features

Temporal analysis:
- Energy levels increased over time
- Relative energy within each decade shows stronger association with hit status

Overall findings:
- Hit songs tend to have higher:
  - energy
  - danceability
  - loudness
  - valence

- Hit songs tend to have lower:
  - acousticness
  - instrumentalness

These results suggest that production intensity and emotional characteristics play an important role in commercial success.

---

## Data Preprocessing and Feature Engineering

Preprocessing steps:

- Converted mode into binary variable is_major
- Standardized numerical variables using z-score normalization

Feature engineering:

Production intensity:
- Composite feature combining energy, loudness, and tempo

Emotional intensity:
- Combination of valence and energy

Energy relative to decade:
- Measures energy relative to historical context

These features improve interpretability and prepare the dataset for future predictive modeling.

---
## Key Findings

Main conclusions:

- Hit songs tend to have higher production intensity and emotional intensity
- Relative energy compared to decade average shows stronger association with hit status
- No single feature fully explains hit status
- Commercial success results from the interaction of multiple audio characteristics

---
## Challenges

Key challenges encountered:

- Severe class imbalance (few hit songs)
- Missing identifiers
- High missingness in some variables
- Overlapping distributions between hit and non-hit songs


