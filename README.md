# FoodHub-Case-Study
## Business Context
The number of restaurants in New York is increasing day by day. Lots of students and busy professionals rely on those restaurants due to their hectic lifestyles. Online food delivery service is a great option for them. It provides them with good food from their favorite restaurants. A food aggregator company FoodHub offers access to multiple restaurants through a single smartphone app. The app allows restaurants to receive a direct online order from a customer. The app assigns a delivery person from the company to pick up the order after it is confirmed by the restaurant. The delivery person then uses the map to reach the restaurant and waits for the food package. Once the food package is handed over to the delivery person, he/she confirms the pick-up in the app and travels to the customer's location to deliver the food. The delivery person confirms the drop-off in the app after delivering the food package to the customer. The customer can rate the order in the app. The food aggregator earns money by collecting a fixed margin on the delivery order from the restaurants.

## Objective
The food aggregator company has stored the data of the different orders made by the registered customers in their online portal. They want to analyze the data to get a fair idea about the demand of different restaurants which will help them in enhancing their customer experience. Suppose you are hired as a Data Scientist in this company and the Data Science team has shared some of the key questions that need to be answered. Perform the data analysis to find answers to these questions that will help the company improve its business.

## Data Dictionary
- order_id: Unique ID of the order
- customer_id: ID of the customer who ordered the food
- restaurant_name: Name of the restaurant
- cuisine_type: Cuisine ordered by the customer
- cost_of_the_order: Cost of the order
- day_of_the_week: Indicates whether the order is placed on a weekday or weekend (The weekday is from Monday to Friday and the weekend is Saturday and Sunday)
- rating: Rating given by the customer out of 5
- food_preparation_time: Time (in minutes) taken by the restaurant to prepare the food. This is calculated by taking the difference between the timestamps of the restaurant's order confirmation and the delivery person's pick-up confirmation.
- delivery_time: Time (in minutes) taken by the delivery person to deliver the food package. This is calculated by taking the difference between the timestamps of the delivery person's pick-up confirmation and drop-off information

## Tools Used
- **Pandas**: for data manipulation
- **Matplotlib & Seaborn**: for data visualization

