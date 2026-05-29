# Day 1 — Student Reference Guide
## Introduction to Data Engineering + GitHub
### Codeboosters Tech — Data Engineering + GenAI Internship Program

---

## Quick Reference Card

| Topic | Key Point |
|-------|-----------|
| Data Engineering | Building systems to collect, store, clean, and deliver data |
| Structured Data | Rows and columns — CSV, Excel, SQL |
| Semi-Structured | Key-value pairs — JSON, XML |
| Unstructured | No fixed format — images, videos, audio, PDFs |
| Pandas | Python library for working with tabular data |
| DataFrame | In-memory table with rows and columns |
| GitHub | Cloud platform for version control and code portfolio |
| Commit | Saved snapshot of code with a description |

---

## Essential Pandas Commands — Day 1

```python
import pandas as pd                    # Import Pandas library

df = pd.read_csv('filename.csv')       # Load a CSV file

df.head()                              # Show first 5 rows
df.head(10)                            # Show first 10 rows
df.tail()                              # Show last 5 rows

df.shape                               # (number_of_rows, number_of_columns)
df.dtypes                              # Data type of each column
df.describe()                          # Statistical summary
df.isnull().sum()                      # Count missing values per column
df.columns.tolist()                    # List all column names

df['column_name']                      # Select one column

# Boolean Filtering
df[df['column'] == 'value']            # Filter rows equal to value
df[df['column'] > 80]                  # Filter rows greater than 80
df[df['column'] < 75]                  # Filter rows less than 75

# Groupby and Aggregation
df.groupby('column')['other'].mean()   # Average per group
df['column'].value_counts()            # Count each unique value

# Sorting
df.sort_values(by='column', ascending=False)   # Sort highest first
df.sort_values(by='column', ascending=True)    # Sort lowest first

# New Column
df['new_col'] = df['col1'] + df['col2']  # Add columns together

# Save DataFrame
df.to_csv('output.csv', index=False)   # Save as CSV
```

---

## Types of Data — Summary

### Structured Data
- Organized in rows and columns
- Every record has the same fields
- Examples: marksheet, bank transactions, attendance register
- Formats: CSV, Excel (.xlsx), SQL Database

### Semi-Structured Data
- Has labels/tags but not in strict rows and columns
- Can have nested data (data inside data)
- Examples: API responses, WhatsApp message metadata, config files
- Formats: JSON, XML

### Unstructured Data
- No predefined format or structure
- Cannot be stored directly in a spreadsheet without losing information
- Examples: photos, lecture videos, voice notes, PDFs, handwritten notes
- Formats: JPG, MP4, MP3, PDF, TXT

**Key Fact:** 80% of all data created in the world is unstructured.

---

## GitHub Key Concepts

| Term | Meaning | Analogy |
|------|---------|---------|
| Repository (Repo) | Project folder on GitHub | Google Drive folder for your project |
| Commit | Saved snapshot with a message | Ctrl+S in Google Docs with a label |
| Push | Send local code to GitHub | Upload to Google Drive |
| Pull | Download code from GitHub | Download from Google Drive |
| README.md | Project description file | Cover page of your project report |
| Branch | Separate version of code | Making a copy to experiment on |

### GitHub Setup Steps
1. Go to github.com
2. Sign Up → enter email, username, password
3. Verify email
4. Click '+' → 'New repository'
5. Name: `codeboosters-internship-2024`
6. Set to **Public**
7. Check 'Add a README file'
8. Click 'Create repository'

### Uploading Notebook to GitHub
1. Go to your repository
2. Click 'Add file' → 'Upload files'
3. Drag and drop your `.ipynb` file
4. Write a commit message: `Add Day 1 notebook`
5. Click 'Commit changes'

---

## Common Errors and Fixes

| Error | Fix |
|-------|-----|
| `ModuleNotFoundError: No module named 'pandas'` | Run `!pip install pandas` |
| `FileNotFoundError: student_performance.csv` | Upload file via Colab Files panel |
| `KeyError: 'column_name'` | Check `df.columns` for exact spelling |
| `SyntaxError` | Check for missing brackets, quotes, colons |
| `IndentationError` | Use exactly 4 spaces. Never mix tabs and spaces |

---

## Dataset Reference — student_performance.csv

