# Altano Bank – Customer & Operations Analytics Dashboard

Interactive Power BI dashboard analysing customer profitability, transaction quality, and card portfolio performance for a retail bank, built for three audiences (Executive, Middle Manager, Loan Officer).

*Assignment achieved a High Distinction.*

**Tools:** Power BI, DAX, Power Query, SQL logic (business rules)

## Overview
Audited and cleaned 3 raw datasets (Customer, Transaction, Card), then built an 8-page interactive report structured in three layers: a general business-health view (customer segmentation, operational quality, market performance) for any stakeholder, audience-specific dashboards tailored to Executive, Middle Manager, and Business User roles, and two drill-through pages for deeper regional and customer-level investigation.
## Dashboard Pages

### 1. General Business Health (for all stakeholders)
#### Customer Segmentation
Profitability and risk profile by credit score band and life stage.
![Customer Segmentation](screenshots/Customer%20Segmentation.png)

#### Market Performance
Card brand market share, per-card transaction value, and chip adoption.
![Market Performance](screenshots/Market%20Performance.png)

#### Operational Quality
Transaction error rate vs. error intensity by card type, region, and time.
![Operational Quality](screenshots/Operational%20Quality.png)

### 2. Audience-Specific Dashboards
#### Executive Strategic Overview
Portfolio concentration and error exposure for leadership decision-making.
![Executive Strategic Overview](screenshots/Executive%20Strategic%20Overview.png)

#### Middle-level Manager
Regional operational KPIs (at-risk, on-track, retired-with-debt counts) and weekly error tracking.
![Middle-level Manager](screenshots/Middle-level%20Manager.png)

#### Business User
Loan officer view: customer risk flow, DTI classification, and recommendation table.
![Business User](screenshots/Business%20User.png)

### 3. Drill-Through Pages
#### State Performance (drill-through)
State Performance (drill-through)
Drills down from a selected U.S. region into state-level transaction volume, error count, and card brand mix.![State Performance](screenshots/State%20Performance.png)

#### Customer Financial Health (drill-through)
Individual customer view with credit score, DTI ratio, retirement risk, and loan recommendation — dynamically updates per selected customer. Three example outcomes below:

| | Credit Score | Total Debt | Yearly Income | DTI Ratio | Recommendation | Retirement Status |
|---|---|---|---|---|---|---|
| ![Customer 1](screenshots/Customer%20Financial%20Health%201.png) | 759 | $0 | $51K | 0.00 | Approve - Prime Candidate | Debt-Free |
| ![Customer 2](screenshots/Customer%20Financial%20Health%202.png) | 739 | $3K | $37K | 0.09 | Conditional - Review | On Track - Comfortable |
| ![Customer 3](screenshots/Customer%20Financial%20Health%203.png) | 733 | $37K | $17K | 2.23 | Decline - High Risk | Retired with Debt |

## Data Cleaning Highlights (Power Query)
- Fixed scientific-notation display on card numbers by correcting data type
- Flagged invalid CVV values against card-brand rules (3 vs 4 digits)
- Corrected logical inconsistencies between card type and credit limit
- Added Card_Status flag for expired vs. active cards instead of deleting records
- Standardised inconsistent text casing across categorical fields

## Key Insights
- The "Good" credit segment drives the highest transaction volume, led by Senior and Gen X customers
- Mastercard Debit shows disproportionately high error intensity, pointing to a processing-level issue rather than volume exposure
- Over 70% of customers across every credit band carry a critical Debt-to-Income ratio, including "Excellent" score holders

## Recommendations
- AI-driven transaction error monitoring across regions and time periods
- Customer Lifetime Value (CLV) segmentation to separate high-volume from high-value customers
- Standardised 0.45 DTI threshold for loan approval decisions

## Files
- `dashboard/` – Power BI .pbix file
- `screenshots/` – all dashboard page exports referenced above
