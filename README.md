# Identifying Hidden Patterns and Visualising All Nobel Prize Winners

## Table of Contents

- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Findings](#findings)

### Project Overview
---

The Nobel Prize is perhaps the most recognized scientific prize in the world. Accordingly, this data analysis project conducted in **Python** is intended to identify undiscovered patterns by exploring some intriguing Nobel Prize winner data.

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Python.-Identifying-Patterns-and-Visualising-Nobel-Prize-Winners/blob/main/Visuals/Nobel%20Prize%20Image.png"
 alt="Alfred Nobel">
</p>

Made available by the Nobel Foundation, the analysed data includes all prize winners from 1901 to 2023. In this regard, awards are bestowed in chemistry, literature, physics, physiology or medicine, economics, and peace. 


### Data Sources

The dataset used for this analysis is the *"nobel_dataset.csv"* file, containing detailed information about each award winner up to date ever since the Prize was established.

### Tools

- [Anaconda Navigator: ](https://www.anaconda.com/download)
  - To access the Jupyter Notebook for **Python**


### Data Preparation

Only *the nobel_dataset.csv* dataset was first inspected and then imported into a Pandas DataFrame to begin conducting the exploratory data analysis work:


### Exploratory Data Analysis

EDA involved exploring the Nobel Prize data to answer key questions, such as:

1.  Which has been the most commonly awarded gender and top birth country up to date?
2.  What has been the proportion of US-born winners per decade?
3.  What has been the proportion of female laureates per decade and category?
4.  Who was the first woman to receive a Nobel Prize, and in what category?
5.  Which individuals/organisations have won the Prize multiple times?


### Data Analysis

The following code helped me consolidate my knowledge in subsetting, filtering and then grouping the resulting subset by two separate categories for a count-type aggregate operation:

```python
female_winners = nobel_winners_df[nobel_winners_df['sex'] == 'Female'].groupby(['decade',
                                                                                'category']).agg({"prize":"count"})
```

In addition, the code below helped me clear out the blurry lines between a Pandas Series and DataFrames where each one of those have a different set of functions and methods.

By resorting to an integer-based indexing on my Pandas DataFrame below, I was able to fetch what I required and assigned it to a variable:

```python
top_birth_country = nobel_winners_df["birth_country"].value_counts().reset_index().iloc[0,0]
```

### Findings

The critical analysis results are summarised as follows:

1. The most commonly awarded gender and top birth country of the award winners turn out to be **Male** and **the United States of America** respectively.
   
2. The proportion of **US-born award winners** till 2000 was in a gradual uptrend, peaking at slightly higher than **the 0.4 ratio**, before dipping by nearly **25%** during early 2000s:
<p align="center">
<img src="https://github.com/OzzyGoylusun/Python.-Identifying-Patterns-and-Visualising-Nobel-Prize-Winners/blob/main/Visuals/Trend%20of%20US-born%20Winners%20per%20Decade.png" alt="Trend of US-born Winners per Decade" width="650">
</p>
  
3. **Female award winners** have almost entirely dominated the disciplines of **Peace and Literature** as of the 2000s:
<p align="center">
<img src="https://github.com/OzzyGoylusun/Python.-Identifying-Patterns-and-Visualising-Nobel-Prize-Winners/blob/main/Visuals/Trend%20of%20Female%20Winners%20per%20Decade%20and%20Category.png" alt="Trend of Female Winners per Decade and Category" width="650">
</p>

4. **Marie Curie**, née Sklodowska was the first woman to receive a Nobel Prize in the category of **Physics**.


### Limitations

The presumption is that the dataset provided by DataCamp encompasses all Nobel Prize winners up to date.

### References

1. [DataCamp](https://www.datacamp.com/)
2. [GeeksforGeeks: Use of Cut Function on Python](https://www.geeksforgeeks.org/pandas-cut-method-in-python/)
3. [Pandas DataFrame: Use of iLoc](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.iloc.html)
4. [Seaborn Library: Visualising a Lineplot](https://seaborn.pydata.org/generated/seaborn.lineplot.html)

