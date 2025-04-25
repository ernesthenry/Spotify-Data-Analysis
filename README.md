# Spotify Data Analysis Python Project 🎼🎧

![Spotify Analysis](https://github.com/ernesthenry/Spotify-Data-Analysis/assets/91487663/43749cf9-4eb1-476c-89ea-bf1625b17168)

## Contents 📖

- [Introduction](#introduction)
- [Import Required Libraries](#import-required-libraries)
- [Exploring the Dataset](#exploring-the-dataset)
- [Identifying Null Values in the Dataset](#identifying-null-values-in-the-dataset)
- [Dataset Overview: Rows, Columns, Data Types, and Memory Usage](#dataset-overview-rows-columns-data-types-and-memory-usage)
- [Extracting Insights from the Dataset through Analysis](#extracting-insights-from-the-dataset-through-analysis)

## Introduction

The Spotify Data Analysis Project: In today's changing world data analysis has become crucial in fields such as business, research and meteorology. This project showcases the role that data plays in making decisions, advancing research initiatives and even predicting weather patterns.

The immense potential of data analysis is evident in this project, which focuses on extracting insights from music related datasets using Python. At its core, Spotify takes stage as an audio streaming giant with captivating features like seamless song sharing and synchronized lyrics display.

Throughout this project I delved into the realm of data using Python's libraries and functions. From analyzing to visualizing the data, this project covers all aspects of data processing. The interactive environment provided by Jupyter notebook enhanced my experience by allowing me to engage with the data and discover patterns.

Through the Spotify Data Analysis Project I not only sharpened my skills but also gained a deep understanding of how data intertwines with the world of music. This journey provided insights and equipped me with confidence to undertake similar projects in the future.

Feel free to reach out for any questions or suggestions about this project. I'm open to discussions and eager to assist.
[Linkedln | Henry Kato](https://www.linkedin.com/in/keh95/)

Don't forget to follow and star ⭐ the repository if you find it valuable.

### Tools Used 🛠️:
- Programming Language: Python
- Libraries: Pandas, Numpy, Matplotlib, Seaborn
- IDE: Jupyter Notebook

Dataset: [Spotify Dataset](https://www.kaggle.com/datasets/lehaknarnauli/spotify-datasets?select=artists.csv)

## Import Required Libraries

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

- `import numpy as np`: This imports the NumPy library and aliases it as 'np'. NumPy is used for numerical computations and provides support for arrays and matrices.
- `import pandas as pd`: This imports the Pandas library and aliases it as 'pd'. Pandas is used for data manipulation and analysis, providing data structures like DataFrames for tabular data.
- `import matplotlib.pyplot as plt`: This imports the Pyplot module from the Matplotlib library and aliases it as 'plt'. Matplotlib is a popular plotting library in Python, and Pyplot provides a convenient interface to create visualizations.
- `import seaborn as sns`: This imports the Seaborn library and aliases it as 'sns'. Seaborn is built on top of Matplotlib and offers a higher-level interface for creating attractive statistical visualizations.

## Exploring the Dataset

```python
sp_tracks = pd.read_csv('D:/spotifydata/tracks.csv')
sp_feature = pd.read_csv('D:/spotifydata/SpotifyFeatures.csv')
```

- `sp_tracks = pd.read_csv('D:/spotifydata/tracks.csv')`: This line reads a CSV file named 'tracks.csv' located at the 'D:/spotifydata/' directory and loads its data into a Pandas DataFrame called `sp_tracks`. This DataFrame is likely to contain information about tracks.
- `sp_feature = pd.read_csv('D:/spotifydata/SpotifyFeatures.csv')`: This line reads another CSV file named 'SpotifyFeatures.csv' from the same directory and loads its data into a separate Pandas DataFrame called `sp_feature`. This DataFrame probably contains additional features or attributes related to the Spotify tracks.

```python
# viewing the tracks data
sp_tracks.head()
```

NOTE: The image provided is not the entirety of the complete image, as there are restrictions in capturing full images through screenshots. To access the comprehensive table, please refer to the Jupyter notebook folder within this repository.

- `#viewing the tracks data`: This is a comment that indicates the following line of code is meant to display or view the data in the 'sp_tracks' DataFrame.
- `sp_tracks.head()`: This line of code calls the `head()` method on the 'sp_tracks' DataFrame. The `head()` method is used to display the first few rows of the DataFrame. This is useful for quickly getting an overview of the data.

```python
# viewing the feature data
sp_feature.head()
```

NOTE: The image provided is not the entirety of the complete image, as there are restrictions in capturing full images through screenshots. To access the comprehensive table, please refer to the Jupyter notebook folder within this repository.

- `#viewing the feature data`: This is a comment that indicates the following line of code is intended to display or view the data in the 'sp_feature' DataFrame.
- `sp_feature.head()`: This line of code calls the `head()` method on the 'sp_feature' DataFrame. The `head()` method is used to display the first few rows of the DataFrame. This allows you to quickly inspect the initial records and get a sense of the data.

## Identifying Null Values in the Dataset

```python
# checking null in tracks data
pd.isnull(sp_tracks).sum()
```

- `#checking null in tracks data`: This comment indicates that the following line of code is used to identify and count the missing (null) values in the 'sp_tracks' DataFrame.
- `pd.isnull(sp_tracks).sum()`: This line of code uses the `pd.isnull()` function on the 'sp_tracks' DataFrame to create a boolean DataFrame where each cell contains `True` if the corresponding cell in the original DataFrame is null and `False` otherwise. The `.sum()` function is then used to count the number of `True` values in each column, effectively giving you the count of missing values in each column.

```python
# checking null in feature data
pd.isnull(sp_feature).sum()
```

- `#checking null in feature data`: This comment indicates that the following line of code is intended to identify and count the missing (null) values in the 'sp_feature' DataFrame.
- `pd.isnull(sp_feature).sum()`: This line of code uses the `pd.isnull()` function on the 'sp_feature' DataFrame to create a boolean DataFrame where each cell contains `True` if the corresponding cell in the original DataFrame is null and `False` otherwise. The `.sum()` function is then used to count the number of `True` values in each column, effectively giving you the count of missing values in each column.

## Dataset Overview: Rows, Columns, Data Types, and Memory Usage

```python
# checking info in tracks data
sp_tracks.info()
```

- `#checking info in tracks data`: This comment indicates that the following line of code is meant to display information about the 'sp_tracks' DataFrame.
- `sp_tracks.info()`: This line of code calls the `info()` method on the 'sp_tracks' DataFrame. The `info()` method provides a concise summary of the DataFrame, including the data types of each column, the number of non-null values, and memory usage. It's a useful way to get a quick overview of the data and its structure.

```python
# checking info in feature data
sp_feature.info()
```

- `#checking info in feature data`: This comment indicates that the following line of code is intended to display information about the 'sp_feature' DataFrame.
- `sp_feature.info()`: This line of code calls the `info()` method on the 'sp_feature' DataFrame. The `info()` method provides a concise summary of the DataFrame, including the data types of each column, the number of non-null values, and memory usage. This summary helps you understand the structure and content of the DataFrame.

## Extracting Insights from the Dataset through Analysis 📊

### 1. Exploring the 10 Least Popular Songs in the Spotify Dataset

```python
a = sp_tracks.sort_values('popularity', ascending=True)[0:10]
a[['name', 'popularity']]
```

- `a = sp_tracks.sort_values('popularity', ascending=True)[0:10]`: This line of code creates a new DataFrame `a` by sorting the 'sp_tracks' DataFrame based on the 'popularity' column in ascending order. The `[0:10]` notation selects the first 10 rows of the sorted DataFrame, effectively selecting the 10 least popular tracks.
- `a[['name', 'popularity']]`: This line of code selects specific columns, namely 'name' and 'popularity', from the DataFrame `a` created in the previous line. This will show the names of the 10 least popular tracks along with their corresponding popularity values.

### 2. Descriptive Statistics

```python
# descriptive statistics of tracks
sp_tracks.describe().transpose()
```

- `#descriptive statistics of tracks`: This comment indicates that the following line of code is intended to compute and display descriptive statistics of the 'sp_tracks' DataFrame.
- `sp_tracks.describe().transpose()`: This line of code calls the `describe()` method on the 'sp_tracks' DataFrame, which calculates various summary statistics for each numeric column in the DataFrame. The `.transpose()` method is then used to transpose the resulting statistics table, making it easier to read with columns as rows and vice versa.

```python
# descriptive of feature
sp_feature.describe().transpose()
```

- `#descriptive statistics of feature`: This comment indicates that the following line of code is intended to compute and display descriptive statistics of the 'sp_feature' DataFrame.
- `sp_feature.describe().transpose()`: This line of code calls the `describe()` method on the 'sp_feature' DataFrame, which calculates various summary statistics for each numeric column in the DataFrame. The `.transpose()` method is then used to transpose the resulting statistics table, making it easier to read with columns as rows and vice versa.

### 3. Discovering the Top 10 Popular Songs in the Spotify Dataset

```python
a = sp_tracks
b = a[a['popularity'] > 90].sort_values('popularity', ascending=False)[:10]
b[['name', 'popularity', 'artists']]
```

- `a = sp_tracks`: This line of code assigns the 'sp_tracks' DataFrame to a new DataFrame variable `a`.
- `b = a[a['popularity'] > 90].sort_values('popularity', ascending=False)[:10]`: This line of code creates a new DataFrame `b` by selecting rows from the DataFrame `a` where the 'popularity' column is greater than 90. The DataFrame is then sorted in descending order based on the 'popularity' column, and the first 10 rows are selected. This effectively gives you the top 10 most popular tracks.
- `b[['name', 'popularity', 'artists']]`: This line of code selects specific columns ('name', 'popularity', and 'artists') from the DataFrame `b` created in the previous line. This will display the names, popularity values, and artist information of the top 10 most popular tracks.

### 4. Setting Release Date as the Index Column

```python
sp_tracks.set_index('release_date', inplace=True)
sp_tracks.index = pd.to_datetime(sp_tracks.index)
sp_tracks.head()
```

- `sp_tracks.set_index('release_date', inplace=True)`: This line of code sets the 'release_date' column as the index of the 'sp_tracks' DataFrame. The `inplace=True` argument modifies the DataFrame in place, meaning the change is applied directly to the original DataFrame.
- `sp_tracks.index = pd.to_datetime(sp_tracks.index)`: This line of code converts the index of the 'sp_tracks' DataFrame to a datetime format using the `pd.to_datetime()` function. This is often done to ensure that the index represents dates in a meaningful way, allowing for time-based operations.
- `sp_tracks.head()`: This line of code calls the `head()` method on the 'sp_tracks' DataFrame, which will display the first few rows of the DataFrame with the updated index.

### 5. Extracting Artist Name from the 18th Row of the Dataset

```python
sp_tracks[['artists']].iloc[18]
```

- `sp_tracks[['artists']].iloc[18]`: This line of code selects the 'artists' column from the 'sp_tracks' DataFrame and then uses the `iloc[18]` indexer to retrieve the value at the 18th row of the 'artists' column. This will display the artists' information for the track at index 18.

### 6. Converting Song Duration from Milliseconds to Seconds

```python
sp_tracks['duration'] = sp_tracks['duration_ms'].apply(lambda x: round(x/1000))
sp_tracks.drop('duration_ms', inplace=True, axis=1)
sp_tracks.duration.head()
```

- `sp_tracks['duration'] = sp_tracks['duration_ms'].apply(lambda x: round(x/1000))`: This line of code creates a new column called 'duration' in the 'sp_tracks' DataFrame. It calculates the duration in seconds by applying a lambda function to the 'duration_ms' column. The lambda function divides the 'duration_ms' value by 1000 and rounds it to get the duration in seconds.
- `sp_tracks.drop('duration_ms', inplace=True, axis=1)`: This line of code removes the original 'duration_ms' column from the 'sp_tracks' DataFrame. The `inplace=True` argument makes the change directly to the DataFrame.
- `sp_tracks.duration.head()`: This line of code displays the first few values from the newly created 'duration' column in the 'sp_tracks' DataFrame.

### 7. Visualization: Pearson Correlation Heatmap for Two Variables

```python
td = sp_tracks.drop(['key', 'mode', 'explicit'], axis=1).corr(method='pearson')
plt.figure(figsize=(9, 5))
hmap = sns.heatmap(td, annot=True, fmt='.1g', vmin=-1, vmax=1, center=0, cmap='Greens', linewidths=0.1, linecolor='black')
hmap.set_title('Correlation HeatMap')
hmap.set_xticklabels(hmap.get_xticklabels(), rotation=90)
```

- `td = sp_tracks.drop(['key', 'mode', 'explicit'], axis=1).corr(method='pearson')`: This line of code creates a correlation matrix by calculating Pearson correlation coefficients between numeric columns in the 'sp_tracks' DataFrame. It drops the columns 'key', 'mode', and 'explicit' before calculating the correlations.
- `plt.figure(figsize=(9, 5))`: This line of code sets the figure size for the upcoming heatmap visualization using Matplotlib.
- `hmap = sns.heatmap(td, annot=True, fmt='.1g', vmin=-1, vmax=1, center=0, cmap='Greens', linewidths=0.1, linecolor='black')`: This line of code uses Seaborn's `heatmap()` function to create a heatmap visualization of the correlation matrix. It displays the correlation values as annotations, uses a color map ('Greens') to represent the correlation strength, and sets the range of correlation values to be between -1 and 1.
- `hmap.set_title('Correlation HeatMap')`: This line of code sets the title for the heatmap visualization.
- `hmap.set_xticklabels(hmap.get_xticklabels(), rotation=90)`: This line of code rotates the x-axis labels of the heatmap for better readability.

### 8. Creating a 4% Sample of the Entire Dataset

```python
sample_sp = sp_tracks.sample(int(0.004 * len(sp_tracks)))
print(len(sample_sp))
```

- `sample_sp = sp_tracks.sample(int(0.004 * len(sp_tracks)))`: This line of code creates a random sample of the 'sp_tracks' DataFrame. The `sample()` function is used to select a random subset of rows. The argument `int(0.004 * len(sp_tracks))` determines the number of rows to be sampled. In this case, it's approximately 0.4% of the total number of rows in the 'sp_tracks' DataFrame.
- `print(len(sample_sp))`: This line of code prints the length (number of rows) of the `sample_sp` DataFrame to the console. This will show you the number of rows in the sampled subset.

### 9. Regression Plot of Loudness vs. Energy with Regression Line

```python
plt.figure(figsize=(8, 4))
sns.regplot(data=sample_sp, y='loudness', x='energy', color='#054907').set(title='Regression Plot - Loudness vs Energy Correlation')
```

- `plt.figure(figsize=(8, 4))`: This line of code sets the figure size for the upcoming visualization using Matplotlib.
- `sns.regplot(data=sample_sp, y='loudness', x='energy', color='#054907')`: This line of code uses Seaborn's `regplot()` function to create a regression plot. It visualizes the relationship between the 'loudness' and 'energy' columns from the `sample_sp` DataFrame. The `color='#054907'` argument sets the color of the plot.
- `.set(title='Regression Plot - Loudness vs Energy Correlation')`: This line of code sets the title for the regression plot.

### 10. Regression Plot of Popularity vs. Acousticness with Regression Line

```python
plt.figure(figsize=(8, 4))
sns.regplot(data=sample_sp, y='popularity', x='acousticness', color='#008000').set(title='Regression Plot - Popularity vs Acousticness Correlation')
```

- `plt.figure(figsize=(8, 4))`: This line of code sets the figure size for the upcoming visualization using Matplotlib.
- `sns.regplot(data=sample_sp, y='popularity', x='acousticness', color='#008000')`: This line of code uses Seaborn's `regplot()` function to create a regression plot. It visualizes the relationship between the 'popularity' and 'acousticness' columns from the `sample_sp` DataFrame. The `color='#008000'` argument sets the color of the plot.
- `.set(title='Regression Plot - Popularity vs Acousticness Correlation')`: This line of code sets the title for the regression plot.

### 11. Adding a New Column to the Tracks Table

```python
sp_tracks['dates'] = sp_tracks.index.get_level_values('release_date')
sp_tracks.dates = pd.to_datetime(sp_tracks.dates)
years = sp_tracks.dates.dt.year
sp_tracks.head()
```

- `sp_tracks['dates'] = sp_tracks.index.get_level_values('release_date')`: This line of code creates a new column called 'dates' in the 'sp_tracks' DataFrame. It uses the `get_level_values()` method on the index of the DataFrame to extract the 'release_date' values and assigns them to the 'dates' column.
- `sp_tracks.dates = pd.to_datetime(sp_tracks.dates)`: This line of code converts the values in the 'dates' column to datetime format using the `pd.to_datetime()` function. This ensures that the dates are treated as proper datetime objects.
- `years = sp_tracks.dates.dt.year`: This line of code extracts the year component from the 'dates' column using the `dt.year` attribute of the datetime objects. It assigns the extracted years to the 'years' variable.
- `sp_tracks.head()`: This line of code displays the first few rows of the modified 'sp_tracks' DataFrame, which now includes the 'dates' column and the extracted 'years' variable.

### 12. Graph: Number of Songs per Year

```python
sns.displot(years, discrete=True, aspect=2, height=4, kind='hist', color='g').set(title='No of songs - per year')
```

- `sns.displot(years, discrete=True, aspect=2, height=4, kind='hist', color='g')`: This line of code uses Seaborn's `displot()` function to create a histogram plot. It visualizes the distribution of the 'years' variable, which contains the release years of the songs. The `discrete=True` argument indicates that the data is discrete (years), `aspect=2` adjusts the width-to-height ratio of the plot, `height=4` sets the height of the plot, `kind='hist'` specifies that it's a histogram plot, and `color='g'` sets the color of the plot.
- `.set(title='No of songs - per year')`: This line of code sets the title for the histogram plot.

### 13. Line Graph: Duration of Songs Over Each Year

```python
total_dr = sp_tracks.duration
fig_dims = (15, 5)
fig, ax = plt.subplots(figsize=fig_dims)
fig = sns.barplot(x=years, y=total_dr, ax=ax, errwidth=False).set(title='Years vs Duration')
plt.xticks(rotation=90)
```

- `total_dr = sp_tracks.duration`: This line of code creates a new variable `total_dr` and assigns the values from the 'duration' column of the 'sp_tracks' DataFrame to it.
- `fig_dims = (15, 5)`: This line of code sets the dimensions of the figure for the upcoming visualization.
- `fig, ax = plt.subplots(figsize=fig_dims)`: This line of code uses Matplotlib to create a subplot figure with the specified dimensions. It returns two variables: `fig` (the figure) and `ax` (the axis).
- `fig = sns.barplot(x=years, y=total_dr, ax=ax, errwidth=False)`: This line of code uses Seaborn's `barplot()` function to create a bar plot. It plots the 'years' on the x-axis and 'total_dr' (duration) on the y-axis, using the provided axis `ax`. The `errwidth=False` argument disables error bars.
- `.set(title='Years vs Duration')`: This line of code sets the title for the bar plot.
- `plt.xticks(rotation=90)`: This line of code rotates the x-axis tick labels for better readability.

### 14. Horizontal Bar Plot: Song Duration Across Different Genres

```python
plt.title('Duration of songs in different Genres')
sns.color_palette('crest', as_cmap=True)
sns.barplot(y='genre', x='duration_ms', data=sp_feature)
plt.xlabel('Duration in ms')
plt.ylabel('Genres')
```

- `plt.title('Duration of songs in different Genres')`: This line of code sets the title for the upcoming visualization using Matplotlib.
- `sns.color_palette('crest', as_cmap=True)`: This line of code sets the color palette for the visualization. The 'crest' palette is being used here.
- `sns.barplot(y='genre', x='duration_ms', data=sp_feature)`: This line of code uses Seaborn's `barplot()` function to create a bar plot. It plots the 'genre' on the y-axis and 'duration_ms' on the x-axis from the 'sp_feature' DataFrame.
- `plt.xlabel('Duration in ms')`: This line of code sets the label for the x-axis.
- `plt.ylabel('Genres')`: This line of code sets the label for the y-axis.

### 15. Bar Plot: Top Five Genres by Popularity

```python
sns.set_style(style='darkgrid')
plt.figure(figsize=(8, 4))
Top = sp_feature.sort_values('popularity', ascending=False)[:10]
sns.barplot(y='genre', x='popularity', data=Top).set(title='Genres by Popularity-Top 5')
```

- `sns.set_style(style='darkgrid')`: This line of code sets the style of the Seaborn plots to 'darkgrid' style, which includes a dark grid in the background of the plot.
- `plt.figure(figsize=(8, 4))`: This line of code sets the figure size for the upcoming visualization using Matplotlib.
- `Top = sp_feature.sort_values('popularity', ascending=False)[:10]`: This line of code creates a new DataFrame `Top` by sorting the 'sp_feature' DataFrame in descending order based on the 'popularity' column and selecting the top 10 rows.
- `sns.barplot(y='genre', x='popularity', data=Top).set(title='Genres by Popularity-Top 5')`: This line of code uses Seaborn's `barplot()` function to create a bar plot. It plots the 'genre' on the y-axis and 'popularity' on the x-axis from the `Top` DataFrame. The `.set()` function sets the title for the plot.
