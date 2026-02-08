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
