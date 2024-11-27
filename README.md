# Restaurant-Analysis

***Necessary Libraries for this project***

- `pandas` for Data Manipulation.
- `numpy` for Numerical Computation.
- `seaborn`,`matplotlib` for Visualizations.
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

**Reducing memory**
- I removed the Locality Verbose column as it is a concatenation of City and Locality, making it redundant. Keeping this column is unnecessary since its information can already be derived from existing columns.
- I optimized the dataset by converting columns with an object data type to the category data type for those that have more than one unique value and six or fewer unique values. This conversion reduces memory usage and enhances processing efficiency while preserving the data's categorical nature.

---

***EDA (Exploratory Data Analysis)***

---

**Distribution**

- Votes is Right skewed data.
- Aggregate rating has outlier, more number of 0 rating.

**Number of Restaurants based on countries**

> There are `15 countries` in this Dataset.

<p> India have more number of Restaurants among all other Countries in the Dataset followed by US.</p>

**Top 10 Cities with more number of Restaurants**

- New Delhi (5473)
- Gurgaon (1118)
- Noida (1080)
- Faridabad (251)
- Ghaziabad (25)
- Bhubaneshwar (21)
- Lucknow (21)
- Ahmedabad (21)
- Amritsar (21)
- Guwahati (21)

**Top 5 Popular Cuisines**

- North Indian (38 %)
- Chinese (26.2 %)
- Fast Food (19 %)
- Mughlai (9.5 %)
- Italian (7.3 %)

---
