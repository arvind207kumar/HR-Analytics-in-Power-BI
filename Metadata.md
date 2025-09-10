# 📄 Metadata Documentation: HR Performance Review Dataset

This document outlines the structure and relationships of the key tables used in the HR Analytics project. It includes column definitions, data types, and descriptions to help users understand the dataset and its analytical potential.

---

## 🧾 Fact Table: `Performance`

| Column                          | Data Type | Description                                                                 |
|----------------------------------|-----------|-----------------------------------------------------------------------------|
| `PerformanceID`                 | text      | Unique ID for each performance review                                      |
| `EmployeeID`                    | text      | Unique ID for each employee (connects to `DimEmployee`)                   |
| `ReviewDate`                    | date      | Date the performance review took place                                     |
| `EnvironmentSatisfaction`       | number    | Satisfaction with work environment (connects to `DimSatisfiedLevel`)      |
| `JobSatisfaction`               | number    | Satisfaction with job role (connects to `DimSatisfiedLevel`)              |
| `RelationshipSatisfaction`      | number    | Satisfaction with workplace relationships (connects to `DimSatisfiedLevel`)|
| `WorkLifeBalance`              | number    | Satisfaction with work-life balance (connects to `DimSatisfiedLevel`)     |
| `SelfRating`                    | number    | Employee’s self-assessed performance (connects to `DimRatingLevel`)       |
| `ManagerRating`                 | number    | Manager’s assessment of employee performance (connects to `DimRatingLevel`)|
| `TrainingOpportunitiesWithinYear` | number | Number of training opportunities offered in the past 12 months             |
| `TrainingOpportunitiesTaken`   | number    | Number of training opportunities taken                                     |

---

## 📘 Dimension Table: `DimSatisfiedLevel`

| Column            | Data Type | Description                                                                 |
|------------------|-----------|-----------------------------------------------------------------------------|
| `SatisfactionID` | number    | Unique ID for satisfaction levels                                           |
| `SatisfactionLevel` | text   | Satisfaction description: Very Satisfied, Satisfied, Neutral, Dissatisfied, Very Dissatisfied |

Used in: `EnvironmentSatisfaction`, `JobSatisfaction`, `RelationshipSatisfaction`, `WorkLifeBalance`

---

## 📗 Dimension Table: `DimRatingLevel`

| Column        | Data Type | Description                                                                 |
|--------------|-----------|-----------------------------------------------------------------------------|
| `RatingID`   | number    | Unique ID for rating levels                                                 |
| `RatingLevel`| text      | Rating description: Above and Beyond, Exceeds Expectation, Meets Expectation, Needs Improvement, Unacceptable |

Used in: `SelfRating`, `ManagerRating`

---

## 🎓 Dimension Table: `DimEducationLevel`

| Column             | Data Type | Description                                                                 |
|-------------------|-----------|-----------------------------------------------------------------------------|
| `EducationLevelID`| number    | Unique ID for education levels                                              |
| `EducationLevel`  | text      | Education description: Doctorate, Masters, Bachelors, High School, No Formal Qualifications |

Used in: `Education` column of `DimEmployee`

---


