# Python-Exploratory-Data-Analysis-SpotifyYouTube-E

## Table of Contents

- [Data Analysis](#data-analysis)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Findings](#findings)

### Project Overview
---
This EDA analysis conducted in Python aims to discover and explore the specific elements that comprise the top 50 Spotify songs, as well as the extent to degree which their Spotify popularity is reflected on YouTube through their official channels on the platform.

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Python-Exploratory-Data-Analysis-SpotifyYouTube-E/blob/main/Data%20Visuals/Spotify-YouTube%20Logo.png"  alt="Spotify-YouTube Logo" width="300">
</p>

As an illustration, below is a heatmap designed to highlight correlations between various musical parameters, taking into account nearly 18,000 unique tracks found in the dataset used.

In this respect, *a darker green color* indicates a stronger positive correlation between two variables for more, while *a darker black color* indicates a stronger negative correlation between the variables. 

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Python-Exploratory-Data-Analysis-SpotifyYouTube-E/blob/main/Data%20Visuals/1)%20Data%20Correlation%20Heat%20Map.png"
 alt="Heatmap for Data Correlation" width="750">
</p>

For instance, there is a strong positive correlation between the *Energy and Loudness* parameters among the select tracks, with a coefficient value of 0.74, while there is a somewhat strong negative correlation between *Loudness and Acousticness*, with a coefficient value of -0.55.

### Data Sources

The dataset used for this EDA project was **Spotify-YouTube.csv** also available on Kaggle. (*Refer to References*)

### Tools

- Anaconda Navigator to access the Jupyter Notebook for **Python** - Data Inspection, Manipulation, Analysis and Visualisation
  - [Download Here](https://www.anaconda.com/download)

### Data Preparation and Preprocessing

The following data preparation and preprocessing tasks were undertaken:

- The dataset was inspected and imported into two separate Pandas DataFrames, one for each (i.e., Spotify and YouTube-related data).
- NaN/non-existing values of certain records within particular columns were also removed.
- Certain columns that would not be required at any stage of the analysis were permanently dropped in both DataFrames.
- Some data transformation tasks (e.g., new columns for a deeper data classification, data conversion) were undertaken in an attempt to represent the data in the most user-friendly manner possible.

### Exploratory Data Analysis

By analysing the dataset at hand, EDA sought to answer the following key questions, including but not limited to:

1. What percentage of the top 50 songs on Spotify are composed by the top 20 artists on Spotify?
2. How strong is the correlation between the top 50 Spotify tracks and their corresponding song durations?
3. XXX
4. XXX
5. XXX

### Data Analysis

XXX

```python
XXX
```

### Findings

The critical analysis results are summarised as follows:

1. XXX
2. XXX


### Recommendations

Based on the findings above, I propose the following recommendations:

1. XXX
2. XXX
3. XXX

### Limitations

XXX


### References

1. [Kaggle: Spotify & YouTube Dataset](https://www.kaggle.com/datasets/salvatorerastelli/spotify-and-youtube)
2. [Seaborn: Heatmap Data Correlation Visualisation](https://seaborn.pydata.org/generated/seaborn.heatmap.html)
