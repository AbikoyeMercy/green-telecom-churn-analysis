# Project Case Study: Green Telecom Churn Shield Retention Dashboard

## Executive Summary
This project delivers an interactive data solution for Green Telecom, a telecommunications provider seeking to reduce subscriber cancellations and secure baseline revenue. The primary purpose of this project is to build an early warning churn tracking tool by identifying high-risk customer traits. By writing defensive SQL scripts to audit, clean, and standardize messy billing logs, this analysis reveals exactly which payment methods and contract terms lead to subscriber losses. Ultimately, it provides customer retention teams with a dynamic dashboard to track revenue at risk ($139K) and launch targeted promotions to protect the company's bottom line.

## Problem Statement
*   **Situation:** Green Telecom monitors a subscriber base of over 7,000 customers, tracking billing records, contract structures (Month-to-month, One year, Two year), payment methods, and churn data.
*   **Complication:** The raw data logs were highly inconsistent. some column contained missing fields, and logical variables were recorded using mixed terms (like 1, 0,"YES", "NO", and "No internet service"). Leaving the data in this messy format would cause the visual reporting charts to crash, yield faulty aggregation summaries, and skew the true churn rate.
*   **Core Question:** How can we use data visuals to pinpoint the exact customer profiles and operational bottlenecks causing subscriber cancellations, allowing the retention team to protect the revenue at risk?

## Tools Used

*   **SQL (Data Engineering & Cleaning):**
    *   **Data Quality Auditing:** Wrote analytical queries to check for null values, empty entries, and formatting anomalies across thousands of customer IDs.
    *   **Missing Data Remediation:** Handled blanks in financial tracking metrics by automatically mapping unrecorded values to a clean numerical baseline of 0.00.
    *   **Categorical Standardization:** Used conditional logical formatting (CASE WHEN logic) to align inconsistent tracking labels. Rewrote messy string text into an optimized binary structure (1 for YES, 0 for NO) to prevent report errors and maximize query processing speeds.
*   **Power BI (Modeling & Visualization):**
    *   **Semantic Layer Design:** Ingested the clean SQL-transformed views and constructed an active data model with interactive global cross-filtering page slicers (Contract Type and Tenure Band).
    *   **Dashboard** Designed a corporate layout showcasing vital high-level summary cards (Total Monthly Revenue at $456K, Churn Rate at 26.54%) alongside heatmaps, donut graphs, and time-series line trends.

## How the Dashboard Works
1.  **Macro Headline Tracking:** Provides executives with immediate insight into major health metrics, highlighting a Total Customer count of 7.043K and Revenue at Risk sitting at $139K.
2.  **Subscriber Segment Deep-Dives:** Utilizes side-by-side vertical bar charts to track absolute subscriber loss volumes across specific temporal segments (e.g., isolating a massive drop-off among short-term 0–12 month tenure customers).
3.  **Cross-Filtered Matrix Grid:** Incorporates a master detailed table mapping the intersection of Customer IDs, internet setups, partner links, and payment pathways. Rows are sorted by Revenue at Risk to let account managers focus efforts efficiently.
<img width="1254" height="766" alt="Screenshot 2026-11-05 153552" src="https://github.com/user-attachments/assets/7b32591a-8b81-4d0e-b9f3-fbbe1790be69" />

## Key Findings
*   **The Month-to-Month Contract Trap:** Subscribers tied to flexible Month-to-month contracts exhibit the highest risk of churn, making up the vast majority of lost accounts. In contrast, longer multi-year contracts provide highly stable revenue.
*   **Electronic Check Friction:** A disproportionate chunk of the overall churn slice (57.3%) is concentrated entirely within customers using Electronic Check billing paths, indicating potential billing friction, card expirations, or processing glitches.
*   **Critical Early-Stage Churn Window:** Account cancellations are overwhelmingly concentrated in the 0–12 month tenure bracket (exceeding 1,000 lost accounts). Once a subscriber hits their second year (13–24 months), the likelihood of cancellation drops off significantly.
*   **Fiber Optic Risk Concentration:** High-value customers subscribing to premium Fiber Optic internet packages represent the largest concentration of high-churn rates and revenue leakage when coupled with month-to-month billing paths.

##  Recommendations
1.  **Introduce Automatic Billing Incentives:** Launch a targeted campaign to transition the high-risk 57.3% Electronic Check segment over to Bank Transfers or automatic Credit Card processing by offering a one-time invoice credit.
2.  **Early Retention Milestones:** Deploy customized customer-success check-ins and onboarding outreach specifically targeting month-to-month subscribers during their first 90 to 180 days of contract lifetime to bridge the high-risk 12-month tenure slump.
3.  **Contract Migration Strategy:** Incentivize high-value Fiber Optic users to migrate off standard Month-to-month options onto fixed 1-Year or 2-Year packages by offering small, value-add service upgrades or speed boosts.
