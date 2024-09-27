SQL Query Collection
This repository contains a set of SQL queries designed to analyze flight data, user booking patterns, and airport services. The queries address the following tasks:

Flight Departure Analysis: Count flights departing during the work week and weekends.
User Hotel Discount Analysis: Identify users with significant hotel discounts.
Airport Services Calculation: Determine the airport with the most services.
Airport Services Ranking: Rank airports by the total number of services as a percentage.
Query Descriptions and Clauses Used
1. Flight Departure Analysis

Task: Calculate the number of flights with a departure time during the work week (Monday through Friday) and the number of flights departing during the weekend (Saturday or Sunday).
Key Clauses:
SELECT: Specify the columns to be returned.
SUM(CASE WHEN ...): Conditional aggregation to count flights based on the day of the week.
EXTRACT(DOW FROM ...): Extract the day of the week from the departure time.
2. User Hotel Discount Analysis

Task: Identify users whose maximum hotel discount is strictly greater than the maximum average discount across all users who have booked at least two trips with a hotel discount.
Key Clauses:
SELECT DISTINCT: Select unique user IDs.
GROUP BY: Group results by user ID to calculate aggregates.
HAVING: Filter groups based on aggregate conditions.
Subquery: Used to calculate the maximum average hotel discount.
3. Airport Services Calculation

Task: Calculate the total number of services for each airport and find the airport with the most services.
Key Clauses:
WITH ... AS: Common Table Expressions (CTEs) to structure intermediate result sets.
UNION ALL: Combine results from multiple queries.
GROUP BY: Aggregate results by airport.
ORDER BY ... DESC: Order results in descending order to find the airport with the most services.
FETCH FIRST 1 ROW ONLY: Limit the result to the top airport.
4. Airport Services Ranking

Task: Rank airports by the total number of services as a percentage.
Key Clauses:
WITH ... AS: Common Table Expressions (CTEs) to structure intermediate result sets.
RANK() OVER (ORDER BY ...): Window function to rank airports based on the number of services.
COUNT(*) OVER (): Window function to count the total number of airports.
ROUND(...): Round the percentage rank to one decimal place.
Each query is designed to provide insights into different aspects of flight and booking data, utilizing various SQL clauses and functions to perform complex data manipulations and calculations.
