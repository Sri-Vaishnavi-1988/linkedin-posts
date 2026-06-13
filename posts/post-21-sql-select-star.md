# Post 21 — SQL: Stop Using SELECT *

**Category:** SQL Tip
**Status:** Pending
**Best Time to Post:** Monday 8-10 AM

---

## Post Text

Stop writing SELECT * in production SQL. Here's why.

I see this in almost every junior analyst's code:

SELECT * FROM orders WHERE date >= '2024-01-01'

Looks harmless. It isn't.

Here's what actually happens:
→ You pull every column including 12 you don't need
→ Query time doubles on wide tables
→ When the source table adds a new column, your downstream breaks
→ Nobody reading your code knows what data you're actually using

What I write instead:

SELECT
  order_id,
  customer_id,
  order_date,
  revenue
FROM orders
WHERE order_date >= '2024-01-01'

Benefits:
✅ Faster query execution
✅ Explicit — anyone knows exactly what's being used
✅ Stable — adding columns upstream won't break your logic
✅ Easier to debug when something goes wrong

Name your columns.
Own your query.

Save this. Share it with a junior analyst who needs it. 🔖

#SQL #DataAnalytics #DataAnalyst #SQLTips #DataEngineering

---

## Image Suggestion

Code split. Top: SELECT * in red. Bottom: explicit columns in green. Title: 'Stop Using SELECT *'. Dark code theme. 1200x1200px.