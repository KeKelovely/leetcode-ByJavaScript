[Nth Highest Salary](https://leetcode.com/problems/nth-highest-salary/description/)

### 问题描述
Write a SQL query to get the nth highest salary from the Employee table.
```
+----+--------+
| Id | Salary |
+----+--------+
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |
+----+--------+
```
For example, given the above Employee table, the nth highest salary where n = 2 is 200. If there is no nth highest salary, then the query should return null.
```
+------------------------+
| getNthHighestSalary(2) |
+------------------------+
| 200                    |
+------------------------+
```

### 解法
1. mySQL语言实现

### 源码
```
CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT
BEGIN
    
  RETURN (
      # Write your MySQL query statement below.
      SELECT e1.Salary
      FROM (SELECT DISTINCT Salary FROM Employee) e1
      WHERE (SELECT COUNT(*) FROM (SELECT DISTINCT Salary FROM Employee) e2 WHERE e2.Salary > e1.Salary) = N - 1        
      LIMIT 1
  );
END
```
