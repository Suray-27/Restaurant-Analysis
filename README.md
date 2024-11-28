# Restaurant-Analysis

📌 ***Purpose of the Study***

<p> This study aims to provide insights into customer preferences and factors influencing restaurant performance.</p>

🎯 ***Objectives of the Study***

1. **Price Segments and Online Delivery:** Analyze whether online delivery services are more prevalent in the low-price segment or the high-price segment of restaurants.
2. **Table Booking and Ratings:** Investigate whether restaurants offering table booking facilities tend to have higher customer ratings.
3. **Cuisines and Ratings:** Explore how different cuisines(`Single` or `Multiple`) influence restaurant ratings.
4. **Popular Cuisines:** Identify the most popular cuisines based on customer preferences.
5. **Cuisine Impact on Ratings:** Determine if any specific type of cuisine has a significant impact on the overall rating of restaurants.
6. **Optimizing Predictive Models:** Evaluate and identify the best machine learning model for predicting restaurant ratings.

📊 ***Key Performance Indicators (KPIs)***

- Percentage of restaurants offering online delivery by price segment.  
- Average ratings of restaurants with and without table booking facilities.  
- Correlation coefficient between cuisines and restaurant ratings.  
- Identify popular cuisines based on votes.  
- Rating trends across specific cuisine types to determine their impact.

---

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
- I removed the `Locality Verbose` column, as it is a concatenation of the `City` and `Locality` columns, making it redundant. Keeping this column was unnecessary since the same information can be derived from the existing columns.
- I optimized the dataset by converting columns with an `object` data type to the `category` data type for those that have more than one unique value and six or fewer unique values. This conversion reduces memory usage and enhances processing efficiency while preserving the data's categorical nature.

---

***EDA (Exploratory Data Analysis)***

---

**Distribution**

- Votes is Right skewed data.
- Aggregate rating has outlier, more number of 0 rating.

**Number of Restaurants based on countries**

> There are `15 countries` in this Dataset.

<p> India has the highest number of restaurants in the dataset, followed by the United States.</p>

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

**Top 10 Cuisines by city with Highest Number of Restaurants**

* This chart clearly shows that `North Indian cuisine` is particularly popular in restaurants in `New Delhi`.
* In `New Delhi`, apart from `North Indian cuisine`, other popular cuisines include `Chinese`, `Fast Food`, `Mughal`, `Bakery`, `South Indian`, and `Street Food`.
* The Cities featuredin the `Top 10 Cuisines by City with the Highest Number of Restaurants` are all located in `India`.

**Online Delivery Availablity by Price Range**

- A low proportion of restaurants in the `high-price (4)` segment offer online delivery.
- `41%` of restaurants in the `price segment 2` provide online delivery.
- The `price segment 2` has approximately `1,276 restaurants` offering online delivery, which is the highest among all price segments.
- The `price segment 4` has fewer restaurants overall, and even fewer offering online delivery. However, the online deliveries in this segment are concentrated in `urbanized cities`.


> Only `5%` of restaurants offer both `table booking` and `online delivery` facilities.

**Average ratings of restaurant based on table booking facility**

> `Restaurants offering table booking` tend to have `higher ratings` compared to those that do not provide this facility.

**Correlation between `Has table booking` and `Aggregate rating`**

- `Restaurants offering table reservations` tend to receive `higher customer ratings`.
- However, the relationship between these two variables is `very weak`, indicating that additional factors should be considered to derive more reliable insights.


**Correlation between Location and Aggregate rating**

- Initially, there was no correlation found between location and aggregate rating.
- To address this, I utilized the `geopy` library to `fix reference points` and explore potential correlations more effectively.
- The heatmap suggests a `very weak negative correlation` between `Aggregate rating` and `Distance to reference`.
- It shows that restaurants closer to the reference point (capital coordinates) tend to have higher aggregate ratings.
- However, due to the weak correlation between these two variables, we need to consider additional factors to draw more reliable insights.

**Analysis based on `Single` and `Multiple` Cuisines offering restaurants**
`
- The `t-test` reveals a significant difference between restaurants offering `single cuisine` and those offering `multiple cuisines`.

> Cohen's d test for practical significance.

- The `Cohen's d` analysis indicates that restaurants offering `single cuisine` tend to have `lower ratings` compared to those offering `mixed cuisines`.


**Top 10 Most popular cuisines by votes**

- The graph clearly illustrates that the combination of `North Indian` and `Mughal cuisines` is the most popular among customers.
- Specifically, `North Indian cuisine` stands out as the top choice for customers.

> Does offering `American cuisine` lead to `higher ratings` based on customer votes?

- The analysis indicates that `American cuisine` is more frequently offered compared to other cuisines.
- A `t-test` reveals a significant difference in ratings between restaurants offering American cuisine and those that do not.
- The `Cohen's d` results confirm that restaurants with `American cuisine` have higher ratings than those without it.

**Key Note** <p>This `Aggregate rating` and `Votes` are not only based on `Cuisines` it should be based on `Restaurant's ambience, services and many factors` so we need more information to get more accurate insight.</p>

---

***Machine Learning***

---

**Data Preprocessing**

- Data Encoding (`Label Encoder`,`One Hot Encoder` and `Frequency encoding`) for Categorical Data.
- Removed Unwanted and Non Encoded columns after being Encoded.
- Scaling the Dataset by `Standardization` Technique.

**Target Variable** is `Aggregate rating`.

**Models**

- Linear Regression Model
- Random Forest Regression
- Decision Tree Regression
- k - Nearest Neighbors Regression

**Model Comparision**

* `Random Forest Regression` outperforms other models with a `low error value` and a strong `R² value`.
* Based on the analysis, `Random Forest Regression` is identified as the `best model` for this dataset.

---

📈 ***Key Insights***

---

- `Online delivery` appears to be influenced more by cities with `high populations`, `job opportunities`, and `urbanization`, rather than price segments.
- Restaurants with a `table booking facility` consistently achieve higher customer ratings.
- Offering `multiple cuisines` significantly enhances restaurant ratings.
- `North Indian cuisine` emerges as the most popular choice among customers.
- Including `American cuisine` contributes to improved restaurant ratings.

---

💡 ***Suggestions***

---

1. **Enhance Ratings Through Table Booking:** Implementing a table booking facility can significantly boost restaurant ratings and improve customer satisfaction.
2. **Leverage Multiple Cuisine Options:** Restaurants should consider offering `multiple cuisine` options, ensuring that `North Indian` and `American cuisines` are included to achieve higher ratings and attract a broader audience.

---

🔍 ***Further Directions***

---

- Develop a comprehensive project focused exclusively on `cuisine types` to identify and tailor the best cuisine varieties for different customer preferences.
- Incorporate `feature selection` methods in the modeling process to enhance predictive accuracy and uncover the most significant factors influencing restaurant ratings.

---