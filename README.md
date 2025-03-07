# SQL_Learning

Important topics for sql

-> Joins(left,right,inner,full,cross,self)
-> CTE (Common table expression) & recursive cte
-> How to write Subqueries
-> Window function(Rank,dense rank,Row number,lag,lead,moving average)
-> Indexing
-> Views and Temporary Table
-> Trigger
-> Sql merge concept
-> Acid property
-> Nolock
-> SHarding and partioning


JOINS

Inner join ->>> Common data from both the table
Left join ->> COmmon data + data left in the left table
Right Join --> Common data + data left in the right table
Full Join ->> Common data + data left in the left table + data left in the right table
Cross Join -->> Multiplication of rows
Self join -->> 


employee

Question: Find the employee who earns more than his manager.

select b.* from employee a join employee b on a.id = b.managerId  where b.salary > a.salary


| id | team_name |
| — — | — — — — — — — |
| 1 | India |
| 2 | Pakistan |
| 3 | Australia |
| 4 | England |
| 5 | South Africa |
| 6 | New Zealand |

Question: Given a table named “teams” with columns `id` and `team_name`, schedule matches between teams such that no team plays against the same team twice, and no team plays multiple matches at the same time.

| id | team_name |
| — — | — — — — — — — |
| 1 | India |
| 2 | Pakistan |
| 3 | Australia |
| 4 | England |
| 5 | South Africa |
| 6 | New Zealand |


Expected Output Table:

| team1 | team2 |
| — — — — — — | — — — — — — — |
| India | Pakistan |
| India | Australia |
| India | England |
| India | South Africa |
| India | New Zealand |
| Pakistan | Australia |
| Pakistan | England |
| Pakistan | South Africa |
| Pakistan | New Zealand |
| Australia | England |
| Australia | South Africa |
| Australia | New Zealand |
| England | South Africa |
| England | New Zealand |
| South Africa | New Zealand |

select t1.name as team1,t2.name as team2 from team t1 join team t2 on t1.id < t2.id;


