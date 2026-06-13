# Post 2 — SQL Tip: CTEs

**Category:** SQL Tip
**Status:** Pending
**Best Time to Post:** Wednesday 8–10 AM

---

## Post Text

This SQL trick saves me 2 hours every week.

Most analysts write this:

SELECT *
FROM orders
WHERE status = 'completed'
AND date >= '2024-01-01'

I write this:

WITH completed_orders AS (
  SELECT order_id, customer_id, revenue, date
  FROM orders
  WHERE status = 'completed'
    AND date >= '2024-01-01'
)
SELECT
  customer_id,
  COUNT(order_id) AS total_orders,
  SUM(revenue) AS total_revenue
FROM completed_orders
GROUP BY customer_id

CTEs (Common Table Expressions) make your SQL:
✅ Readable by any teammate
✅ Easier to debug
✅ Reusable across your query

Stop writing monolithic SQL.
Start writing SQL that tells a story.

Save this post. You'll thank yourself later. 🔖

#SQL #DataAnalytics #DataAnalyst #Analytics #TechTips

---

## Image Suggestion

Split screen: messy SQL (left) vs clean CTE version (right). Title: 'SQL Before vs After.' Dark code theme. 1200x1200px.