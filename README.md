# 📘 README: Understanding Third Normal Form (3NF) in SQL
## 🧠 Project Title
Database Normalization: Achieving Third Normal Form (3NF) with a Company Employees Table

📝 Description
This notebook concludes the normalization series by focusing on **Third Normal Form (3NF)**. Building on 1NF and 2NF, it demonstrates how to identify and eliminate **transitive dependencies** in relational databases by splitting tables into logical, related entities. The transformation process ensures a cleaner schema design, minimizes data redundancy, and promotes maintainability.

| ⚠️ This notebook is intended to run on a local machine connected to **MySQL Workbench** and a MySQL database named `company_data`. It will not run on Google Colab due to the need for local database connectivity.


## 🎯 Learning Objectives
By the end of this lesson, learners will be able to:

- ✅ Understand the **criteria for 3NF**

- ✅ Detect and eliminate **transitive dependencies**

- ✅ Design and create **relational tables** with clear separation of concerns

- ✅ Apply the concepts using a real-world example (Company Employees dataset)

## 📦 Requirements
### 💻 Tools
- MySQL Workbench or another local MySQL server

- Jupyter Notebook, VS Code, or a MySQL-compatible IDE

- Python libraries for DB access in Jupyter:
```
pip install sqlalchemy pymysql pandas
```
### 📁 Database
- Database: `company_data`

- Table(s): `Company_employees`, plus new tables created during normalization

🧱 Project Structure
```
.
├── 3nf_normalization_notebook.ipynb   # Main notebook for Third Normal Form
├── README.md                          # Documentation for the project
├── sql/                               # SQL files for table creation and inserts
└── company_data_schema.sql            # Optional: original schema before normalization
```
## 🔧 How to Use
1. Ensure your local MySQL server is running.

2. Open MySQL Workbench and make sure the `company_data` database exists.

3. Open the notebook `(3nf_normalization_notebook.ipynb)` in Jupyter or VS Code.

4. Connect to the database using SQLAlchemy in the following format:
```
mysql+pymysql://root:<your_password>@localhost:3306/company_data
```
5. Follow each section to:

    - Inspect current table structure
    
    - Identify transitive dependencies
    
    - Normalize the schema into 3NF
    
    - Create and query the final tables
  
## 🧪 Example of 3NF Transformation
**❌ Not in 3NF (transitive dependency)**:
```
| EmployeeID | JobCode | DepartmentID | DepartmentName |
| ---------- | ------- | ------------ | -------------- |
| 1          | J001    | D001         | HR             |
```
| `DepartmentName` depends on `DepartmentID`, which is **not a primary key** — this is a transitive dependency.

**✅ After Applying 3NF**:
Table: Employee_roles
```
| EmployeeID | JobCode | DepartmentID |
| ---------- | ------- | ------------ |
```
## 📚 Key Concepts in 3NF
- Must already be in **2NF**

- **No transitive dependency**: Non-key columns cannot depend on other non-key columns

- Each non-key column must depend **only on the primary key**

## 📧 Contact
**Author**: Ibrahim Ambale
📍 Nairobi, Kenya
🔗 LinkedIn: [Ibrahim Ambale](https://linkedin.com/in/ibrahim-ambale/)

