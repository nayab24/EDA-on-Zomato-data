# Zomato Data Exploratory Data Analysis (EDA) Project
## Overview
This project aims to perform an Exploratory Data Analysis (EDA) on the Zomato dataset to uncover insights and patterns related to restaurant listings, customer preferences, and other relevant aspects. The dataset includes various attributes such as restaurant names, locations, ratings, cuisines, and whether online ordering is available.

## Table of Contents
* Project Structure
* Dataset
* Installation
* Usage
* Analysis
* Results
* Contributing
* License

## Dataset
* Source: The Zomato dataset can be found [here](https://github.com/nayab24/EDA-on-Zomato-data/blob/main/Zomato%20data%20.csv).
* Attributes: The dataset contains various attributes such as:
 
  * Restaurant Name
  * online_orde
  * book_table
  * rate
  * votes
  * approx_cost(for two people)
  * listed_in(type)

## Usage
* Clone the repository:

```
git clone https://github.com/yourusername/zomato-eda.git
cd zomato-eda
```
* Place the dataset (zomato.csv) in the data/ directory.

* Open the Jupyter Notebook:
```
jupyter notebook notebooks/EDA_Zomato.ipynb
```
* Run the cells in the notebook to perform the analysis.

## Analysis

The analysis includes the following steps:

1. **Data Cleaning:** Handling missing values, duplicates, and incorrect data types using numpy and pandas.
2. **Data Visualization:** Creating various plots to visualize the data using matplotlib and seaborn, including bar plots, scatter plots, and heatmaps.
3. **Feature Engineering:** Creating new features to aid in the analysis.
4. **Insights:** Deriving insights from the visualizations and statistical analysis.

### Example Code Snippets

Heatmap of Online Orders vs. Restaurant Type

**python**
```
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
df = pd.read_csv('data/zomato.csv')

# Create a pivot table
pivot_table = df.pivot_table(index='listed_in(type)', columns='online_order', aggfunc='size', fill_value=0)

# Plot the heatmap
sns.heatmap(pivot_table, annot=True, cmap="YlGnBu", fmt='d')
plt.title("Heatmap of Online Orders vs. Restaurant Type")
plt.xlabel("Online Order")
plt.ylabel("Restaurant Type")
plt.show()
```

## Results

* **Online Ordering Trends:** Most popular restaurant types for online orders.
* **Cuisine Preferences:** Analysis of the most popular cuisines in different locations.
* **Rating Analysis:** Distribution of restaurant ratings and factors affecting ratings.
