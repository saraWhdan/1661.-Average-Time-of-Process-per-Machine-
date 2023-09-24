# 1661.-Average-Time-of-Process-per-Machine-
Problem Link:
https://leetcode.com/problems/average-time-of-process-per-machine/submissions/1013377928/?envType=study-plan-v2&envId=top-sql-50

## Solution

```sql
SELECT a1.machine_id
,ROUND(AVG(a2.timestamp-a1.timestamp),3) processing_time 
FROM Activity a1
join Activity a2
ON a1.machine_id=a2.machine_id
AND a1.process_id=a2.process_id
AND a1.activity_type='start'
AND a2.activity_type ='end'
GROUP BY a1.machine_id