## Project:
Project was part of **Post Graduate Program in Artificial Intelligence and Machine Learning** from *University of Texas at Austin* delivered via *Great Learning*.
[Project link:] (https://www.mygreatlearning.com/eportfolio/samyuktha25)


##  Conclusions
###  Data Overview
- The dataset contains 1,898 rows and 9 columns.
- 5 columns are of numeric datatype, while 4 columns are of object datatype.
- No missing values were found; however, 736 orders do not have customer ratings.
- Missing ratings were imputed using the median value and stored in a new numeric column for further analysis.
- Summary statistics revealed key metrics for numerical features:
- - cost_of_the_order: Minimum, average, and maximum values
- - food_preparation_time: Minimum, average, and maximum values
- - delivery_time: Minimum, average, and maximum values
- - cost_of_the_order is positively skewed, as the mean is greater than the median.
- No duplicate entries were found in the dataset.

###  Exploratory Data Analysis (EDA)
#### Univariate Analysis
##### Distribution Analysis of Numerical Data:

- **cost_of_the_order data** is *positively skewed* implies many customers place small orders, but occasionally, a few large orders, pulling the mean to the right (from histogram plot of order cost).

- **food_preparation_time** is more or less *uniformly distributed* impliying it takes almost same time to prepare every order with occational splikes.(from histogram plot of food preparation time).

- **Delivery time** data is almost *uniformly distributed* with occational peak times(from histogram plot of delivery time).

- Majority of orders are **highly rated** (4, 5) as evident from countplot.

- **Top 5 restaurants** by number of orders: Shake Shack, The Meatball Shop, Blue Ribbon Sushi, Blue Ribbon Fried Chicken, Parm
- **Most popular cuisines**:American, Japanese, Italian
- **Multi-cuisine restaurant**: *The Meatball Shop* serves both Italian and American cuisines.
- Weekend order volume is significantly higher — approximately **147% more than weekdays**.
- **High-value orders** (costing more than $20) account for *29.24%* of total orders.
- **Average delivery time** is approximately *24.16 minutes*.
- **Top 3 frequent customers eligible for 20% discount:**
- - Customer ID 52832 – 13 orders
- - Customer ID 47440 – 10 orders
- - Customer ID 83287 – 9 orders

#### Multivariate Analysis
**No significant correlation between:**
- order cost and delivery time
- order cost and food preparation time
- food preparation time and delivery time
- None of the columns in the data correlate with each other(from correlation matrix heatmap).

**Food Preparation Time across different cuisines(Box Plots)**
- Korean cuisine takes lesser time to prepare food as evident from how its data is spread.
- Thai cuisine had wider spread of data indicating it's preparation times significantly varies depending on the order.
- Remaining cuisines more or less has similar data spreads ie., similar food preparation time.

**Order Cost Across Different Cuisines(Box Plots)**
- Order value of vietnamese cuisine is low. Very few outliers. Also, data is negatively skewed implying most of it costed very less.
- Korean cuisine is a typical low value order as it has narrow spread and few large orders occationaly.
- Southern cuisine has wider spread indicating order cost varied signifcately as per different orders.
- Mediterranean cuisine orders costed moderately with some large value orders sometimes.
- Remaining cuisines more or less has similar cost range ( 11− 24)

**Cuisine Type Vs. Total Delivery Time**
- There is not much impact of cuisine type on total time taken to deliver the order since it is placed.

**7 restaurants are eligible for promotional offers based on performance:** Blue Ribbon Fried Chicken, Blue Ribbon Sushi, Parm, RedFarm Broadway, RedFarm Hudson, Shake Shack, The Meatball Shop

**Total revenue generated** (based on order commission): *$6,166.30*

**10.54%** of the orders took *more than 60 minutes* (from order placement to delivery).

**Weekday** deliveries are, on average, *6 minutes longer* than weekend deliveries.

## Recommendations
**1. Business Growth & Marketing**
- Weekend Promotions: Launch “Weekend Combo Deals” and send peak-hour flash offers to capitalize on ~147% weekend order spike.
- Loyalty Program: Reward top users (e.g., IDs 52832, 47440, 83287) with gamified perks, personalized combos, and referral bonuses.
- High-Value Orders: Promote order-threshold rewards and upsell combos to boost revenue from 30%+ orders over $20.

**2. Restaurant Strategy**
- Promote Top Performers: Feature restaurants like Shake Shack, Blue Ribbon, and The Meatball Shop more prominently.
- Menu Expansion: Encourage dual/multi-cuisine offerings and test fusion items using A/B testing.
- Cuisine Focus: Onboard more American and Japanese cuisine restaurants, ensuring geographic spread.

**3. Operations & Delivery**
- Weekday Delays: Optimize delivery shifts and use real-time routing to cut weekday delays (~6 mins longer).
- Late Orders: Analyze 10.54% of >60 min orders; offer real-time alerts and apology coupons.
- Prep Time Benchmarking: Help slower kitchens (e.g., Thai) improve by sharing efficient practices from faster ones (e.g., Korean).

**4. Customer Experience**
- Improve Feedback: Incentivize order ratings and use NLP for review sentiment analysis.
- Transparency: Show real-time status updates and cuisine-specific delivery estimates to set accurate expectations.

**5. Financial Optimization**
- Dynamic Commission Tiers: Reward fast, high-rated, high-volume restaurants with lower commissions.
- Smart Ad Spend: Allocate marketing budget to high-ROI partners with great service and satisfaction.
- Low-Value Cuisine Strategy: Promote add-ons and offer free delivery thresholds to increase Korean/Vietnamese order value.
