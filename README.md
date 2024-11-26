# Restaurant-Analysis

***Necessary Libraries for this project***

- `pandas` for Data Manipulation.
- `numpy` for Numerical Computation.
- `seaborn`,`matplotlib` for static charts and `plotly` for Geographic chart.
- `geopy` for Geographic Analysis.
- `scipy` for Statistical Analysis.
- `scikit-learn` for Machine Learning.

***Exploring the Dataset***

- Data types needs Attention.
- There are `9551` rows and `21` columns.
- `Cuisines` column has `9` *Null* Values.
- There is *No Duplicated* values in the Dataset.

***Data Cleansing***

---

To handle missing values (`NaN`) in the `Cuisines` column based on the `City` column, I aim to create a function (`str_miss`) that replaces these missing values with the mode of `Cuisines` for the corresponding `City`. 

However, there are instances where a city has only one restaurant, making it impossible to determine the mode of `Cuisines`. To ensure that no restaurant data is lost in such cases, I will replace the missing `Cuisines` values with the placeholder `"Unknown"`. This approach allows me to retain the remaining data for those restaurants while maintaining data integrity.

---
