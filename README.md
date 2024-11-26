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

However, there are instances where a city has only one restaurant, making it impossible to determine the mode of `Cuisines`. To ensure that no restaurant data is lost in such cases, I will replace the missing `Cuisines` values with the placeholder `"Unknown"`. This approach allows us to retain the remaining data for those restaurants while maintaining data integrity.

---

**Reducing memory**
- I removed the `Locality Verbose` column because it's a Concatination of both `city` and `Locality`. it's Totaly unnecessary for keep this column.
- I changed the `Object` Data type to `Category` for the columns with more than 1 unique value and less than or equal to 6 unique value.
