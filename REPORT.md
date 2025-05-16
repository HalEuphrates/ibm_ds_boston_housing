# 🏠 Boston Housing Data Analysis

This report presents an exploratory data analysis of the Boston Housing dataset, a classic dataset widely used in regression and housing price prediction problems. The analysis was conducted as part of the IBM Data Science professional coursework, and aims to uncover patterns, correlations, and statistical relationships that influence the median value of homes across various Boston neighborhoods.

---

## Dataset Overview

The dataset contains 506 observations across 14 variables, each describing a housing tract in Boston, Massachusetts. The target variable is `MEDV`, the median value of owner-occupied homes in thousands of dollars.

Below is a brief description of the main variables used in this analysis:

| Variable | Description |
|----------|-------------|
| `CRIM`   | Per capita crime rate by town |
| `ZN`     | Proportion of residential land zoned for large lots |
| `INDUS`  | Proportion of non-retail business acres per town |
| `CHAS`   | Charles River dummy variable (1 = tract bounds river) |
| `NOX`    | Nitric oxides concentration (parts per 10 million) |
| `RM`     | Average number of rooms per dwelling |
| `AGE`    | Proportion of owner-occupied units built before 1940 |
| `DIS`    | Weighted distances to five Boston employment centers |
| `RAD`    | Index of accessibility to radial highways |
| `TAX`    | Property tax rate per $10,000 |
| `PTRATIO`| Pupil-teacher ratio by town |
| `B`      | A composite of Black population by town |
| `LSTAT`  | % of lower status population |
| `MEDV`   | Median value of homes (target variable) |

---

## Data Exploration and Visualization

Initial data exploration involved examining summary statistics and visualizing key variables using boxplots, bar plots, histograms, and scatter plots. A boxplot of `MEDV` revealed some degree of skewness and several high-value outliers, likely representing luxury tracts. While such outliers may skew certain statistics, they were retained for this analysis due to their relevance in housing market variation.

Analysis of `CHAS`, the binary indicator of proximity to the Charles River, revealed that only a small subset of tracts border the river. A boxplot comparing `MEDV` across `CHAS` categories showed slightly higher home values near the river, though the spread was wide and overlapping.

To investigate the effect of housing age, the continuous `AGE` variable (proportion of homes built before 1940) was converted into categorical bins (e.g., <35%, 35–70%, >70%). A boxplot comparing `MEDV` across these groups indicated a subtle trend of declining home value with increasing housing age, though the differences were not stark.

A scatter plot between `NOX` (nitric oxide pollution) and `INDUS` (industrial land usage) highlighted a strong positive relationship, implying that more industrial neighborhoods tend to have higher pollution levels — consistent with urban environmental expectations.

---

## Statistical Testing

A two-sample t-test was conducted to assess whether proximity to the Charles River (`CHAS`) has a statistically significant impact on home values. The test compared `MEDV` between tracts bordering the river and those that do not. The result suggested no strong evidence of a significant difference, implying that river proximity alone may not drive higher property values.

To explore the influence of housing age, an ANOVA test was applied to compare `MEDV` across the aforementioned `AGE` groups. While there were observable differences in group means, the ANOVA results indicated that these were not statistically significant at conventional levels.

Finally, Pearson correlation analysis confirmed a strong positive correlation between `NOX` and `INDUS`, validating the visual relationship observed earlier.

---

## Regression Analysis

A simple linear regression model was fitted to assess the relationship between `DIS` (distance to employment centers) and `MEDV`. The model revealed a statistically significant negative relationship: as the distance from employment hubs increases, the median home value tends to decrease. This is consistent with urban economic models where proximity to job centers often increases housing demand and prices.

---

## Conclusion

This analysis of the Boston Housing dataset revealed multiple socio-environmental factors associated with variations in home values. Variables such as air quality (`NOX`), industrial density (`INDUS`), and proximity to employment centers (`DIS`) demonstrated meaningful relationships with the target variable `MEDV`.

While the dataset provides valuable insights, it also has limitations: it lacks temporal data, detailed demographics, and external economic factors. Thus, any predictive models built from it should be interpreted cautiously and supplemented with richer context when applied to real-world scenarios.

Nonetheless, this project illustrates the utility of data science methods — including visualization, statistical testing, and regression — for extracting insight from complex real-world datasets.

---

## Tools Used

- Python (Jupyter Notebook)
- pandas, matplotlib, seaborn
- scipy.stats

---

*Report authored by [Hal Euphrates](https://github.com/HalEuphrates) as part of IBM Data Science coursework.*