| Column | Type | Description |
|--------|------|-------------|
| student_id | int | Unique student number |
| name | text | Student's full name |
| age | int | Age in years |
| gender | text | Male or Female |
| department | text | Engineering department |
| semester | int | Current semester |
| math_score | int | Math marks (0-100) |
| science_score | int | Science marks (0-100) |
| english_score | int | English marks (0-100) |
| programming_score | int | Programming marks (0-100) |
| attendance_percentage | int | Attendance % (0-100) |
| city | text | Home city |
| admission_year | int | Year of admission |

**This dataset will be used across all 10 days of the internship.**

---

## Practice Questions — Day 1

1. A hospital stores patient X-ray images, doctor's notes, and a table of patient vital signs. Classify each data type.

2. Why do companies need Data Engineers? Give a real-world example.

3. Write Python code to load `sales.csv` and show its first 10 rows.

4. What does `df.shape` return? If it returns `(500, 15)`, what does each number mean?

5. How do you filter a DataFrame called `orders` to show only rows where `city` is `Mumbai`?

6. You accidentally delete your Python script. How would GitHub have saved you?

---

## Day 1 Completion Checklist

- [ ] I can explain what a Data Engineer does
- [ ] I can classify Structured, Semi-Structured, and Unstructured data
- [ ] I have loaded `student_performance.csv` in Google Colab
- [ ] All notebook cells run without errors
- [ ] I have created a GitHub account
- [ ] I have created a repository named `codeboosters-internship-2024`
- [ ] I have uploaded my Day 1 notebook to GitHub
- [ ] I have updated my README.md

---

## What's Coming on Day 2

On Day 2, we take the **same student dataset** and:
- Store it in a real **database** using SQLite
- Write **SQL queries** to find insights
- Create **charts and visualizations** using Matplotlib
- Build a **Student Performance Dashboard**

---

*Codeboosters Tech | Data Engineering + GenAI Internship | Day 1 of 10*

# Day 2 — Student Reference Guide
## Database Fundamentals + SQL + Data Visualization
### Codeboosters Tech — Data Engineering + GenAI Internship

---

## Continuity from Day 1
The `student_performance.csv` from Day 1 is **loaded into a real SQLite database** today.
Pipeline: `CSV → SQLite DB → SQL Queries → DataFrames → Charts`

---

## Database Quick Concepts

| Term | Meaning | Example |
|------|---------|---------|
| **Database** | Organized storage for structured data | `college.db` |
| **Table** | Rows and columns inside a database | `students` table |
| **Row / Record** | One complete entry | One student's data |
| **Column / Field** | One attribute per record | `math_score` |
| **Primary Key** | Unique ID for each row — cannot repeat | `student_id` |
| **Foreign Key** | Column linking to another table's PK | `dept_code` |
| **SQL** | Language to query databases | `SELECT * FROM students` |
| **SQLite** | Lightweight DB stored in one file | `college.db` |

---

## Python Database Setup — Essential Code

```python
import sqlite3
import pandas as pd
import matplotlib.pyplot as plt

# 1. Connect to (or create) database
conn = sqlite3.connect('college.db')
cursor = conn.cursor()

# 2. Load CSV into database table
df = pd.read_csv('student_performance.csv')
df.to_sql('students', conn, if_exists='replace', index=False)

# 3. Run SQL → get DataFrame
result = pd.read_sql_query("SELECT * FROM students LIMIT 5", conn)

# 4. Close when done
conn.close()
```

---

## SQL Cheat Sheet

```sql
-- Basic SELECT
SELECT name, math_score FROM students;
SELECT * FROM students;                        -- all columns
SELECT * FROM students LIMIT 10;              -- first 10 rows

-- Filter with WHERE
SELECT name FROM students WHERE math_score > 80;
SELECT name FROM students WHERE department = 'Computer Science';
SELECT name FROM students WHERE math_score > 70 AND attendance_percentage > 85;
SELECT name FROM students WHERE department IN ('Computer Science', 'Electronics');
SELECT name FROM students WHERE math_score BETWEEN 70 AND 90;

-- Sort and limit
SELECT name, math_score FROM students ORDER BY math_score DESC LIMIT 5;
SELECT DISTINCT department FROM students;      -- unique values

-- Aggregate functions
SELECT COUNT(*)                 FROM students;             -- total rows
SELECT AVG(math_score)          FROM students;             -- average
SELECT SUM(attendance_percentage) FROM students;           -- sum
SELECT MIN(math_score)          FROM students;             -- minimum
SELECT MAX(math_score)          FROM students;             -- maximum
SELECT ROUND(AVG(math_score),2) FROM students;             -- rounded avg

-- GROUP BY
SELECT department, COUNT(*) AS num_students
FROM students GROUP BY department;

SELECT department, ROUND(AVG(math_score),2) AS avg_math
FROM students GROUP BY department ORDER BY avg_math DESC;

-- HAVING (filter groups)
SELECT department, AVG(math_score) AS avg_math
FROM students GROUP BY department HAVING AVG(math_score) > 70;

-- Calculated column
SELECT name, math_score + science_score + english_score + programming_score AS total_score
FROM students ORDER BY total_score DESC;

-- INNER JOIN
SELECT s.name, s.math_score, d.hod_name
FROM students AS s
INNER JOIN departments AS d ON s.dept_code = d.dept_code;
```

