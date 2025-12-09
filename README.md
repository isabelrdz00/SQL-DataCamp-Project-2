# SQL-DataCamp-Project-2
## 📊 Project Overview – GoodThought NGO SQL Analytics

This project analyzes a relational PostgreSQL database from GoodThought, a global NGO focused on education, healthcare, and sustainable development initiatives. The dataset contains detailed historical records of assignments (projects), donations, and donors from 2010 to 2023.

Using SQL, I explored how donor behavior and project performance metrics can help inform funding decisions and improve the organization’s impact strategy.

### Dataset & ERD Summary
- The database includes three core tables:
- assignments – Project metadata such as name, duration, budget, region, and impact_score.
donations – Financial contributions linked to donors and assignments, including donation amount, date, and status.
donors – Information on individual and organizational donors, including donor_type.

The ERD shows a 1-to-many relationship:

One assignment → many donations

One donor → many donations

This relational structure supports aggregation of donation amounts and analysis of donor types across projects.

### 🔍 Objective 1 – Top Donated Assignments by Donor Type

Goal:
Identify which assignments generated the highest total donation value and understand the influence of donor types on those totals.

### Key Tasks:

Aggregate donation amounts per assignment and donor_type.

Round totals to two decimals.

Join assignments, donations, and donors at the correct granularity.

Rank results and return the top 5 highest-funded assignments.

Result Saved As: highest_donation_assignments

### Skills Demonstrated:

Grouped aggregations

Multi-table joins

Subqueries (calculating totals before joining to avoid incorrect aggregation grain)

Ranking with ORDER BY

Data accuracy validation

This query required correctly structuring a subquery to compute donation totals grouped by both assignment and donor_type, ensuring accurate aggregation before joining back to the assignments table.

#### 🌍 Objective 2 – Highest-Impact Assignment per Region

Goal:
Find the project with the highest impact_score within each region, but only among assignments that received at least one donation.

Key Tasks:

Filter assignments to include only those with ≥1 donation.

Count total donations per assignment.

Identify the maximum impact_score for each region.

Ensure only one assignment per region is returned.

Sort final output by region.

Result Saved As: top_regional_impact_assignments

Skills Demonstrated:

Grouping and HAVING filters

Counting donations (COUNT on primary keys)

Correlated subqueries (per-region maximum impact)

Deduplication logic

Analytical reasoning on aggregation grain

This query showcases the ability to combine multi-level logic: first summarizing donation counts, then ranking assignments by impact_score inside each region, and finally selecting only the top result per region.
