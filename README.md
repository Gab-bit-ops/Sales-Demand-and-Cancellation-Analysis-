# Sales Demand and Cancellation Analysis (2025)
Overview & Executive Summary
This project analyzes Kora’s 2025 sales demand and order cancellations using a MySQL database (comprising 7 tables) and an interactive Power BI dashboard.
 * Total Orders (2025): 6,001 orders
 * Total Sales (Net of Cancellations): ₦17.11 billion
 * Cancellation Rate: ~4% (219 orders cancelled, valued at approximately ₦0.60bn)
 * On-Time Delivery Rate: 56% (44% of deliveries arrived late)
 * Seasonality Peak: Orders grew steadily from 410 in January to a peak of 700 in November, with October through December accounting for 31% of the annual volume.
Methodology & Data Quality Assurance
The analysis followed a rigorous workflow to ensure data integrity before generating insights:
 * Environment Setup: Working copies of all 7 tables were created to preserve the original raw data.
 * Data Cleaning: Checked for duplicates, blank fields, extra spaces, and spelling inconsistencies. Text entries were trimmed as a precaution.
   * Missing Values Handled: Blank cancellation reasons on 5,782 non-cancelled orders were marked as "No Records", and a dedicated column was introduced to flag missing dispatch (65 rows) or delivery (271 rows) dates.
 * SQL & Power BI Alignment: All six core business questions were answered via MySQL queries. Cancelled orders were explicitly excluded from sales and discount calculations.
 * Validation: Results across SQL and the Power BI dashboard matched perfectly (e.g., 6,001 orders, ₦17.11bn sales, 3.65% cancellation rate, and November peak of 700).
Key Assumptions
 * Cancelled orders are omitted from sales and discount figures, while pending and partly delivered orders are retained since the transactions occurred.
 * "On time" is defined as delivery occurring on or before the promised date.
 * Discount savings presume that customers maintain consistent purchasing behavior, and financial figures are denoted in Naira without inflation adjustments.
Key Findings & Recommendations
1. Fix Late Deliveries
 * The Insight: 2,695 out of 6,137 delivered orders (44%) arrived late. Performance across all three carriers was nearly identical (ranging from 56% to 58% on time), proving this is a systemic issue rather than a single underperforming carrier. Furthermore, two out of three late deliveries lacked a recorded reason.
 * Actionable Steps:
   * Provide realistic delivery estimates that fulfillment teams can reliably meet.
   * Enforce mandatory root-cause logging for every delayed delivery.
   * Review and scale logistics capacity.
2. Streamline Credit Checks to Reduce Cancellations
 * The Insight: 219 orders totaling ~₦0.60bn were cancelled. The primary drivers are credit holds (89 orders / 41%), customer-initiated requirement changes (73 orders), and stock unavailability (57 orders). Branch cancellation rates remain tightly clustered between 3.4% and 4.2% (with Enugu slightly the highest at ~4%), indicating that process triggers matter more than geographic location.
 * Actionable Steps:
   * Run customer credit evaluations earlier in the workflow during order intake.
   * Explicitly confirm product requirements with clients before locking in orders.
3. Proactively Plan for Peak Seasons
 * The Insight: November experienced 700 orders (a 71% surge compared to January), with Q4 (October to December) making up nearly a third of total annual volume.
 * Actionable Steps:
   * Secure inventory stock and ramp up delivery personnel capacity starting in September ahead of the rush.
Limitations & Next Steps
 * Analytical Limitations: The dataset lacks cost and profitability metrics (making it impossible to evaluate margin health on high discounts) and covers only a single year (May–December 2025 contract span across 18 active customers), leaving year-over-year seasonality unverified.
 * Data Requests for Future Iterations:
   * Product-level cost/profit metrics and contract terms for the 18 contract clients.
   * Carrier contracts, transit distances, and itemized delay explanations.
   * Customer credit limits and historical 2024 order logs to benchmark seasonality patterns.
