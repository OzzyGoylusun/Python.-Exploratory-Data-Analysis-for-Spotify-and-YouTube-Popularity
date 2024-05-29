# Exploratory Data Analysis for Spotify & YouTube Popularity

## Table of Contents

- [Data Analysis](#data-analysis)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Findings](#findings)

### Project Overview
---
This EDA analysis conducted in Python aims to discover and explore the specific elements that comprise the top 50 Spotify songs, as well as the extent to degree which their Spotify popularity is reflected on YouTube through their official channels on the platform.

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Python-Exploratory-Data-Analysis-SpotifyYouTube-E/blob/main/Data%20Visuals/Spotify-YouTube%20Logo.png"  alt="Spotify-YouTube Logo" width="250">
</p>

As an illustration, below is a heatmap designed to highlight correlations between various musical parameters, taking into account nearly 18,000 unique tracks found in the dataset used.

In this respect, *a darker green color* indicates a stronger positive correlation between two variables for more, while *a darker black color* indicates a stronger negative correlation between the variables. 

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Python-Exploratory-Data-Analysis-SpotifyYouTube-E/blob/main/Data%20Visuals/1)%20Data%20Correlation%20Heat%20Map.png"
 alt="Heatmap for Data Correlation" width="750">
</p>

For instance, there is a strong positive correlation between the *Energy and Loudness* parameters among the select tracks, with a coefficient value of 0.74, while there is a somewhat strong negative correlation between *Loudness and Acousticness*, with a coefficient value of -0.55.

---
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
3. Which musical track measures exhibit meaningful strong positive or negative correlations?
4. What are the main characteristics of the top 50 Spotify songs based on the correlated measures?
5. To what extent have the top 50 Spotify songs achieved popularity on YouTube as well?

### Data Analysis

What I enjoyed most in this EDA project was the challenge of calculating correlation coefficients between multiple track measures to uncover potential hidden patterns and relationships. Consequently, I found that resorting to a correlation matrix was an effective solution for revealing such insights:

```python
rows_with_na = main_sy_df[['Danceability', 'Energy', 'Key', 'Loudness', 
                           'Speechiness', 'Acousticness', 'Tempo', 'Instrumentalness',
                           'Liveness', 'Valence']].isna().any(axis=1)

corr_spotify_df = main_sy_df[~rows_with_na]

# Preparing our Spotify Correlation Matrix

corr_spotify = corr_spotify_df[['Danceability', 'Energy', 'Key', 'Loudness', 
                                   'Speechiness', 'Acousticness', 'Tempo', 'Instrumentalness',
                                   'Liveness', 'Valence']]

corr_spotify_matrix = corr_spotify.corr()

# Plotting our Correlation Heatmap using our customised color palette

## We have created our customised Spotify-themed heatmap colors. Darker Green - Stronger + Correlation; Darker Black - Stronger - Correlation
spotify_target_colors = ["#111111", "#535353", "#D1D7D0", "#F5F5F5", "#E1ECE3", "#62D089", "#1DB954", "#457E59"]

plt.figure(figsize=(10, 8))
sns.heatmap(corr_spotify_matrix, annot=True, cmap=spotify_target_colors)
```

### Findings

The critical EDA analysis results are summarised as follows:

1. Only **46%** of the top 50 Spotify songs/tracks was composed by the top 20 Spotify artists.
2. There is **almost no correlation** identified between the popularity of a Spotify song and its total duration, with a coefficient of -0.10. Nevertheless, it could be argued that composing slightly shorter songs could favour the artist to a small extent.

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Python.-Exploratory-Data-Analysis-Spotify-YouTube-Popularity/blob/main/Data%20Visuals/2)%20Correlation%20between%20All%20Songs%20and%20Durations.png"  alt="Correlation between songs and durations" width="750">
</p>

3. As visualized above in *the Project Overview*, **Energy** and **Loudness** exhibit a strong positive correlation, while **Energy** and **Valence-Danceability** show a somewhat strong positive correlation. Additionally, **Energy-Loudness** and **Acousticness-Instrumentalness** display a strong negative correlation.

4. The main characteristics of the top 50 Spotify songs, based on the correlated measures, are summarised as below:
   
<p align="center">
  <img src="https://github.com/OzzyGoylusun/Python.-Exploratory-Data-Analysis-Spotify-YouTube-Popularity/blob/main/Data%20Visuals/3)%20Natural%20Characteristics%20of%20the%20Top%2050%20Songs.png"  alt="Natural characteristics of the top 50 songs on Spotify" width="750">
</p>

* They exhibit medium or medium-to-high energy levels, accompanied by high or even extreme decibel levels.
* Both acousticness and instrumentalness are extremely low for such songs, meaning that the presence of lyrics with an electronic ambiance plays a paramount role in the popularity of these songs.
* Songs' danceability levels are predominantly at medium or good levels.
* Valence levels tend to skew towards neutral or slightly negative, suggesting that songs on Spotify are more preferred if they include elements of sadness, anger, depression or even anarchy instead of being cheerful or euphoric.

5. Only **22%** of the top 50 songs on Spotify managed to make it to the list of the top 50 viewed song tracks on YouTube within the same dataset. This percentage drops even further when considering the number of likes and comments left by users, with only **20%** and **8%** respectively.
   
<p align="center">
  <img src="https://github.com/OzzyGoylusun/Python.-Exploratory-Data-Analysis-Spotify-YouTube-Popularity/blob/main/Data%20Visuals/4)%20The%20Degree%20of%20Spotify%20Popularity%20on%20YouTube.png"  alt="Spotify vs. YouTube Popularity" width="750">
</p>


### Recommendations

It was left to the discretion of enjoying readers to draw their own conclusions based upon their valuable perspectives and individual needs.


### Limitations

XXX


### References

1. [Kaggle: Spotify & YouTube Dataset](https://www.kaggle.com/datasets/salvatorerastelli/spotify-and-youtube)
2. [Seaborn: Heatmap Data Correlation Visualisation](https://seaborn.pydata.org/generated/seaborn.heatmap.html)
