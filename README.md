# HR-Analytics-in-Power-BI

<img width="1730" height="674" alt="image" src="https://github.com/user-attachments/assets/c7cc19ca-d214-469b-af37-c5dd4b4e458a" />
## 🧩 Data Model: Snowflake Schema Overview

This project uses a **Snowflake Schema**, which promotes data integrity and reduces redundancy by normalizing dimension tables. While this structure is ideal for maintaining clean relationships and scalable data modeling, tools like Power BI may require optimization techniques to ensure smooth performance.


### 🗂️ Core Tables & Relationships

The central fact table is:

- **`Performance`**  
  Contains employee performance reviews, satisfaction ratings, training metrics, and both self and manager evaluations.

This fact table connects to several dimension tables:

#### 📌 Dimension Tables

| Table Name         | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| `Employee`         | Contains demographic, job role, education, and tenure details for each employee |
| `SatisfiedLevel`   | Maps numeric satisfaction scores to descriptive levels (e.g., Very Satisfied, Neutral) |
| `RatingLevel`      | Maps performance ratings to qualitative labels (e.g., Exceeds Expectations, Unacceptable) |
| `EducationLevel`   | Maps education codes to formal qualifications (e.g., Masters, High School) |

#### 📐 Measures

The model includes calculated measures such as:

- Average satisfaction scores across categories
- Training participation rates
- Performance rating distributions
- Attrition-linked performance trends

### 🔗 Relationships

- `Performance.EmployeeID` → `Employee.EmployeeID`  
- `Performance.EnvironmentSatisfaction`, `JobSatisfaction`, `RelationshipSatisfaction`, `WorkLifeBalance` → `SatisfiedLevel.SatisfactionID`  
- `Performance.SelfRating`, `ManagerRating` → `RatingLevel.RatingID`  
- `Employee.Education` → `EducationLevel.EducationLevelID`

This structure enables flexible slicing and dicing of performance data across multiple dimensions while maintaining referential integrity.

---
