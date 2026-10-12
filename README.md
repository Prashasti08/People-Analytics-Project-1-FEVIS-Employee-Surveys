# People Analytics Project: Employee Engagement Predictors

Identifying workplace predictors of employee engagement using real survey data, SQL, Python, predictive modeling, and Tableau.

## Research Question

- Which workplace factors predict engagement among employees of U.S. federal government agencies (N=87,321)?

## Business Purpose

- Identify where federal agency HR teams should focus efforts to improve employee engagement.

## Methodology

- **Data preparation:** Cleaned **87,321 real employee records**, retaining **78,685 complete responses** to engagement questions (Q86–Q90) and workplace questions (Q1, Q5, Q50, Q57). Averaged Q86–Q90 into one engagement score
- **Descriptive analysis and correlation:** Examined four workplace factors - Development Opportunities (Q1), Reasonable Workload (Q5), Supervisor Listening (Q50), and Leadership Motivation (Q57) and their relationships with engagement scores
- **Predictive modeling:** Conducted **multiple linear regression** to examine each factor’s relationship with engagement while accounting for the other three
- **Model comparison:** Used an 80/20 train-test split to compare Multiple Linear Regression, Decision Tree, and Random Forest against an average-score baseline using **Mean Absolute Error (MAE)**

## Findings

- **Descriptive analysis:** Leadership motivation had the lowest average rating (**3.39/5.00**); supervisor listening had the highest (**4.30/5.00**)
- **Correlation:** Development (**0.577**) and leadership (**0.573**) had the strongest relationships with engagement: employees giving these factors higher ratings tended to report higher engagement scores
- **Regression:** Development and leadership remained the strongest predictors after accounting for workload and supervisor listening. Together, the four factors explained **45.6% of differences in engagement scores**
- **Model comparison:** Random Forest had the lowest average prediction error: **0.443 points**, versus Decision Tree (**0.447**), regression (**0.460**), and the average-score baseline (**0.623**)

## Key Insights and Recommendations

- **Leadership priority:** Leadership combined a low rating with a strong engagement association. Conduct **follow-up surveys or employee interviews** to identify specific leadership concerns before choosing initiatives.
- **Development priority:** Development had the largest regression association with engagement. Investigate barriers to learning opportunities and pilot targeted improvements. Supporting research: [Gallup, 2025—Employee Development Barriers](https://www.gallup.com/workplace/692642/addressing-barriers-blocking-employee-development.aspx).
- **Targeted action:** Consider clearer communication of organizational purpose if follow-up feedback identifies this concern. Supporting research: [Gallup, 2024—The Great Detachment](https://www.gallup.com/workplace/653711/great-detachment-why-employees-feel-stuck.aspx).
- **Investment decisions:** Evaluate pilots using engagement changes, relevant performance measures, intervention costs, and a comparison group before expanding agency-wide.

## Data Source

- [2024 OPM Federal Employee Viewpoint Survey — Official Data Page (select 2024)](https://www.opm.gov/fevs/public-data-file/)
- **Q86–Q90:** OPM’s Employee Experience Index questions covering employees’ inspiration from their jobs, accomplishment from their work, attachment to their agency, identification with its mission, and belief that contributing to the common good is important

## Code

- **Python / Jupyter Notebook:** Data cleaning, descriptive statistics, correlations, multiple linear regression, predictive modeling, and charts.
- **SQLite:** Executed **SQL aggregation queries** using `COUNT`, `AVG`, and `GROUP BY` to extract employee counts and average engagement by development and leadership ratings.
- [View Python Analysis and SQL Queries](https://github.com/Prashasti08/People-Analytics-Project-Employee-Engagement-Predictors/blob/main/Employee_Engagement_Analysis.ipynb.ipynb)

## Data Visualizations and Dashboard

- **Python:** Horizontal bar charts displaying **Pearson correlation coefficients** and **model MAE comparisons**.
- **Tableau:** Interactive horizontal bar charts showing **mean engagement by development and leadership ratings**, with cross-filtering.
- **Planned additions:** Correlation heatmap, Tableau regression coefficient plot, and model-comparison bar chart.

## Limitations

- **Unweighted, observational analysis:** Findings identify associations, not proven causes.
- **Business impact:** Provides evidence for prioritizing investigations and pilots; financial returns were not measured.
