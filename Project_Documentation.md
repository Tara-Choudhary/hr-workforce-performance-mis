# Project Documentation: HR Workforce & Performance MIS Reporting System

## 1. Overview

This project uses Microsoft Excel to turn a fictional HR dataset into an interactive management information system (MIS). It focuses on workforce composition and selected performance-related indicators.

## 2. Dataset and handling

The working dataset contains 311 employee records. The source is the Human Resources Data Set by Rich Huebner on Kaggle:
https://www.kaggle.com/datasets/rhuebner/human-resources-data-set

The project reviewed data types, employee identifiers, missing values, and relevant category fields. The `EmpID` field was checked for duplicates and no duplicate employee IDs were found. The user also observed eight missing `ManagerID` values and 207 null `DateofTermination` values for active employees. These null termination dates are consistent with active status and should not be filled with invented dates.

The dataset's `DateofTermination` field has missing values; the data profile showed 67% empty. Publicly shared workbook copies should remove employee names, dates of birth, ZIP codes, and other unnecessary identifiers. Confirm the source license before redistributing the data itself.

## 3. Workbook structure

- `Raw_Data`: preserved source records
- `Clean_Data`: data prepared for analysis
- `KPI_Summary`: overall metrics
- `Department_MIS`: department-level PivotTables
- `HR_Dashboard`: management-facing visuals and slicer

## 4. KPI definitions and current results

| KPI | Current result | Definition |
|---|---:|---|
| Total employees | 311 | Count of employee records / unique employee IDs after validation |
| Active employees | 207 | Count of records with active employment status |
| Terminated employees | 104 | Count of records classified as terminated |
| Average salary | $69,020.68 | Mean salary across the 311 records |
| Average engagement | 4.11 | Mean `EngagementSurvey` score |
| Average satisfaction | 3.89 | Mean `EmpSatisfaction` score |
| Average absences | 10.24 | Mean `Absences` value |
| Total absences | 3,184 | Sum of `Absences` |
| Average days late | 0.41 | Mean `DaysLateLast30` value |

Confirm the workbook formulas and PivotTable aggregation settings before making changes or publishing a refreshed version.

## 5. Department-level reporting

The `Department_MIS` sheet summarizes employee count, average salary, average absences, employees with performance records, average engagement, and average satisfaction by department.

| Department | Headcount | Average salary | Average absences | Average engagement | Average satisfaction |
|---|---:|---:|---:|---:|---:|
| Admin Offices | 9 | $71,791.89 | 8.67 | 4.39 | 3.56 |
| Executive Office | 1 | $250,000.00 | 10.00 | 4.83 | 3.00 |
| IT/IS | 50 | $97,064.64 | 10.44 | 4.15 | 3.96 |
| Production | 209 | $59,953.55 | 10.14 | 4.13 | 3.86 |
| Sales | 31 | $69,061.26 | 11.55 | 3.82 | 4.03 |
| Software Engineering | 11 | $94,989.45 | 8.73 | 4.06 | 4.09 |
| **Total / overall average** | **311** | **$69,020.68** | **10.24** | **4.11** | **3.89** |

The Executive Office has only one record, so its average salary and other metrics should not be compared as though they were based on a large group.

## 6. Performance distribution

| Performance category | Employee count | Share of records (approx.) |
|---|---:|---:|
| Fully Meets | 243 | 78.1% |
| Exceeds | 37 | 11.9% |
| Needs Improvement | 18 | 5.8% |
| PIP | 13 | 4.2% |
| **Total** | **311** | **100%** |

Percentages may appear rounded in the dashboard.

## 7. Dashboard design

The dashboard contains:
- KPI cards for total employees, active employees, terminated employees, and average salary
- Employee headcount by department
- Employee performance distribution
- Average engagement by department
- Average absences by department
- Average satisfaction by department
- Department slicer

The slicer was connected to the relevant PivotTables and the KPI-card calculations were adjusted so that the displayed KPI values respond to the department selection. Test each department and clear the filter before publishing.

## 8. Data-quality notes

- No duplicate `EmpID` values were found in the reviewed data.
- Eight `ManagerID` values were reported as null.
- Active employees have null `DateofTermination` values; do not treat these as errors or impute termination dates.
- Review remaining missing values and category consistency before publishing a sanitized copy.
- Preserve the raw source separately from the prepared reporting data.

## 9. Key observations

- Production is the largest department (209 records).
- Fully Meets is the most common performance category (243 records).
- Sales has the highest average absences (11.55).
- Executive Office has the highest average engagement score (4.83), but the group contains one record only.
- These are descriptive observations, not evidence of cause and effect.

## 10. Limitations

- The dataset is fictional and may not represent current HR practices.
- The results are limited to the supplied fields and records.
- Small department sizes can make averages unstable.
- The analysis should not be used to make real employment decisions.
- Validate all figures against the latest saved workbook if the data or formulas change.

## 11. Data source and attribution

Rich Huebner, Human Resources Data Set, Kaggle:
https://www.kaggle.com/datasets/rhuebner/human-resources-data-set

Check the dataset page for the current license and attribution requirements. Do not publish the raw CSV or a workbook containing unnecessary employee identifiers unless the applicable license and privacy review permit it.
