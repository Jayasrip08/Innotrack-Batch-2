# Day 13 Task – Personal Expense Tracker (Flask + SQLite + Jinja2)

## Batch

**VelTech Students – Batch 2**

---

# Objective

Today your goal is to build the backend integration of the **Personal Expense Tracker** application using:

* Flask
* Jinja Template Rendering
* SQLite Database
* HTML, CSS, and JavaScript

Students must implement complete CRUD operations and dynamically display data from the database.

---

# Project Overview

The Personal Expense Tracker helps users record and manage their daily expenses.

Users should be able to:

* Add expenses
* View all expenses
* Edit expenses
* Delete expenses
* View expense summaries
* Filter expenses by category

---

# Technologies Used

* Frontend: HTML, CSS, JavaScript
* Backend: Flask
* Template Engine: Jinja2
* Database: SQLite

---

# Project Structure

```text
PersonalExpenseTracker
│
├── app.py
├── expense.db
│
├── templates
│   ├── index.html
│   ├── add_expense.html
│   ├── expenses.html
│   ├── edit_expense.html
│   └── summary.html
│
└── static
    ├── css
    │   └── style.css
    │
    ├── js
    │   └── script.js
    │
    └── images
```

---

# Database Requirements

Create a SQLite database named:

```text
expense.db
```

Create a table named:

```sql
expenses
```

Columns:

| Column Name  | Data Type                         |
| ------------ | --------------------------------- |
| id           | INTEGER PRIMARY KEY AUTOINCREMENT |
| title        | TEXT                              |
| amount       | REAL                              |
| category     | TEXT                              |
| payment_mode | TEXT                              |
| expense_date | TEXT                              |
| description  | TEXT                              |

---

# Flask Routes to Implement

### Home Page

```text
/
```

Displays project dashboard and quick statistics.

---

### Add Expense Page

```text
/add-expense
```

Allows users to add new expense records.

---

### View Expenses Page

```text
/expenses
```

Displays all expenses stored in SQLite.

---

### Edit Expense Page

```text
/edit/<id>
```

Allows updating an existing expense.

---

### Delete Expense

```text
/delete/<id>
```

Deletes a selected expense.

---

### Expense Summary Page

```text
/summary
```

Displays:

* Total Expenses
* Category-wise Expense Count
* Highest Expense
* Recent Expenses

---

# Form Fields

The Add Expense form must contain:

* Expense Title
* Amount
* Category
* Payment Mode
* Date
* Description

Categories can include:

* Food
* Transport
* Shopping
* Bills
* Entertainment
* Education
* Health
* Others

Payment Modes:

* Cash
* UPI
* Debit Card
* Credit Card
* Net Banking

---

# Jinja2 Requirements

Students must use:

```python
render_template()
```

and Jinja syntax:

```html
{% for %}
{% if %}
{{ variable }}
```

for displaying database data dynamically.

---

# Frontend Requirements

All pages should include:

✅ Responsive Navigation Bar

✅ Dashboard Cards

✅ Professional Color Theme

✅ Tables with Hover Effects

✅ Form Validation using JavaScript

✅ Responsive Design

✅ Confirmation before Delete

✅ Attractive Footer

---

# Additional Challenge Tasks

Implement any TWO:

1. Search expenses by title.
2. Filter expenses by category.
3. Display monthly total spending.
4. Add expense charts using Chart.js.
5. Display top spending category.
6. Add dark mode.

---

# Running the Project

Install dependencies:

```cmd
pip install flask
```

Run the project:

```cmd
python app.py
```

Open Browser:

```text
http://127.0.0.1:5000
```

---

# Deliverables

Every team must demonstrate:

✓ Correct Flask project structure

✓ SQLite database creation

✓ Database connection using Python

✓ Insert expense records

✓ Display records dynamically using Jinja2

✓ Edit functionality

✓ Delete functionality

✓ Summary page

✓ Professional frontend design

✓ At least TWO challenge features implemented

---

# Submission Requirements

Each team must submit:

1. Source Code Folder
2. SQLite Database File
3. Screenshots of all pages
4. Short demonstration video (2–3 minutes)
5. GitHub Repository Link

---

### Deadline

Submit the completed project before tomorrow's session.

Tomorrow we will extend this project further by adding authentication and advanced analytics features.
