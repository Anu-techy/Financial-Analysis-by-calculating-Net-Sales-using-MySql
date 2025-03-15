# Financial Analysis by calculating Net Sales using MySql

**Aim**

1. Calculate net_invoice_sales using CTE (Common Table Expressions)
2. Calculate net_invoice_sales using Views
3. Calculate Net_sales using Views
4. Calculate Top markets by net sales in a given fiscal year
5. Calculate Top custoners by net sales in a given market, fiscal year
6. Calculate Top products by net sales for a given year.

======================================================================                            
**ETL (Extract Transform Load) Process**

Data is imported from Atliq Database

**Dimension tables:**

dim_customer (customer_code, customer, platform, market, sub_zone, region)

dim_product (product_code, division, segment, category, product, variant)

**Fact tables/Transaction tables:**

fact_sales_monthly (monthly aggregated data in start of the month date, product_code, customer_code, sold_quantity )

fact_freight_Cost (market, fiscal_year, freight_pct, other_cost_pct)

fact_gross_price (product_code, fiscal_year, gross_price)

fact_manufacturing_cost (product_code, cost_year/fiscal_year, manufacturing_cost)

fact_post_invoice_deductions (customer_code, product_code, date, discounts_pct, other_deductions_pct)

fact_pre_invoice_deductions (customer_code, fiscal_year, pre_invoice_discount_pct)

=======================================================================

**Common Table Expression (CTE)**

CTEs allow you to write modular queries to improve readability, making complex SQL statements easier to understand and maintain.

You can use the same CTE multiple times within a single query,

CTEs can be recursive, which is useful for queries that need to handle hierarchical or recursive data (e.g., finding all descendants in a tree structure).

Use a CTE when you need temporary, modular, and reusable logic within a single query. It's ideal for complex operations that can benefit from better query organization and clarity.

**View**

A View is a virtual table that stores a predefined SQL query in the database schema. When a query is executed on a view, the database runs the underlying query and returns the result as though it's a table.

A view is reusable across multiple queries and sessions.

Use a View when you need to encapsulate a complex query as a virtual table that will be used repeatedly across different queries, or when you need to provide simplified access to data for different users or applications.

========================================================

**Conclusion:**

Net sales provide a more accurate measure of a company’s revenue by factoring in returns, discounts, and allowances. Analyzing net sales is essential for:

1. Assessing business performance, profitability, and customer behavior

2. Informing financial decisions and forecasting

3. Identifying top markets, customers, and products to optimize strategies and resource allocation
