#### Brief Summary of Market Basket Analysis Project

**Objective**: The Market Basket Analysis project identifies frequently purchased product combinations, uncovers hidden relationships, and informs business strategies like product placement, promotions, and inventory management using SQL, Power BI, and Excel.

**Steps and Execution**:
1. **Data Preparation (Excel)**:
   - Start with a transactional dataset (e.g., `TransactionID`, `CustomerID`, `Product`, `Date`).
   - Clean data in Excel (remove duplicates) and pivot it into a basket format (rows: transactions, columns: products, values: 1 if purchased, 0 if not).
   - Example: Milk and Bread purchased together in Transaction 1 → `[Milk: 1, Bread: 1]`.

2. **Aggregation (SQL)**:
   - Import data into a SQL database (e.g., SQLite).
   - Query to count product pairs bought together (e.g., `SELECT Product1, Product2, COUNT(*) AS Frequency`).
   - Filter for pairs with sufficient frequency (e.g., ≥2 transactions) to identify common itemsets.

3. **Association Rules (Python, Optional)**:
   - Use the Apriori algorithm (`mlxtend` library) on the basket data to find frequent itemsets and generate association rules.
   - Calculate metrics:
     - **Support**: % of transactions containing an itemset (e.g., Cereal and Milk in 60% of transactions → Support = 0.6).
     - **Confidence**: Likelihood of buying the consequent given the antecedent (e.g., if Cereal, 100% buy Milk → Confidence = 1.0).
     - **Lift**: Strength of the rule (Lift > 1 means positive correlation, e.g., Cereal → Milk, Lift = 1.667).

4. **Visualization (Power BI)**:
   - Import SQL results (frequent itemsets) and Python outputs (association rules).
   - Create visuals: bar charts for pair frequencies, tables for rules (support, confidence, lift), and slicers for filtering.
   - Build an interactive dashboard to present insights.

5. **Business Insights (Excel)**:
   - Summarize findings: e.g., Cereal and Milk are frequently bought together (Support = 0.6, Lift = 1.667).
   - Recommend strategies: place Cereal and Milk together, offer bundled promotions, and stock more Milk during peak times.

**Calculation Overview**:
- **Support** = (# transactions with itemset) / (total transactions). Example: 3/5 transactions have Cereal and Milk → Support = 0.6.
- **Confidence** = (# transactions with antecedent and consequent) / (# transactions with antecedent). Example: All Cereal transactions include Milk → Confidence = 3/3 = 1.0.
- **Lift** = Confidence / (Support of consequent). Example: Confidence (Cereal → Milk) = 1.0, Support (Milk) = 0.6 → Lift = 1.0 / 0.6 = 1.667.

**Deliverables**:
- Excel: Cleaned data, basket format, and insight report.
- SQL: Queries for frequent itemsets.
- Python: Association rules with metrics.
- Power BI: Dashboard with visuals.

This process identifies purchase patterns (e.g., Cereal → Milk) and translates them into actionable strategies, calculated using support, confidence, and lift to quantify relationships.# Elitetech
Project repository for EliteTech internship tasks
