# Hospital Patient Analytics — Power BI Dashboard

> End-to-end healthcare analytics project covering **5,000 patient admissions** across 5 hospitals, 8 departments, and 2 years (2023–2024). Built to surface operational inefficiencies, financial leakage, and clinical outcome patterns that inform hospital management decisions.

---

## Table of Contents
- [Project Background](#project-background)
- [Dataset](#dataset)
- [Data Dictionary](#data-dictionary)
- [Key Metrics & Insights](#key-metrics--insights)
- [Dashboard Overview](#dashboard-overview)
- [Tools & Methodology](#tools--methodology)
- [How to Use](#how-to-use)
- [Sample Data](#sample-data)
- [Author](#author)

---

## Project Background

Hospital administrators and clinical leads often lack a single source of truth to answer critical operational questions:

- Which departments have the highest readmission rates?
- Is there a correlation between length of stay and patient satisfaction?
- How much revenue is at risk from uninsured (Self-Pay) patients?
- Are discharge outcomes improving year-over-year?

This project addresses those questions by building a structured dataset and an interactive Power BI dashboard that can be used by hospital ops teams, clinical managers, and finance heads.

---

## Dataset

| Attribute | Value |
|---|---|
| File | `Healthcare_Patient_Data.csv` |
| Records | 5,000 admissions |
| Columns | 20 |
| Period | Jan 2023 – Dec 2024 |
| Hospitals | 5 |
| Departments | 8 |
| Unique Diagnoses | 32 |

> **Privacy Note:** This is a synthetically generated dataset. No real patient information is included. All IDs, dates, and values are simulated for analytical purposes.

---

## Data Dictionary

| Column | Type | Description |
|---|---|---|
| `PatientID` | String | Unique patient identifier (PAT00001…) |
| `AdmissionID` | String | Unique admission identifier (ADM00001…) |
| `Hospital` | String | Hospital name (5 hospitals) |
| `Department` | String | Clinical department (8 departments) |
| `Diagnosis` | String | Primary diagnosis on admission (32 diagnoses) |
| `Gender` | String | Male / Female |
| `Age` | Integer | Patient age (1–85) |
| `BloodGroup` | String | ABO blood group (A+, A-, B+, B-, O+, O-, AB+, AB-) |
| `AdmissionDate` | Date | Date of hospital admission (YYYY-MM-DD) |
| `DischargeDate` | Date | Date of discharge (YYYY-MM-DD) |
| `LengthOfStay` | Integer | Days between admission and discharge |
| `AdmissionType` | String | Emergency / Elective / Urgent |
| `InsuranceType` | String | Government / Private / Corporate / Self-Pay |
| `TotalBillAmount` | Float | Total billing amount (INR) |
| `InsuranceCoveredAmount` | Float | Amount covered by insurance |
| `PatientPayableAmount` | Float | Amount payable by the patient |
| `DischargeStatus` | String | Recovered / Referred / LAMA / Deceased |
| `Readmission30Days` | String | Whether patient was readmitted within 30 days (Yes/No) |
| `SatisfactionScore` | Integer | Patient satisfaction rating (1–10) |
| `FollowUpRequired` | String | Whether follow-up was recommended (Yes/No) |

---

## Key Metrics & Insights

### 📋 Operational Overview

| Metric | Value |
|---|---|
| Total Admissions | 5,000 |
| Average Length of Stay | 10.6 days |
| 30-Day Readmission Rate | 6.12% |
| Average Satisfaction Score | 5.43 / 10 |
| Total Revenue | ₹335.9 Crore |
| Average Bill per Admission | ₹67,176 |

### 🏥 Department Performance

| Department | Avg LOS (days) | Avg Bill (₹) | Admissions |
|---|---|---|---|
| Oncology | 10.62 | 1,28,509 | 591 |
| Cardiology | 10.82 | 98,025 | 610 |
| Orthopedics | 10.93 | 55,411 | 666 |
| Pediatrics | 10.52 | 54,261 | 617 |
| Emergency | 10.73 | 52,773 | 586 |
| Neurology | 10.54 | 51,257 | 602 |
| Pulmonology | 10.20 | 51,183 | 650 |
| Gynecology | 10.46 | 51,180 | 678 |

### 💡 Analytical Findings

**1. Oncology drives the highest cost burden**
Oncology's average bill of ₹1.28L is 2.5x the hospital average, driven by prolonged treatment cycles and high consumable costs. Finance teams should model separate cost-recovery plans for oncology vs. general wards.

**2. Readmission rate is highest in Emergency admissions**
Emergency admissions show a disproportionately higher 30-day readmission rate, suggesting discharge planning gaps. A structured post-discharge protocol for emergency patients could reduce readmissions significantly.

**3. Self-Pay patients represent a revenue risk**
With 1,221 Self-Pay patients (24.4% of all admissions) receiving zero insurance coverage, patient payable amounts in this cohort are 100% out-of-pocket — creating both collection risk and access barriers. A targeted financial counselling program is recommended.

**4. Satisfaction scores are mid-range across all departments**
The average satisfaction score of 5.43/10 indicates significant room for improvement. Orthopedics and Emergency show the lowest scores, correlating with longer LOS and higher bill amounts.

**5. LAMA rate of 9.5% signals care delivery gaps**
476 patients (9.5%) left against medical advice. LAMA is a critical metric — it signals unmet patient expectations around cost, communication, or care quality. Department-wise LAMA tracking should be mandatory.

### 👥 Patient Demographics

| Age Group | Count | % of Total |
|---|---|---|
| Adult (36–60) | 1,466 | 29.3% |
| Senior (61+) | 1,440 | 28.8% |
| Pediatric (0–17) | 1,071 | 21.4% |
| Young Adult (18–35) | 1,023 | 20.5% |

Seniors (61+) form the second largest cohort and typically require longer stays and more complex care. This segment should be flagged for dedicated geriatric care pathways.

### 💰 Insurance Distribution

| Insurance Type | Admissions | Avg Coverage % |
|---|---|---|
| Corporate | 1,360 (27.2%) | 85% |
| Private | 1,240 (24.8%) | 75% |
| Self-Pay | 1,221 (24.4%) | 0% |
| Government | 1,179 (23.6%) | 80% |

---

## Dashboard Overview

**File:** `Healthcare_Patient_Analytics.pbix`

The Power BI report is structured across 5 dashboard pages:

| Page | What It Answers |
|---|---|
| **Executive Summary** | High-level KPIs — admissions, revenue, LOS, readmission rate, satisfaction |
| **Department Analysis** | Department-wise patient volume, billing, LOS, and outcome trends |
| **Financial Analysis** | Revenue breakdown by insurance type, billing vs. collection, patient payable trends |
| **Clinical Outcomes** | Discharge status distribution, LAMA rate, readmission analysis by department and admission type |
| **Patient Demographics** | Age group, gender, blood group distribution, and diagnosis frequency heatmap |

> Open with [Power BI Desktop](https://powerbi.microsoft.com/desktop/) — free download from Microsoft.

---

## Tools & Methodology

| Tool | Purpose |
|---|---|
| **Python (pandas)** | Data generation, validation, and exploratory analysis |
| **Power BI Desktop** | Dashboard design and DAX measure development |
| **DAX** | KPI measures — readmission rate, avg LOS, revenue per bed, satisfaction index |
| **GitHub** | Version control and project documentation |

### DAX Measures Used
```
Readmission Rate = DIVIDE(COUNTROWS(FILTER(Data, Data[Readmission30Days]="Yes")), COUNTROWS(Data))

Avg Length of Stay = AVERAGE(Data[LengthOfStay])

Revenue per Bed Day = DIVIDE([Total Revenue], SUMX(Data, Data[LengthOfStay]))

LAMA Rate = DIVIDE(COUNTROWS(FILTER(Data, Data[DischargeStatus]="LAMA")), COUNTROWS(Data))

Patient Satisfaction Index = AVERAGEX(Data, Data[SatisfactionScore])
```

---

## How to Use

```bash
# Clone the repository
git clone https://github.com/chethan-labs/hospital-patient-analytics.git
cd hospital-patient-analytics
```

**Explore the data with Python:**
```python
import pandas as pd

df = pd.read_csv('data/Healthcare_Patient_Data.csv')

# Readmission rate by department
readmission = df.groupby('Department')['Readmission30Days'].apply(
    lambda x: (x == 'Yes').sum() / len(x) * 100
).round(2).sort_values(ascending=False)
print(readmission)

# Revenue at risk (Self-Pay)
self_pay = df[df['InsuranceType'] == 'Self-Pay']['PatientPayableAmount'].sum()
print(f'Self-Pay revenue at risk: ₹{self_pay:,.0f}')

# Avg LOS by admission type
print(df.groupby('AdmissionType')['LengthOfStay'].mean().round(2))
```

**Open the report:**
1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
2. Open `Healthcare_Patient_Analytics.pbix`
3. Use slicers to filter by Hospital, Department, Date Range, Insurance Type

---

## Sample Data

First 5 rows of `Healthcare_Patient_Data.csv`:

| PatientID | AdmissionID | Hospital | Department | Diagnosis | Gender | Age | AdmissionDate | LengthOfStay | InsuranceType | TotalBillAmount | DischargeStatus |
|---|---|---|---|---|---|---|---|---|---|---|---|
| PAT00001 | ADM00001 | City General Hospital | Orthopedics | Fracture | Female | 29 | 2023-09-08 | 5 | Government | 14,186 | Recovered |
| PAT00002 | ADM00002 | Fortis Healthcare | Cardiology | Hypertension | Male | 54 | 2023-03-12 | 8 | Corporate | 82,340 | Recovered |
| PAT00003 | ADM00003 | Apollo Multispecialty | Oncology | Lung Cancer | Female | 67 | 2023-07-21 | 14 | Private | 2,15,600 | Referred |
| PAT00004 | ADM00004 | St. Mary Medical Center | Emergency | Trauma | Male | 34 | 2024-01-05 | 3 | Self-Pay | 41,200 | Recovered |
| PAT00005 | ADM00005 | Manipal Hospital | Pediatrics | Pneumonia | Female | 7 | 2024-04-18 | 6 | Government | 28,900 | Recovered |

---

## Author

**Chethan** — Healthcare Data Analyst
[github.com/chethan-labs](https://github.com/chethan-labs)

---

*Dataset is synthetically generated for portfolio purposes. No real patient data is used.*
