# Post 23 — SQL: CASE WHEN Advanced

**Category:** SQL Tip
**Status:** Pending
**Best Time to Post:** Friday 8-10 AM

---

## Post Text

The most underused SQL function in data analytics:

CASE WHEN

Most analysts use it for simple labels.
The best analysts use it for everything.

Simple use (what everyone does):
SELECT
  order_id,
  CASE WHEN revenue > 1000 THEN 'High' ELSE 'Low' END AS tier
FROM orders

Advanced use (what changes your analysis):

-- Pivot rows into columns
SELECT
  month,
  SUM(CASE WHEN region = 'North' THEN revenue ELSE 0 END) AS north_revenue,
  SUM(CASE WHEN region = 'South' THEN revenue ELSE 0 END) AS south_revenue,
  SUM(CASE WHEN region = 'East'  THEN revenue ELSE 0 END) AS east_revenue
FROM sales
GROUP BY month

-- Conditional aggregation
SELECT
  customer_id,
  COUNT(CASE WHEN status = 'returned' THEN 1 END) AS returns,
  COUNT(CASE WHEN status = 'completed' THEN 1 END) AS completed
FROM orders
GROUP BY customer_id

No pivot table needed.
No Python needed.
Just SQL.

Which CASE WHEN trick changed your analysis workflow? 👇

#SQL #DataAnalytics #DataAnalyst #SQLTips #Analytics

---

## Image Suggestion

Side-by-side code blocks. Left: Basic CASE WHEN. Right: Advanced pivot. Dark theme. Title: 'CASE WHEN — Beyond the Basics.' 1200x1200px.