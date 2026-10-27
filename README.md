# HR Analytics Dashboard (Tableau)

An interactive **HR Analytics Dashboard** built in **Tableau** to understand employee attrition, workforce demographics and job satisfaction across the organisation.

![HR Analytics Dashboard](images/dashboard.png)

---

## Table of Contents

- [Overview](#overview)
- [Key Metrics](#key-metrics)
- [Dashboard Sheets](#dashboard-sheets)
- [Key Insights](#key-insights)
- [Dataset](#dataset)
- [Data Dictionary](#data-dictionary)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [How to Use](#how-to-use)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## Overview

This dashboard gives HR teams a single view of workforce health. It helps answer questions such as:

- How many employees are leaving, and what is the overall attrition rate?
- Which departments, education fields and age groups see the most attrition?
- How does attrition differ between male and female employees?
- How satisfied are employees in each job role?

**Dashboard size:** 1580 x 900 (custom size)

## Key Metrics

| KPI | Value |
|---|---|
| Employee Count | 1,470 |
| Attrition Count | 237 |
| Attrition Rate | 16% |
| Active Employees | 1,233 |
| Average Age | 37 |

## Dashboard Sheets

| Sheet | Description |
|---|---|
| **KPI** | Headline numbers: employee count, attrition count, attrition rate, active employees, average age |
| **Attrition by Gender** | Attrition split by gender (Male: 150, Female: 87) |
| **Department wise Attrition** | Pie chart of attrition per department (R&D 133, Sales 92, HR 12) |
| **No of Employee by Age Group** | Histogram of employees by age with an adjustable **Bin Size** parameter |
| **Job Satisfaction Rating** | Heatmap-style matrix of job role vs. satisfaction rating (1-4) |
| **Education field wise Attrition** | Bar chart of attrition by education field |
| **Attrition Rate by Gender for different Age group** | Donut charts comparing male/female attrition across 5 age bands |

The dashboard is assembled on the **HR ANALYTICS DASHBOARD** tab from these seven sheets.

## Key Insights

All figures below were checked against the dataset in `data/HR_Data.xlsx`.

- Overall attrition is **16%** (237 of 1,470 employees).
- **By gender:** male employees account for more leavers (150) than female (87). Relative to headcount, the rates are 17.0% (male) and 14.8% (female).
- **By department:** R&D has the most leavers (133) simply because it is the biggest department. In proportion to size, **Sales** has the highest attrition rate (20.6%), followed by **HR** (19.0%) and **R&D** (13.8%).
- **By age:** employees **under 25** leave the most (39.2% attrition), followed by the **25-34** band (20.2%). Attrition drops to about 10% for ages 35-54.
- **By education field:** **Life Sciences** (89) and **Medical** (63) backgrounds have the most leavers, followed by Marketing (35) and Technical Degree (32).
- **Largest job roles** by headcount: Sales Executive (326), Research Scientist (292) and Laboratory Technician (259).

## Dataset

| | |
|---|---|
| **File** | `data/HR_Data.xlsx` (sheet: `HR data`) |
| **Rows** | 1,470 employees |
| **Columns** | 39 |
| **Missing values** | None |
| **Target column** | `Attrition` (Yes / No): 237 Yes, 1,233 No |

Employees are identified only by an anonymous ID (`emp no`, e.g. `STAFF-1`); the file contains no names or contact details. The structure matches the widely used public *IBM HR Analytics Employee Attrition* sample data, with a few extra helper columns (prefixed `CF_`) added for the dashboard.

The same file is also packaged inside the Tableau workbook (`.twbx`), so the dashboard opens without any extra setup.

## Data Dictionary

**Identifiers and labels**

| Column | Description |
|---|---|
| `emp no` | Anonymous staff ID (e.g. `STAFF-1`) |
| `Employee Number` | Numeric employee ID |
| `Employee Count` | Always 1; used to sum headcount |
| `Over18` | Always `Y` |
| `Standard Hours` | Always 80 |

**Attrition and helper columns**

| Column | Description |
|---|---|
| `Attrition` | Whether the employee left (`Yes`) or stayed (`No`) |
| `CF_attrition label` | `Ex-Employees` or `Current Employees` |
| `CF_current Employee` | 1 = current employee, 0 = left |
| `CF_age band` | Age group: Under 25, 25 - 34, 35 - 44, 45 - 54, Over 55 |

**Demographics**

| Column | Description |
|---|---|
| `Age` | Age in years (18 to 60) |
| `Gender` | Male / Female |
| `Marital Status` | Single / Married / Divorced |
| `Education` | Highest level: High School, Associates Degree, Bachelor's Degree, Master's Degree, Doctoral Degree |
| `Education Field` | Field of study (Life Sciences, Medical, Marketing, Technical Degree, Human Resources, Other) |
| `Distance From Home` | Distance from home to work |

**Job and company**

| Column | Description |
|---|---|
| `Department` | HR, R&D or Sales |
| `Job Role` | One of 9 roles (e.g. Sales Executive, Research Scientist) |
| `Job Level` | Seniority level |
| `Business Travel` | Non-Travel / Travel_Rarely / Travel_Frequently |
| `Over Time` | Whether the employee works overtime (Yes / No) |
| `Num Companies Worked` | Number of previous companies |
| `Total Working Years` | Total career length in years |
| `Years At Company` | Tenure at this company |
| `Years In Current Role` | Time in current role |
| `Years Since Last Promotion` | Years since last promotion |
| `Years With Curr Manager` | Time with current manager |
| `Training Times Last Year` | Number of trainings last year |

**Pay**

| Column | Description |
|---|---|
| `Monthly Income` | Monthly income |
| `Daily Rate` / `Hourly Rate` / `Monthly Rate` | Pay rates |
| `Percent Salary Hike` | Last salary increase (%) |
| `Stock Option Level` | Stock option tier |

**Satisfaction and performance (rating scales)**

| Column | Description |
|---|---|
| `Job Satisfaction` | Rating 1 to 4 |
| `Environment Satisfaction` | Rating 1 to 4 |
| `Relationship Satisfaction` | Rating 1 to 4 |
| `Job Involvement` | Rating 1 to 4 |
| `Work Life Balance` | Rating 1 to 4 |
| `Performance Rating` | Performance score |

## Tech Stack

- **Tableau** (workbook built with Tableau 2026.2) - dashboard design and visualisation
- **Microsoft Excel** (`.xlsx`) - data source

## Project Structure

```
.
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── .gitignore
├── data/
│   └── HR_Data.xlsx                  # Dataset (1,470 rows x 39 columns)
├── dashboard/
│   └── HR_Analytics_Dashboard.twbx   # Tableau packaged workbook
└── images/
    └── dashboard.png                 # Dashboard screenshot used in this README
```

## How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/hr-analytics-dashboard-tableau.git
   ```
2. Open `dashboard/HR_Analytics_Dashboard.twbx` in **Tableau Desktop** or **Tableau Public**.
3. The data is already packaged inside the workbook. If you want to refresh it or connect your own data, point the data source to `data/HR_Data.xlsx`.
4. Go to the **HR ANALYTICS DASHBOARD** tab and use the filters and the **Bin Size** control on the age group chart to explore the data interactively.

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. The dataset is a sample HR dataset and is provided for learning and portfolio purposes.

## Author

**Your Name**
GitHub: [@your-username](https://github.com/your-username)

---

If you found this project useful, please give it a star.
