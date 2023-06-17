# Personal Finance Database and Dashboard
In this project, I developed a MySQL database called "spend_save" tracking all of my financial transactions. This includes purchases, deposits, withdraws, credit card payments, and more. Any transaction that results in a change in a bank account or credit card balance is tracked in this database. These transactions are extracted from my banking website in the form of CSV files, transformed using customized Python scripts, and loaded into the database via the sqlalchemy Python library. I then created SQL views to understand my spending habits and developed a Power BI dashboard linked to the MySQL database to view these habits visually.

## Technologies/Skills
- SQL (MySQL), MySQL Workbench, Python (NumPy, Pandas, SQLAlchemy), Power BI, DAX
- Data modeling, database development, data wrangling, data cleaning, ETL, data analysis, data visualization/dashboarding

## Inspiration
My inspiration for developing a financial database and dashboard stemmed from a desire to gain a deeper understanding of my spending habits. I was motivated by the idea of having a comprehensive tool that would allow me to track and analyze my expenses, giving me valuable insights into my financial patterns. I wanted to effortlessly visualize which categories I spent the most on and observe how my spending habits evolved over time. By creating this database and dashboard, I aimed to empower myself with knowledge and make informed decisions about my finances, ultimately working towards improving my financial well-being.

---

## Identifying Requirements 
My primary objective was to create a system that could meticulously monitor every transaction flowing through my bank and credit card accounts. I aimed to capture crucial details such as transaction categories, transaction types (credit card purchases, paychecks, credit card bill payments, etc.), and transaction dates. It was imperative for me to have a comprehensive view of all my financial activities, enabling me to gain a profound understanding of my monetary flow and make informed decisions based on this valuable information.

## Data Modeling
To achieve the desired requirements above, I opted to create a dimensional model consisting of 4 dimension tables and one fact table as seen below:

![data_model](final_data_model.png)

The `account`, `transaction_type`, `category`, and `date` tables are all dimensional tables, providing more information about each transaction in the transaction_facts table. However, as indicated on the data model, the `category` dimension is optional. This is because only transactions flagged as a transaction type of debit or credit card purchase are marked with a category.

To gain a better understanding of the schema tables and relationships, check out the [data_dictionary](data_dictionary.md).

## Database Creation

The creation of the database creation was performed via the "forward engineer" feature of MySQL Workbench. Additionally, the check constraint mentioned above was added. To view full creation script view [final database creation script](final_database_creation_script.sql).

## Loading Data into Dimensional Tables

Data was loaded into the dimension tables in the form of  files. To view this data, see the [dimensions_table_data](dimensions_table_data) folder.

## Transactions Data Cleaning

Transactions were loaded into the database from all accounts present in `account` dimension table (savings account, checking account, credit card). This account data was manually extracted individually for savings account transactions, checking account transactions, and credit card account transactions from my online banking website in the form of CSV files. This data was then loaded into a Jupyter notebook and each datset was individually transformed with Python. User defined functions were created to streamline this process, only requiring manual review of transactions that could not be accurately processed. To view these functions see [transactions_cleaning_functions.py](transactions_cleaning_functions.py).

I have also performed a sample data transformation for data coming from each data source, view below:

## Loading Data into Transactions_Facts Table

## Database Views Creation

## Power BI Dashboard

## Future Improvements
