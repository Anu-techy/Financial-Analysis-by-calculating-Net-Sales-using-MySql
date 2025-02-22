# Financial Analysis by calculating Net Sales using MySql

**Aim**

1. Calculate net_invoice_sales using CTE (Common Table Expressions)
2. Calculate net_invoice_sales using Views
3. Calculate Net_sales using Views

**Description:**

**Atliq** is a hardware company which manufactures electronic hardware items like PC, Laptop, Hard Drive, mouse, Keyboards, pendrives etc It has operations all over the globe.

===========================================================
           
**Key Performance Indicators (KPIs) to calculate Profit and Loss Statement**

The **Gross Price** refers to the total price of a product or service before any deductions, such as taxes, discounts, or other costs, are subtracted.

A **Pre invoice Deductions** refers to a reduction or discount applied to the price of goods or services before the final invoice is issued.

**Net invoice sales** refers to the total amount of sales revenue that a company recognizes on an invoice after accounting for any deductions, such as discounts, allowances, returns, or any other reductions that might apply.

                                          Net invoice sales = Gross Price - Pre invoice Deductions
                                          
**Post invoice Deductions** are reductions made to the amount due on an invoice after it has been issued. These deductions usually occur after the sale has been completed and the invoice has been sent, and they can be due to various volumne discounts, returns, product defects, shipping delays etc.

**Net sales** refers to the total revenue a company generates from selling goods or services after accounting for all deductions such as discounts, returns, allowances, and any other adjustments. It represents the actual sales the company made and is an important metric for understanding the business's true revenue.

                                          Net Sales = Net invoice Sales - Post invoice Deductions
                                          
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
