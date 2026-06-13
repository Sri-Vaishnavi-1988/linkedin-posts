# Post 25 — Tableau: LOD Expressions

**Category:** Tableau / Technical
**Status:** Pending
**Best Time to Post:** Wednesday 8-10 AM

---

## Post Text

The Tableau feature that separates good analysts from great ones:

LOD Expressions.

(Level of Detail — and yes, they're worth learning)

The problem they solve:
You want to show monthly revenue per customer
BUT your viz is filtered to just this quarter.

Without LOD → your totals change with every filter.
With LOD → you control which calculation ignores filters.

The 3 you need to know:

FIXED
{ FIXED [Customer ID] : SUM([Revenue]) }
→ Calculates per customer regardless of any filter
→ Use for: cohort analysis, customer lifetime value

INCLUDE
{ INCLUDE [Product] : AVG([Revenue]) }
→ Adds a dimension even if it is not in your view
→ Use for: averages that need granularity below the viz level

EXCLUDE
{ EXCLUDE [Month] : SUM([Revenue]) }
→ Removes a dimension from the calculation
→ Use for: year-over-year comparisons, benchmarks

Once you understand LOD, you stop working around Tableau.
You start working with it.

Which LOD expression has saved you the most time? 👇

#Tableau #DataVisualization #DataAnalytics #TableauTips #Analytics

---

## Image Suggestion

Three cards: FIXED / INCLUDE / EXCLUDE. Each with definition and use case. Dark theme, Tableau blue. 1200x1200px.