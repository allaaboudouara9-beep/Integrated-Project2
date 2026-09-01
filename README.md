# 🛒 Retail Product Recommendation & Customer Transaction Analysis

## 📌 Project Overview

This project analyses **retail product and customer transaction data** using machine learning, recommendation systems, and market basket analysis.

The project investigates customer purchasing behaviour and explores how different recommendation approaches can be used to suggest relevant products.

Three recommendation approaches were implemented:

* 🏷️ Content-Based Filtering
* 🔗 Item–Item Based Recommendation
* 👥 User–User Based Recommendation

Market basket analysis was also performed using:

* 🛒 Apriori
* ⚡ FP-Growth

Finally, an interactive **retail analytics dashboard** was designed with accessibility in mind, particularly for users aged **65 and over**.

---

# 📂 Datasets

Two datasets were used in this project:

### 🧾 Transaction Dataset

Contains household-level retail transaction information, including features such as:

* 🛒 Basket ID
* 🕐 Transaction Time
* 🏠 Household information
* 🛍️ Product purchases

Original size:

**2,595,732 rows × 12 columns**

### 📦 Product Dataset

Contains information describing the products purchased by customers.

Original size:

**92,353 rows × 7 columns**

The datasets were combined because each contained complementary information required for the recommendation analysis.

---

# 🧹 Data Preparation

The original datasets were large, so data reduction was performed to improve computational efficiency.

A sample containing approximately **10,000 unique baskets** was selected from the transaction dataset.

Additional preprocessing included:

* 🗑️ Removing empty baskets
* 📉 Removing unpopular products
* 🔗 Merging transaction and product information
* 🧹 Reducing unnecessary data
* ⚙️ Preparing data for recommendation algorithms
* 🛒 Preparing basket data for Apriori and FP-Growth

Reducing the dataset helped decrease execution time and improve the scalability of the recommendation and association-rule algorithms.

---

# 🛠️ Feature Engineering

Several additional features were created to improve the recommendation analysis.

### 📝 Product Text

Provides more detailed product descriptions so that products with similar characteristics can be identified.

### 🛒 Average Basket Size per Household

Measures the typical number of products purchased by a household during a transaction.

### 💰 Household Spending

Represents the amount spent by each household and provides information about customer purchasing behaviour.

### 🔄 Household Purchase Frequency

Measures how frequently households make purchases.

This can help distinguish:

* ⭐ Loyal customers
* 🔄 Frequent shoppers
* 💤 Infrequent shoppers

### 🔥 Product Popularity

Measures how frequently products are purchased across households.

### 🤝 Interaction Score

Combines customer and product interaction information to represent the strength of the relationship between households and products.

---

# 🤖 Recommendation Systems

Recommendation systems help customers discover products that may be relevant to their preferences and purchasing behaviour.

From a business perspective, they can potentially support:

* 💰 Sales
* ❤️ Customer retention
* 🤝 Customer engagement
* 🔍 Product discovery
* 🎯 Personalisation

Three recommendation approaches were explored in this project.

---

# 🏷️ Content-Based Filtering

Content-Based Filtering recommends products by examining their characteristics and identifying similar items.

In this project, a private-brand **Granola Bar** from the *Convenient Breakfast/Wholesome Snacks* category was used as an example.

The recommendations belonged to similar product categories and subcategories.

### ✅ Advantage

The model successfully generated recommendations that were highly relevant to the characteristics of the original product.

### ⚠️ Limitation

Content-Based Filtering can sometimes produce recommendations that are **too similar**.

This may reduce recommendation diversity and limit opportunities for customers to discover products outside their existing preferences.

---

# 🔗 Item–Item Based Recommendation

The Item–Item recommendation system identifies relationships between products based on customer purchasing behaviour.

Rather than focusing only on product descriptions, it investigates which products are associated through household purchasing patterns.

For the Granola Bar example, the analysis identified a strong similarity score of approximately:

### 🎯 0.829

Other products demonstrated different levels of similarity.

Another example used **Sandwich Cookies** as the original product.

The reported recommendations included:

| 🛍️ Product             | 🔗 Similarity Score |
| ----------------------- | ------------------: |
| 🥩 Beef                 |           **0.632** |
| 🥑 Avocado              |           **0.591** |
| 🥤 Soft Drinks          |           **0.492** |
| 🌮 Tortilla/Nacho Chips |           **0.489** |
| 🍓 Frozen Fruit         |           **0.480** |

These results demonstrate how collaborative purchasing behaviour can generate recommendations across different product categories.

---

# 👥 User–User Based Recommendation

User–User recommendation identifies households with similar purchasing behaviour.

The system first identifies similar users and then recommends products purchased by those similar households that may be relevant to the target household.

This approach uses collective customer behaviour rather than relying exclusively on product characteristics.

---

## 🏠 Household 2375

Recommendations included:

* 🍎 Value Added Fruit
* 🥗 Salad Bar Fresh Fruit
* 🥬 Pourable Salad Dressings
* 🥔 Potatoes
* 🧃 Juice

These recommendations suggest a customer segment associated with fresh produce and complementary grocery products.

---

## 🏠 Household 1130

Recommendations included:

* 🥚 Eggs
* 🧁 Snack Cakes
* 🧃 100% Pure Juice
* 🍗 Chicken Drums
* 🥫 Salad Mustard

These recommendations combine staple groceries, meal ingredients, snacks, and beverages associated with households displaying similar purchasing behaviour.

---

# ⚖️ Recommendation Model Comparison

Each recommendation approach provides different advantages.

### 🏷️ Content-Based Filtering

**Focus:** Product characteristics

✅ Useful for recommending products similar to the selected item.

⚠️ May provide limited recommendation diversity.

### 🔗 Item–Item Recommendation

**Focus:** Relationships between products

✅ Useful for identifying products associated through purchasing behaviour.

### 👥 User–User Recommendation

**Focus:** Similar customers/households

✅ Provides a higher level of personalisation by using the purchasing behaviour of similar customers.

Overall, all three approaches generated relevant recommendations but approached the recommendation problem differently.

---

# 🛒 Market Basket Analysis

Market basket analysis was conducted using:

### 🧺 Apriori

and

### ⚡ FP-Growth

The objective was to identify **frequently purchased product combinations** and compare the performance of the two algorithms.

Both algorithms identified:

### 🎯 280 frequent itemsets

This means both methods identified the same number of frequent purchasing patterns within the analysed sample.

---

# ⚡ Apriori vs FP-Growth

The major difference between the two algorithms was execution time.

| Algorithm   | ⏱️ Execution Time | 🛒 Frequent Itemsets |
| ----------- | ----------------: | -------------------: |
| Apriori     |        1.8682 sec |                  280 |
| ⚡ FP-Growth |    **1.4186 sec** |                  280 |

FP-Growth was approximately:

### 🚀 24% faster

than Apriori while identifying the same number of frequent itemsets.

### 🏆 Faster Algorithm: FP-Growth

Based on this experiment, FP-Growth provided better computational efficiency and may therefore be more suitable when scaling market basket analysis to larger retail datasets.

---

# 📊 Retail Analytics Dashboard

An interactive dashboard was developed to present important insights from the retail dataset.

A major design objective was:

### 👴👵 Accessibility for users aged 65+

The dashboard was designed to make complex retail information easier to understand without requiring users to manually analyse large datasets.

---

# ♿ Accessibility & Usability

The dashboard was designed with simplicity as a priority.

Potential benefits include:

### 🧠 Improved Data Understanding

Visualisations make purchasing patterns and product distributions easier to interpret.

### 💼 Decision-Making Support

Retail managers can use the displayed information to support decisions related to:

* 📣 Marketing
* 🏷️ Promotions
* 📦 Inventory
* 🛒 Products

### ⏱️ Time Saving

Users can quickly access important insights without manually examining thousands of transaction records.

### 🤖 Machine Learning Results

Recommendation outputs can be displayed and evaluated through the dashboard.

### 👥 Customer Behaviour

The visualisations help highlight shopping patterns, product popularity, and purchasing trends.

---

# 🛍️ Example Products

Four example products were selected for the dashboard:

### 🍌 Bananas

Represents a popular fresh-food product.

### 🍫 Granola Bars

Represents convenient and health-conscious snack purchases.

### 🍜 Ramen Noodles

Represents inexpensive packaged staple foods.

### 🥤 Soft Drinks

Represents beverages commonly associated with different food purchases.

These products were selected to provide examples across different product categories rather than because they necessarily achieved the highest model performance.

---

# 🎛️ Dashboard Controls

To reduce complexity, the dashboard contains a small number of controls.

### 🔽 Select Product

Allows users to choose the product they want to investigate.

### ✨ Generate Recommendations

Runs the recommendation system and displays products related to the selected item.

### 🧹 Clear Charts

Returns charts and visualisations to their original state.

### 🚪 Exit

Closes the dashboard application.

The limited number of controls was intended to reduce cognitive load and make navigation straightforward.

---

# 📊 Dashboard Visualisations

The dashboard includes several visualisations.

## 📊 Bar Chart

The bar chart displays products frequently appearing in recommendation outputs.

The example visualisation includes:

🥇 Bananas
🥈 Soft Drinks
🥉 Granola Bars
🍜 Ramen Noodles

The chart allows users to compare recommendation frequencies easily.

---

## 📈 Line Chart

The line chart displays changes in product purchases over time.

The example dashboard shows monthly purchases from **January to June**, with purchases increasing from approximately **20 to 60**.

The visualisation provides a simple representation of changes in customer activity over the displayed period.

---

## 🥧 Pie Chart

The pie chart presents the distribution of products across retail departments.

The example dashboard indicates approximately:

### 🛒 Grocery — 45%

### 🥬 Produce — 25%

Other categories, including beverages and frozen foods, represent smaller proportions.

This provides users with a simple overview of the composition of the displayed retail data.

---

# 🔑 Key Findings

The main findings from this project include:

* 🏷️ Content-Based Filtering successfully identified products with similar characteristics.
* 🔗 Item–Item recommendations identified relationships between products using purchasing behaviour.
* 👥 User–User recommendations provided personalised suggestions based on similar households.
* 🎯 Several recommendation examples produced relatively strong similarity scores.
* 🛒 Apriori and FP-Growth both generated **280 frequent itemsets**.
* ⚡ FP-Growth completed the analysis approximately **24% faster** than Apriori.
* 📊 Retail visualisations helped communicate customer behaviour and product patterns.
* ♿ The dashboard was designed with accessibility and simplicity as key priorities.
* 💡 Recommendation systems can provide useful information for both customers and retail businesses.

---

# 🛠️ Technologies & Techniques

This project uses concepts and techniques including:

* 🐍 Python
* 📓 Jupyter Notebook
* 🐼 Pandas
* 🔢 NumPy
* 🤖 Machine Learning
* 🏷️ Content-Based Filtering
* 🔗 Collaborative Filtering
* 👥 User–User Recommendation
* 🛒 Market Basket Analysis
* 🧺 Apriori
* ⚡ FP-Growth
* 📊 Data Visualisation
* 🖥️ Interactive Dashboard Design

---

# 🏁 Conclusion

This project demonstrates how **machine learning, recommendation systems, market basket analysis, and data visualisation** can be applied to retail transaction data.

Three recommendation approaches were explored: **Content-Based Filtering, Item–Item Recommendation, and User–User Recommendation**. Each model demonstrated different strengths, from identifying products with similar characteristics to providing personalised recommendations based on household purchasing behaviour.

Market basket analysis using **Apriori and FP-Growth** identified the same number of frequent itemsets. However, FP-Growth completed the analysis approximately **24% faster**, demonstrating greater computational efficiency in this experiment.

Finally, the retail analytics dashboard transformed the analysis into a more accessible visual format. Its simplified controls and visualisations were designed to make the results easier to understand, particularly for users aged 65 and above.

Overall, the project demonstrates how retail businesses can use customer transaction data to better understand purchasing behaviour, generate relevant product recommendations, and support data-driven decision-making. 🛒🤖📊✨
# Integrated-Project2
Machine Learning X Data Visualisation