**SQL Execution Order:** `FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY → LIMIT`

---

## WHERE vs HAVING

| | WHERE | HAVING |
|--|-------|--------|
| **Filters** | Individual rows | Groups |
| **When applied** | Before GROUP BY | After GROUP BY |
| **Can use aggregates?** | No | Yes |
| **Example** | `WHERE math_score > 80` | `HAVING AVG(math_score) > 80` |

---

## Matplotlib Chart Templates

```python
import matplotlib.pyplot as plt

# ── Template (works for all chart types) ──
fig, ax = plt.subplots(figsize=(10, 6))   # width x height in inches
# ... draw chart here ...
ax.set_title('Title Here', fontsize=16, fontweight='bold')
ax.set_xlabel('X Label', fontsize=13)
ax.set_ylabel('Y Label', fontsize=13)
plt.tight_layout()
plt.show()

# ── Bar Chart ──
ax.bar(x_categories, y_values, color='#4FC3F7', edgecolor='white')

# ── Histogram ──
ax.hist(data_list, bins=10, color='#4FC3F7', edgecolor='white')
ax.axvline(x=mean_val, color='red', linestyle='--', label='Mean')
ax.legend()

# ── Horizontal Bar ──
ax.barh(y_labels, x_values, color='#4FC3F7')
ax.invert_yaxis()                          # highest value at top

# ── Pie Chart ──
ax.pie(sizes, labels=labels, autopct='%1.1f%%', startangle=90,
       wedgeprops={'edgecolor':'white', 'linewidth':2})

# ── 4-Panel Dashboard ──
fig, axes = plt.subplots(2, 2, figsize=(18, 13))
fig.suptitle('Dashboard Title', fontsize=20, fontweight='bold')
ax1 = axes[0][0]   # top-left
ax2 = axes[0][1]   # top-right
ax3 = axes[1][0]   # bottom-left
ax4 = axes[1][1]   # bottom-right
```

---

## pd.read_sql_query — The Bridge

```python
# SQL → DataFrame in one line
result_df = pd.read_sql_query("""
    SELECT department, ROUND(AVG(math_score), 2) AS avg_math
    FROM students
    GROUP BY department
    ORDER BY avg_math DESC
""", conn)

# Now use result_df like any other DataFrame
print(result_df)
ax.bar(result_df['department'], result_df['avg_math'])
```

---

## Common Errors — Day 2

| Error | Cause | Fix |
|-------|--------|-----|
| `no such table: students` | DB setup cell not run | Run the `df.to_sql()` cell first |
| `no such column: name` | Column name typo | Run `PRAGMA table_info(students)` |
| `ProgrammingError: closed connection` | conn was closed | Re-run `conn = sqlite3.connect('college.db')` |
| Chart appears blank | DataFrame is empty | `print(result_df)` before charting |
| Labels cut off | `tight_layout()` missing | Add `plt.tight_layout()` before `plt.show()` |

---

## Practice Questions

1. What is the difference between a Primary Key and a Foreign Key?
2. Write SQL to find the average programming score for female students only.
3. What is the difference between WHERE and HAVING? Give one example of each.
4. Write SQL to find departments where average attendance is above 85%.
5. What does `pd.read_sql_query()` return and what arguments does it need?
6. You want to show how math scores are distributed. Which chart type is best and why?

---

## Day 2 Completion Checklist

