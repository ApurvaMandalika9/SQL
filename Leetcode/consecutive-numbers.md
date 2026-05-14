### 180. Consecutive Numbers
Table: Logs


| Column Name | Type    |
|-------------|---------|
| id          | int     |
| num         | varchar |

In SQL, id is the primary key for this table.
id is an autoincrement column starting from 1.
 

Find all numbers that appear at least three times consecutively.

Return the result table in any order.

### Solution :
# Write your MySQL query statement below
Select distinct(num) as ConsecutiveNums 
from (
    Select LAG(num) OVER (ORDER BY id) AS prev, num, LEAD(num) OVER (ORDER BY id) AS next
    From Logs
    ) a
where (a.prev = num) and (num = a.next)