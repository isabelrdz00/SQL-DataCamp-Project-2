# 📊 GoodThought NGO SQL Analytics Project

This project analyzes a PostgreSQL database from GoodThought, an NGO that tracks global development projects, donations, and donor activity from 2010–2023. The goal was to extract actionable insights about project funding and regional impact using advanced SQL techniques.

## Dataset Summary

assignments – project details (name, region, budget, impact_score)

donations – financial contributions linked to assignments and donors

donors – donor information, including donor_type

Assignments have many donations, and donors can contribute multiple times.

### 🔍 Query 1 — Highest Donation Assignments (Top 5)

Objective: Identify the top five assignments by total donation value, broken down by donor_type.

What I did:

- Aggregated donation amounts at the correct grain (assignment_id + donor_type)
- Used a subquery to prevent double-counting during joins
- Rounded totals to two decimals and returned assignment_name, region, rounded_total_donation_amount, and donor_type
- Saved as: highest_donation_assignments

Skills: multi-table joins, subqueries, grouped aggregation, ranking.

### 🌍 Query 2 — Top Regional Impact Assignments

Objective: For each region, return the assignment with the highest impact_score only among projects that received at least one donation.

What I did:

- Counted donations per assignment using LEFT JOIN + HAVING
- Used a correlated subquery to select the max impact_score per region
- Returned assignment_name, region, impact_score, and num_total_donations
- Saved as: top_regional_impact_assignments

Skills: HAVING filters, correlated subqueries, de-duplication logic.

### 🧠 Skills Demonstrated

- SQL joins and grouping
- Subqueries for correct aggregation
- Filtering and ranking logic
- Translating relational data into funding and impact insights