- [ ] `college.db` created from `student_performance.csv`
- [ ] All 8 SQL queries run without errors
- [ ] 4 charts created (bar, histogram, grouped bar, pie)
- [ ] Student Performance Dashboard (2×2 grid) complete
- [ ] Notebook saved as `Day_02_Database_SQL_Visualization.ipynb`
- [ ] Notebook uploaded to GitHub
- [ ] Commit message: `Add Day 2: SQL Database + Visualization Dashboard`

---

## Day 3 Preview
**ETL Pipelines + Pandas Data Cleaning + Weather API**
- Call a real API and collect live weather data
- Clean messy data (nulls, duplicates, wrong types)
- Build a complete ETL pipeline
- The student dataset continues!

---
*Codeboosters Tech | Data Engineering + GenAI Internship | Day 2 of 10*

# Day 3 — Student Reference Guide
## ETL Pipelines + Pandas Data Cleaning + APIs
### Codeboosters Tech — Data Engineering + GenAI Internship

---

## Continuity from Days 1 & 2
- Day 1: Loaded `student_performance.csv` with Pandas
- Day 2: Stored it in SQLite, queried with SQL, visualized
- Day 3: Learn WHERE clean data comes from — the ETL pipeline

---

## ETL at a Glance

```
EXTRACT     →  Pull data from source (CSV file, API, database)
TRANSFORM   →  Clean it (fix nulls, duplicates, formats, types)
LOAD        →  Save to destination (CSV, database, warehouse)
```

**Water treatment analogy:** River (raw source) → Treatment plant (transform) → Water tank (load) → Homes (users)

| | ETL | ELT |
|--|-----|-----|
| **Order** | Transform before loading | Load first, transform inside warehouse |
| **Where transform happens** | Python / Pandas | SQL inside cloud DB |
| **When to use** | Relational DBs, Python pipelines | Cloud warehouses (Snowflake, BigQuery) |

---

## Pandas Data Cleaning — Essential Commands

```python
import pandas as pd

# ── ALWAYS start with a copy ──
df = raw_df.copy()          # Never modify raw data directly

# ── DETECT problems ──
df.isnull().sum()           # Count missing values per column
df.duplicated().sum()       # Count duplicate rows
df.dtypes                   # Check data types
df['col'].unique()          # Check unique values for inconsistencies

# ── FIX missing values ──
df['col'].fillna(df['col'].median(), inplace=True)   # Fill numbers with median
df['col'].fillna('Unknown', inplace=True)            # Fill text with label
df.dropna(subset=['order_id'], inplace=True)         # Drop rows where ID is null

# ── REMOVE duplicates ──
df.drop_duplicates(inplace=True)                                      # Remove exact duplicates
df.drop_duplicates(subset=['customer', 'product'], inplace=True)     # Targeted dedup

# ── FIX data types ──
df['qty']   = pd.to_numeric(df['qty'],   errors='coerce')  # String → number
df['price'] = pd.to_numeric(df['price'], errors='coerce')  # errors='coerce' → NaN not crash
df['qty']   = df['qty'].astype(int)                        # Float → integer

# ── PARSE dates ──
df['date'] = pd.to_datetime(df['date'], errors='coerce')   # String → datetime
df['year']  = df['date'].dt.year                           # Extract year
df['month'] = df['date'].dt.month                          # Extract month
df['day']   = df['date'].dt.strftime('%A')                 # Extract day name

# ── FIX text ──
df['name'] = df['name'].str.strip().str.title()   # Remove spaces + Title Case
df['col']  = df['col'].str.upper()                # All caps
df['col']  = df['col'].str.lower()                # All lowercase

# ── FIX specific cells with boolean mask ──
mask = (df['product'] == 'Keyboard') & (df['category'] == 'Electronics')
df.loc[mask, 'category'] = 'Accessories'
# df.loc[row_condition, column] = new_value

# ── CREATE new columns ──
df['revenue'] = df['quantity'] * df['unit_price']

# ── AGGREGATE cleaned data ──
summary = df.groupby('category').agg(
    total_revenue = ('revenue', 'sum'),
    avg_order     = ('revenue', 'mean'),
    num_orders    = ('order_id', 'count')
).round(2).reset_index()

# ── SAVE clean data ──
df.to_csv('clean_data.csv', index=False)
```

---

## Missing Values — Decision Guide

| Situation | Strategy |
|-----------|----------|
| Numeric, few nulls (<5%) | `fillna(column.median())` |
| Numeric, many nulls (>30%) | Investigate — may drop column |
| Text / category column | `fillna('Unknown')` |
| ID / primary key column | `dropna(subset=['id'])` — drop row |
| Date column | `dropna()` or fill forward |

