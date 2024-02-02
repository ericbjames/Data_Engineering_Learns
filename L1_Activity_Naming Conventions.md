SQL_naming_conventions_activity

## Lesson Context
Creating good naming conventions makes your work last while also allowing others to quickly step in and understand functionality.
I am testing out having ChatGPT create me activities that force me to think through solutions. Let's see if it can help me get better at naming convention in SQL. I want to have quick and high-quality naming schemes.

Here are the scenarios I asked for:
- Db's
- Tables
- Columns
- Views
- Variables

Here is the plan:
*Round 1:* Speed through all of them spending 1 minute on each. Perfection is not the goal but speed is. 

*Round 2:* After round 1, research best practices online and come up with what I would do in a company with the context given. There is a lot of variability in style guides. For instance, if a team is using SQL Server PascalCase would be used instead of snake_case for table names like in PostgreSQL. The lesson here is to pick a style with intention and learn how to stick to it. Just know you probably have to adapt to new styles throughout your career.

*GPT Comparison:* See what ChatGPT generated with my style guide and if there are any lessons to be gained.

## Creating a Quick Style Guide from Research
- Use snake_case: Separate words with "_" e.g. customer_id instead of customerid
- Maintain a consistent case, undercase seems to be popular e.g. full_name instead of FullName or Full_Name.
- Singular relations. Avoid plural for consistency. e.g. table named "customer" not "customers". 
- Avoid using reserved keywords or special characters. e.g. user
- Primary Key columns should be id
- Foreign Keys should me in the following format table_name_id e.g. customer_id.

### References:
https://community.databricks.com/t5/data-engineering/database-objects-naming-convention-for-bronze-silver-and-gold/td-p/6150
https://github.com/RootSoft/Database-Naming-Convention
https://brainstation.io/learn/sql/naming-conventions#:~:text=There%20are%20also%20a%20number,names%20should%20not%20contain%20spaces.

# Activity 

### Databases
A database containing information related to human resources, including employee records, payroll details, and performance evaluations.
Round 1: <human_resources_db>
Round 2: human_resources
GPT Answer: human_resources 

A database designed for content management, managing articles, blog posts, user comments, and multimedia content.
Round 1: article_manager_db 
Round 2: content_management
GPT Answer: content_managment

A database supporting financial transactions, including accounts, transactions, balances, and investments.
Round 1: finance_ledger_db
Round 2: transactions
GPT Answer: financial_transactions

A database focused on healthcare data management, containing patient records, medical histories, prescriptions, and appointments.
Round 1: health_records_db
Round 2: health_records
GPT Answer: healthcare_management

### Tables:
A table storing information about employees in an organization, including their contact details, department, and job title.
Round 1: employee_details
Round 2: employee
GPT Answer: employee

A table tracking sales transactions made by a company, recording details such as transaction date, customer ID, product ID, quantity, and total amount.
Round 1: sales_transactions_details
Round 2: sales_transactions
GPT Answer: sales_transaction

A table containing data about the current stock of products available in a warehouse, including product ID, quantity on hand, and location.
Round 1: warehouse_ID1_inventory
Round 2: warehouse_inventory
GPT Answer: product_stock

A table for collecting feedback submitted by customers after purchasing products or interacting with customer service representatives.
Round 1: customer_survey_details
Round 2: customer_feedback
GPT Answer: customer_feedback

A table storing articles and blog posts published by a company, including fields for title, content, author, and publication date.
Round 1: website_article_records
Round 2: articles
GPT Answer: blog_post

### Columns:
A unique identifier for each employee stored in the employee table.
Round 1: employee_id
Round 2:id (if primary key, employee_id if foreign)
GPT Answer:

The date when a sales transaction occurred, recorded in the sales transaction table.
Round 1: sale_transaction_dt
Round 2: sale_date
GPT Answer: transaction_date

The price of a product listed in the sales transaction table.
Round 1: item_price
Round 2: product_price
GPT Answer: product_price

The current quantity of a product available in the warehouse stock table.
Round 1: available_product_quantity
Round 2: available_quantity
GPT Answer: stock_quantity

The content of a blog post stored in the blog post table.
Round 1: post_content
Round 2: content
GPT Answer: post_content

### Views:

A view displaying the top-selling products based on sales volume and revenue generated.
Round 1: top_products_by_volume_revenue_view
Round 2: vw_top_sold_products_ranked
GPT Answer: top_selling_products_view

A view combining customer information from various tables to provide a comprehensive view of customer contact details.
Round 1: combined_customer_contact_view
Round 2: vw_combined_customer_contact
GPT Answer: customer_contact_info_view

A view showing orders that are pending processing or awaiting shipment.
Round 1: orders_pending_view
Round 2: vw_orders_in_progress
GPT Answer: pending_orders_view

A view summarizing monthly sales data, including total revenue and number of transactions.
Round 1: monthly_sales_summary_view
Round 2: vw_sales_summary_monthly
GPT Answer: monthly_sales_summary_view

A view analyzing employee performance metrics such as sales targets achieved, customer satisfaction ratings, and productivity.
Round 1: emp_kpi_metrics_view
Round 2: vw_employee_performance_metrics
GPT Answer: employee_performance_view

### Variables:
A variable holding the unique identifier of an employee.
Round 1: employee_id
Round 2: employee_id
GPT Answer: employee_id_var

A variable representing the date of a sales transaction.
Round 1: sale_transaction_dt
Round 2: transaction_date
GPT Answer: transaction_date_var

A variable storing the price of a product.
Round 1: product_price
Round 2: product_price
GPT Answer: product_price_var

A variable representing the quantity of a product in stock.
Round 1: product_available_quantity
Round 2: available_quantity
GPT Answer: stock_quantity_var

A variable holding the feedback response submitted by a customer.
Round 1: customer_response
Round 2: customer_feedback_response
GPT Answer: feedback_response_var
