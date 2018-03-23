## Description of datasets.sat_scores
Table contains 

## question #1
Which school has the highest average SAT writing score?

```sql
Select school, avg(sat_math + sat_verbal + sat_writing) as avg_sat_score
  from datasets.sat_scores
  group by school
  order by avg_sat_score desc
```
![README](visualizations/#1.jpg)
