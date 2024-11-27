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

**Top 10 Cuisines by city with Highest Number of Restaurants**

* This Chart clearly shows `North Indian` Cuisine is Famous in Restaurants at `New Delhi`.
* In `New Delhi` apart from North Indian cuisine there are multiple Cuisines are Famous like `Chinese`,`Fast Food`,`Mughal`,`Bakery`,`South Indian`and `Street Food`.
* The Cities got Placed in this `Top 10 Cuisines by City with the Highest Number of Restaurants` shows Every Cities are in `India`.

**Online Delivery Availablity by Price Range**

- A low proportion of restaurants in the high-price `(4)` segment offer online delivery.
- `41%` of restaurants in the `price segment 2` provide online delivery.
- The `price range 2` segment has `approximately 1,276 restaurants` offering online delivery, which is the highest among all segments.
- The `price range 4` segment has fewer restaurants overall and also fewer offering online delivery. However, these online deliveries are in this segment are concentrated in `urbanized cities`.
- Interestingly, `online delivery` seems to be less influenced by price segments and more by cities with `high populations`, `job opportunities`, and `urbanization`.

> Only 5% Restaurants offer both `Table booking` and `online Delivery` facility.

**Average ratings of restaurant based on table booking facility**

> Restaurants offering table booking tend to have higher ratings compared to those without this facility

**Correlation between `Has table booking` and `Aggregate rating`**

<p> Restaurants offering table reservations receive higher customer ratings, but it is a very week relationship between those two variables so we need to consider some other factors to get valid insights.</p>

**Correlation between Location and Aggregate rating**

> There is no Correlation between location and Aggregate rating. So I use `geopy` library to find correlation by fixing reference points.

<p>The heatmap suggests that there is very week negative correlation between "Aggregate rating" and "Distance to reference" but it says the restaurants near the reference point (Capital coordinates) Aggregate rating is increases, we need to consider some other factors to conclude better insights because of very week correlation between those two variables. </p>

**Analysis based on `Single` and `Multiple` Cuisines offering restaurants**

- T-test shows there is a difference between two groups.

> Cohen's d test for practical significance.

- Cohen's d results shows Restaurant with `Single` Cuisine has lower rating than Restaurant with `Mixed` Cuisines.

**Top 10 Most popular cuisines by votes**

- This Graph clearly shows combination of `North Indian and Mughal` Cuisines are most popular.
- In specific `North Indian` Cuisines is more popular among the customers.

> Is Restaurant offering `American` Cuisine particularly getting Higher rating based on Votes?

- The above analysis shows `American` Cuisine is more repetitive than other cuisines.
- T test shows there is a Difference between Restaurant with `American` Cuisine and non-american cuisine.
- Cohen's d results shows that Restaurant with `American` Cuisine has more rating than Restaurant without American cuisine.

**Key Note** <p>This `Aggregate rating` and `Votes` are not only based on cuisines it should be based on `Restaurant's ambience, services and many factors` so we need more information to get more accurate insight.</p>



---
