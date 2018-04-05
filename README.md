## Description of datasets.sat_scores
This table contains 3 categorical data, including school name, teachers' names and student ID, as well as 4 numerical data including SAT writing scores, SAT verbal scores, SAT math scores and the hours that each student studied for the test.

## question #1
Which school has the highest average SAT writing score?

```sql
Select school, avg(sat_math + sat_verbal + sat_writing) as avg_sat_score
  from datasets.sat_scores
  group by school
  order by avg_sat_score desc
```
![fdf](Visualizations/Graph1.png)

## question #2
Which teacher has the most students?

```sql
Select teacher,
Count (student_id)
From datasets.sat_scores
group by teacher
Order by count desc
```
![fdf](Visualizations/Graph2.png)

## question #3
Which school has the most hard-working students based on average study hours?

```sql
Select school, avg(hrs_studied)
from datasets.sat_scores
group by school
Order by school desc
```
![fdf](Visualizations/Graph3.png)

## question #4
Is there a correlation between hours studied and the total test score?

```sql
Select hrs_studied, sum(sat_math + sat_verbal + sat_writing) as total_sat_score
  from datasets.sat_scores
  group by hrs_studied
  order by hrs_studied ASC
```
