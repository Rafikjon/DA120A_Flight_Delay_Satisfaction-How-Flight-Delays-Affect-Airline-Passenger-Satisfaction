# Project Proposal

## 1. Project Title
**DA120A_Flight_Delay_Satisfaction** – How Flight Delays Affect Airline Passenger Satisfaction

## 2. Team and Roles
| Member | Role | Main responsibilities |
|---|---|---|
| Rafikjon | Team Lead / Data Engineer | Coordination, repository management, data loading and merging |
| Taner | Data Analyst – Data Cleaning & Feature Engineering | Missing values, outliers, delay categories, feature preparation for modelling |
| Mallesh | Data Analyst – EDA & Visualizations | Exploratory analysis, charts, dashboard, planning documents |

## 3. Introduction
Punctuality is one of the most visible parts of the air-travel experience. When a flight departs or arrives late, passengers lose time, miss connections and often lose trust in the airline. This project analyses an airline passenger satisfaction survey of almost 130,000 passengers to measure how departure and arrival delays relate to overall satisfaction, and how strong the effect of delays is compared with service-quality factors such as seat comfort, online boarding and in-flight Wi-Fi.

## 4. Problem Statement
Airlines operate in a highly competitive market where dissatisfied passengers can easily switch to a competitor. Retaining an existing customer is significantly cheaper than acquiring a new one, so understanding what drives dissatisfaction has direct financial value. Delays are partly outside an airline's control (weather, air traffic), while service quality is fully controllable. Without evidence on **how much** delays reduce satisfaction, and **whether good service can compensate for a delay**, airlines cannot decide where to invest: in punctuality, or in the passenger experience.

## 5. Research Questions
1. Is there a significant difference in satisfaction between passengers on delayed and on-time flights?
2. How does the satisfaction rate change as delay length increases (on time, 1–15, 16–60, 60+ minutes)?
3. Is arrival delay or departure delay more strongly related to dissatisfaction?
4. Does the effect of delays differ by travel class, type of travel (business vs. personal) and customer type (loyal vs. disloyal)?
5. Compared with service-quality ratings, how important are delays for predicting satisfaction?

## 6. Objectives
- Clean and prepare the dataset for analysis (missing values, outliers, encoding).
- Create delay-based features (delay categories, delayed flag, delay recovered in flight).
- Quantify the relationship between delays and satisfaction using descriptive statistics and statistical tests (chi-square, t-test / Mann-Whitney).
- Identify the passenger segments most sensitive to delays.
- Build a simple classification model (e.g., logistic regression / random forest) to rank the importance of delays against service factors.
- Present findings in clear visualisations and actionable recommendations for airlines.

## 7. Tools and Technology Stack
| Category | Tool | Purpose |
|---|---|---|
| Programming | Python 3 | Main analysis language |
| Data processing | Pandas, NumPy | Loading, cleaning, transforming data |
| Statistics | SciPy | Hypothesis tests (chi-square, t-test, Mann-Whitney U) |
| Machine learning | scikit-learn | Classification model and feature importance |
| Visualisation | Matplotlib, Seaborn | Static charts for EDA and report |
| Dashboard (optional) | Power BI / Tableau Public | Interactive summary dashboard |
| Development environment | Jupyter Notebook, VS Code | Notebooks and scripts |
| Version control | Git, GitHub | Code and document management, progress log |
| Collaboration | MS Teams | Team communication and instructor contact |
| Planning | draw.io, Excel / Google Sheets | Mindmap and Gantt chart |

## 8. Dataset
**Name:** Airline Passenger Satisfaction
**Source:** Kaggle (TJ Klein) – https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction
**Size:** 129,880 passengers (train.csv 103,904 + test.csv 25,976), 25 columns
**Format:** CSV, tabular

**Key variables**
- **Target:** `satisfaction` – *satisfied* (43.4%) / *neutral or dissatisfied* (56.6%)
- **Delays:** `Departure Delay in Minutes`, `Arrival Delay in Minutes`
- **Service ratings (0–5):** 14 variables, e.g. seat comfort, Wi-Fi, online boarding, cleanliness
- **Passenger profile:** gender, age, customer type, type of travel, class, flight distance

**Why this dataset**
We evaluated four candidate datasets:
| Dataset | Delay data | Satisfaction data | Decision |
|---|---|---|---|
| DoorDash delivery times | Delivery duration only (no expected time) | None | Rejected |
| Olist Brazilian E-Commerce | Yes (estimated vs. actual date) | Review score | Rejected – 9 tables, complex joins for the project scope |
| E-Commerce Shipping Data | Yes/No only | Rating 1–5 | Rejected – delay not measured in time |
| **Airline Passenger Satisfaction** | **Minutes (departure + arrival)** | **Satisfaction label + 14 ratings** | **Selected** |

It is the only candidate that contains both a precise delay measure and a direct satisfaction outcome in a single, clean table.

**Initial data quality observations**
- 393 missing values in `Arrival Delay in Minutes` (0.3%).
- Around 44% of flights had some arrival delay; about 23% were delayed more than 15 minutes.
- Delay distributions are highly right-skewed (median 0, maximum around 1,600 minutes) – outlier handling required.
- Departure and arrival delay are strongly correlated (r ≈ 0.97) – multicollinearity must be handled in modelling.
- Some service ratings contain 0 = "not applicable", which must be treated separately from low ratings.

## 9. Scope
**In scope:** descriptive and statistical analysis of delays vs. satisfaction, segment analysis, a baseline classification model, visualisations and recommendations.
**Out of scope:** real-time data, airline/route-level analysis (not in the dataset), causal inference, deployment of a production model.

## 10. Expected Deliverables
1. Cleaned, documented dataset
2. Jupyter notebooks (cleaning, feature engineering, EDA, modelling)
3. Visualisations / dashboard
4. Final report with findings and recommendations
5. Final presentation

## 11. Risks and Mitigation
| Risk | Mitigation |
|---|---|
| Survey data, not operational data – satisfaction is self-reported | State as limitation; focus on associations, not causation |
| Skewed delay values and outliers | Delay categories and capping / log transform |
| Team availability | Clear task owners in Gantt chart, weekly check-in on MS Teams |
| No airline, date or route information | Limit conclusions to passenger-level patterns |

## 12. Workspace Setup Status
- **MS Teams channel:** DA120A_Flight_Delay_Satisfaction, instructor added.
- **GitHub repository:** private, structured into `data/`, `src/`, `documentation/`, `logs/`; all team members and the instructor added as collaborators. Progress log maintained on the README main page.

## 13. Supporting Documents
- [Data Dictionary](data_dictionary.md)
- [Project Execution Plan & Gantt Chart](execution_plan.md)
- [Mindmap](mindmap.png)
- [Cost Management Plan](cost_management_plan.md)
