## Problem Definition
**Business Context**

The business is a home appliances retail company operating across multiple districts in Rwanda, selling products such as refrigerators, washing machines, cookers, and other household electronics. The sales department manages customer purchases across regions including Gasabo, Kicukiro, Nyarugenge, and other districts.

**Data Challenge**

Management has large volumes of transactional sales data but lacks structured analytical insights. They need to understand which products perform best in each region, how customer purchasing behavior differs, and how sales quantities vary across customers and products to support data-driven decisions.

**Expected Outcome**

The analysis will provide actionable insights to support regional sales optimization, customer segmentation, and product performance evaluation, enabling better inventory planning and targeted marketing strategies.

## **Success Criteria (Measurable Goals)**

Identify the top 5 best-selling products per region using ranking window functions such as RANK() or DENSE_RANK() to support regional inventory planning.

1. Calculate cumulative sales quantities per product across regions using SUM() OVER() to understand overall product demand trends.

2. Analyze changes in customer purchase quantities by comparing previous and current sales using navigation functions like LAG() to detect growth or decline patterns.

3. Segment customers into four performance groups based on total quantity purchased using NTILE(4) to enable customer-focused marketing strategies.

4. Compute average sales quantities across regions using AVG() OVER() to evaluate regional performance consistency and identify underperforming areas.


## **Database Structure Description**

The database consists of multiple related tables, including:

**Customers table** – stores customer details such as customer ID and name

**Products table** – contains product information such as product ID and product name

**Regions/Districts table** – records geographical areas where sales occur

**Sales table** – stores transaction records including customer ID, product ID, region, quantity sold, and sales date

Each sale links a customer, a product, and a region, making joins necessary to combine meaningful business information.

![image alt](https://github.com/NGENZ1/plsql_window_function-_29111_HIRWA/blob/main/ASSIGNMENT.jpg)


## JOINS USED

**Inner Join**

**Description:**
An INNER JOIN retrieves only the records that have matching values in both tables being joined.

**Business Meaning:**
This join ensures that only valid and complete records are analyzed. For example, a sale is only included if it is linked to an existing customer and product.

**Why It Is Important**:

> Eliminates incomplete or orphan records

> Produces accurate and reliable reports

> Ensures consistency across business data

**LEFT JOIN (LEFT OUTER JOIN)**

**Description:**
A LEFT JOIN returns all records from the left table and only the matching records from the right table. If there is no match, the result still includes the left table’s data with null values for the right table.

**Business Meaning:**
This join helps identify records that exist in one table but have no related records in another table, such as customers who have not yet made a purchase.

**Why It Is Important**:

> Helps identify inactive or missing relationships

> Useful for customer follow-up and marketing

> Supports completeness analysis

**RIGHT JOIN (RIGHT OUTER JOIN)**

**Description:**
A RIGHT JOIN returns all records from the right table and only the matching records from the left table.

**Business Meaning:**
This join is useful when the business wants to ensure that all records from a reference table (such as products or regions) appear in the analysis, even if no transactions have occurred.

**Why It Is Important:**

> Highlights products or regions with no sales

> Supports inventory and strategic planning

> Ensures full visibility of business entities

**FULL JOIN (FULL OUTER JOIN)**

**Description:**
A FULL JOIN returns all records when there is a match in either table. Records without matches in one table still appear with null values.

**Business Meaning:**
This join provides a complete view of data from both tables, showing both matched and unmatched records.

**Why It Is Important:**

> Identifies data gaps

> Useful for audits and data quality checks

> Ensures no information is overlooked

**CROSS JOIN**

**Description**:
A CROSS JOIN produces a Cartesian product, meaning each record from one table is combined with every record from another table.

Business Meaning:
This join is often used for simulations, scenario analysis, or generating combinations such as pairing products with regions for forecasting purposes.

**Why It Is Important:**

> Supports planning and forecasting models

> Useful for testing and analysis scenarios

> Helps explore all possible combinations

**Window Functions Analysis**

Window functions are used to perform calculations across related rows while keeping individual row details intact. This is crucial for business analytics.

**Ranking Products by Sales per Region**

**RANK()**

**Description:**
Assigns a rank to rows within a group based on a specified order. Ties receive the same rank, and gaps appear in ranking.

**Business Purpose:**

> Identifies top-performing products or customers

> Supports competitive performance analysis

> Highlights leaders within categories

## **Cumulative Sales Analysis**

**Description**:
Calculates a running or cumulative total over a defined window of rows.

**SUM() OVER()**

**Business Purpose:**

> Track overall product demand

> Identify products with consistently high sales

> Support long-term stock and supplier decisions

## **Customer Purchase Trend Analysis**

**LAG()**

**Description:**
Accesses data from a previous row within the same partition.

**Business Purpose:**

Detect increases or decreases in customer spending

Identify loyal or declining customers

Support targeted promotions and retention strategies

## **Customer Segmentation**

**NTILE(4)**

**Description:**
Customers are divided into four groups based on total purchase quantity.

**Business Purpose:**

> Identify top-performing customers

> Design loyalty programs

> Apply different marketing strategies for each segment

## **Regional Performance Evaluation**

**AVG() OVER()**

**Description:**
Calculates the average sales quantity per region while still displaying individual sales records.

**Business Purpose:**

> Compare regions against the average

> Identify underperforming regions

> Support regional sales improvement strategies

**Overall Business Value of the Analysis**

By combining joins and window functions, the company achieves:

Improved data accuracy

Better sales forecasting

Enhanced customer segmentation

Informed inventory and marketing decisions

This analytical approach transforms raw transactional data into actionable business insights.

## Conclusion

The use of relational joins enables meaningful data integration, while window functions provide advanced analytical capabilities without losing row-level detail. Together, these techniques empower the business to make data-driven decisions, optimize operations, and improve overall performance.

All sources were properly cited. The implementations and analysis represent original work. No AI-generated content was copied without attribution or adaptation.

![WhatsApp Image 2026-02-08 at 23 55 37](https://github.com/user-attachments/assets/61e58c89-c9cf-492b-8ed0-0c37ca4f1146)

![WhatsApp Image 2026-02-08 at 23 55 37 (2)](https://github.com/user-attachments/assets/b55ce874-a7d6-40fa-8e91-818006338db7)

![WhatsApp Image 2026-02-08 at 23 55 37 (1)](https://github.com/user-attachments/assets/e42e65b9-a7ce-43bc-a914-54748a0186cf)

![WhatsApp Image 2026-02-08 at 23 57 50](https://github.com/user-attachments/assets/f8cdce70-adef-4bb8-a751-cfff2f8f039b)