---

## APIs — Quick Reference

```python
import requests

# ── Setup ──
API_KEY  = 'your_key_here'
BASE_URL = 'https://api.openweathermap.org/data/2.5/weather'

# ── Make a GET request ──
params   = {'q': 'Mumbai', 'appid': API_KEY, 'units': 'metric'}
response = requests.get(BASE_URL, params=params, timeout=10)

# ── Check status ──
print(response.status_code)
# 200 = OK    401 = Bad key    404 = Not found    429 = Rate limit

# ── Parse JSON ──
if response.status_code == 200:
    data = response.json()          # JSON text → Python dict
    temp = data['main']['temp']     # Navigate nested dict
    desc = data['weather'][0]['description']   # Navigate list inside dict
    hum  = data['main'].get('humidity', 0)     # Safe access with default

# ── Convert API results to DataFrame ──
records = [{'city': 'Mumbai', 'temp': 32.5}, {'city': 'Delhi', 'temp': 38.2}]
df = pd.DataFrame(records)   # List of dicts → DataFrame
```

**HTTP Status Codes:**
| Code | Meaning | Action |
|------|---------|--------|
| 200 | Success | Proceed |
| 401 | Unauthorized | Check API key |
| 404 | Not Found | Check city name / URL |
| 429 | Rate Limit | Wait 1 min, retry |
| 500 | Server Error | Retry later |

---

## ETL Best Practices

1. **Always check shape before and after** — `print(df.shape)` at start and end
2. **Never modify raw data** — `df = raw_df.copy()`
3. **Log every step** — `print()` what changed and how many rows affected
4. **Validate after each fix** — `isnull().sum()` should be 0 after fillna
5. **Handle errors gracefully** — `errors='coerce'` on type conversions
6. **Document your choices** — comment WHY you chose median vs 0 for fillna

---

## Common Errors — Day 3

| Error | Cause | Fix |
|-------|--------|-----|
| `KeyError: 'main'` | API returned error (wrong city name) | Print `response.json()` to see error message |
| `ConnectionError` | No internet | Check connectivity; use fallback data (Cell 15) |
| `ValueError: mixed date formats` | to_datetime can't parse inconsistent dates | Add `errors='coerce'` |
| `TypeError: str * float` | Multiplying string column | Convert first: `pd.to_numeric(df['col'], errors='coerce')` |
| `AttributeError: 'DataFrame' has no attribute 'append'` | Using old Pandas API | Use `pd.concat([df1, df2], ignore_index=True)` |
| Duplicates not removed | subset= columns too broad/narrow | Check `df[df.duplicated(keep=False)]` to see what's flagged |

---

## Day 3 Datasets

| File | Description |
|------|-------------|
| `messy_sales_data.csv` | 30 rows, 9 columns — 5 data quality issues to fix |
| `clean_sales_data.csv` | Output after Activity 1 cleaning |
| `weather_data.csv` | Output after Activity 2 API pipeline |

---

## Practice Questions

1. Explain ETL using a hospital example (patient records).
2. A DataFrame has 500 rows. After `df.dropna()` it has 412. What does this tell you?
3. Write code to remove rows where `customer_name` AND `product` are both the same.
4. What is the difference between `fillna(0)` and `fillna(df['col'].median())`?
5. Write code to call the weather API for 'Delhi' and print the temperature.
6. What does `response.status_code == 401` mean? How do you fix it?

---

## Day 3 Completion Checklist

- [ ] All notebook cells run without errors
- [ ] `df.isnull().sum().sum() == 0` after cleaning sales data
- [ ] `df.duplicated().sum() == 0` after deduplication
- [ ] `weather_data.csv` saved (8 cities)
- [ ] `clean_sales_data.csv` saved
- [ ] Weather dashboard (3-panel chart) visible
- [ ] Upload: `Add Day 3: ETL Pipeline + Weather API`

---

## Day 4 Preview
**Big Data + Apache Spark + Modern Data Architecture**
- Why Python fails at 300 million rows
- Apache Spark — distributed computing engine
- Medallion Architecture: Bronze → Silver → Gold
- Run PySpark in Google Colab!

---
*Codeboosters Tech | Data Engineering + GenAI Internship | Day 3 of 10*
