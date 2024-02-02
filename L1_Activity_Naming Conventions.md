L1_Practicing Naming Conventions

## Lesson Context
Creating good naming conventions makes your work last while also allowing others to quickly step in and understand functionality.
I don't think depending on ChatGPT to solve all your problems is beneficial longterm. Instead, I am testing out having it create me activities that force me to think through solutions.

I need to get better at quick and high-quality naming schemes so I asked ChatGPT to give me potential scenarios for the following:
- Db's
- Tables
- Columns
- Views
- Variables

I am gonna do three rounds:
Round 1: Speed through all of them spending max 1 minute on each and create the first name that I can think of. Perfection is not the goal but speed is. 

Round 2: Research best practices online and spend time coming up with what I would do in a company with the context given. 

Round 3: Compare with what ChatGPT generated (not that this is neccessarily the most optimal but it will help to see the difference.)

## Best practices collected from Research
Copied from [this post](https://community.databricks.com/t5/data-engineering/database-objects-naming-convention-for-bronze-silver-and-gold/td-p/6150)
- Use lowercase letters for all object names (tables, views, columns, etc.).
- Separate words with underscores for readability.
- Be descriptive and concise. Use names that indicate the purpose of the object.
- Avoid using reserved keywords or special characters.

# Activity 

### Databases
<details>
  <summary>Show all DB answers</summary>
 <hr> A database containing information related to human resources, including employee records, payroll details, and performance evaluations.
 <details>
    <summary>Answer</summary>
    This is the content of Answer 1.
  </details>
<hr> A database designed for content management, managing articles, blog posts, user comments, and multimedia content.
<details>
    <summary>Answer</summary>
    This is the content of Answer 2.
  </details>
<hr> A database supporting financial transactions, including accounts, transactions, balances, and investments.
<details>
    <summary>Answer</summary>
    This is the content of Answer 2.
  </details>
<hr> A database focused on healthcare data management, containing patient records, medical histories, prescriptions, and appointments.
</details>
### Tables:
A table storing information about employees in an organization, including their contact details, department, and job title.
A table tracking sales transactions made by a company, recording details such as transaction date, customer ID, product ID, quantity, and total amount.
A table containing data about the current stock of products available in a warehouse, including product ID, quantity on hand, and location.
A table for collecting feedback submitted by customers after purchasing products or interacting with customer service representatives.
A table storing articles and blog posts published by a company, including fields for title, content, author, and publication date.

### Columns:
A unique identifier for each employee stored in the employee table.
The date when a sales transaction occurred, recorded in the sales transaction table.
The price of a product listed in the sales transaction table.
The current quantity of a product available in the warehouse stock table.
The content of a blog post stored in the blog post table.

### Views:
A view displaying the top-selling products based on sales volume and revenue generated.
A view combining customer information from various tables to provide a comprehensive view of customer contact details.
A view showing orders that are pending processing or awaiting shipment.
A view summarizing monthly sales data, including total revenue and number of transactions.
A view analyzing employee performance metrics such as sales targets achieved, customer satisfaction ratings, and productivity.
Stored Procedures:
A stored procedure for adding a new employee to the employee table.
A stored procedure for updating inventory stock levels based on incoming shipments or sales transactions.
A stored procedure for generating monthly sales reports with customizable parameters such as date range and product category.
A stored procedure for calculating employee bonuses based on performance metrics and sales targets.
A stored procedure for sending automated email surveys to customers to collect feedback.

### Variables:
A variable holding the unique identifier of an employee.
A variable representing the date of a sales transaction.
A variable storing the price of a product.
A variable representing the quantity of a product in stock.
A variable holding the feedback response submitted by a customer.