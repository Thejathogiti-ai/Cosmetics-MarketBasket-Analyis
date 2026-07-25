# Cosmetics-MarketBasket-Analyis

Cosmetics Market Basket Analysis using Apriori
Project Overview
Retailers often want to know which products customers tend to purchase together so they can improve product placement, create bundle offers, and recommend complementary products.
In this project, I performed Market Basket Analysis (MBA) on a cosmetics transaction dataset using the Apriori algorithm. The objective was to discover frequent product combinations and generate association rules that reveal purchasing patterns.
Instead of predicting an outcome, this project focuses on finding relationships between products based on customer transactions.
Business Problem
A cosmetics retailer wants to answer questions such as:
Which products are frequently purchased together?
Which items should be recommended during checkout?
Which combinations can be bundled for promotional campaigns?
Which products should be placed close to each other to increase sales?
Answering these questions helps improve customer experience while increasing cross-selling opportunities.
Dataset
The dataset consists of customer transactions where each cosmetic product is represented as a Yes/No value indicating whether it was purchased in that transaction.
Each row represents one customer's purchase, while each column represents a product category.
Project Workflow
1. Data Exploration
The dataset was loaded and examined to understand its structure.
Initial checks included:
Dataset information
Missing value verification
Basic inspection of transactions
No missing values required treatment before analysis.
2. Transaction Analysis
To better understand purchasing behavior, I calculated the total number of items purchased in each transaction.
This helped visualize how many products customers typically buy in a single purchase.
A count plot was created to observe the distribution of basket sizes.
3. Transaction Formatting
Association Rule Mining requires transactions in list format rather than Yes/No columns.
The dataset was therefore converted into transaction records where each customer transaction contains only the products marked "Yes".
Example:
Instead of
Lipstick
Eyeliner
Brushes
Yes
No
Yes
it becomes
['Lipstick', 'Brushes']
4. Transaction Encoding
The transaction lists were transformed using TransactionEncoder from mlxtend.
This converted the transactions into the one-hot encoded format required by the Apriori algorithm.
5. Frequent Itemset Generation
The Apriori algorithm was applied to identify frequently occurring product combinations.
Configuration used:
Minimum Support = 0.001
Maximum Itemset Length = 3
This generated all item combinations meeting the support threshold.
6. Association Rule Mining
Using the frequent itemsets, association rules were generated and ranked using Lift.
The following evaluation metrics were used:
Support – How frequently a product combination appears in the dataset.
Confidence – Probability that customers purchase the consequent when they purchase the antecedent.
Lift – Measures how much stronger the relationship is compared to random chance. Higher lift indicates a more meaningful association.
7. Rule Filtering
To identify stronger recommendations, the generated rules were filtered using:
Confidence > 0.10
Lift > 3.0
This removed weaker relationships and retained only the more significant product associations.
The analysis also specifically examined rules where the recommended product was:
Eyeliner
Brushes
to identify products that strongly influence purchases of these items.
Results
The Apriori algorithm successfully identified frequent product combinations and generated association rules based on customer purchasing behavior.
By filtering rules using higher confidence and lift values, the analysis highlighted stronger product relationships that are more useful for recommendation systems and retail decision-making.
The targeted analysis for Eyeliner and Brushes demonstrated how association rules can be used to recommend specific products based on items already present in a customer's shopping basket.
Business Implications
The discovered association rules can support several retail strategies:
Recommend complementary cosmetic products during checkout.
Design product bundles to increase average order value.
Improve shelf placement by positioning frequently purchased products together.
Create targeted promotional campaigns based on customer purchasing patterns.
Enhance recommendation engines for online cosmetic stores.
Technologies Used
Python
Pandas
NumPy
Matplotlib / Seaborn
mlxtend
Apriori Algorithm
Association Rule Mining
TransactionEncoder
Key Learning Outcomes
Through this project, I learned how to:
Convert transactional data into a format suitable for association rule mining.
Apply the Apriori algorithm to discover frequent itemsets.
Generate association rules from frequent itemsets.
Interpret Support, Confidence, and Lift to evaluate product relationships.
Filter rules to identify stronger and more actionable business insights.
Translate association mining results into practical retail recommendations.
