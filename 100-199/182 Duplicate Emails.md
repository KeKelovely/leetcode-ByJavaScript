[Duplicate Emails](https://leetcode.com/problems/duplicate-emails/description/)

### 问题描述
Write a SQL query to find all duplicate emails in a table named Person.
```
+----+---------+
| Id | Email   |
+----+---------+
| 1  | a@b.com |
| 2  | c@d.com |
| 3  | a@b.com |
+----+---------+
```
For example, your query should return the following for the above table:
```
+---------+
| Email   |
+---------+
| a@b.com |
+---------+
```

### 解法描述
1. 使用mySQL语言实现

### 源码
```
# Write your MySQL query statement below
select distinct p1.email from Person p1, Person p2
  where p1.email = p2.email and p1.Id != p2.Id
```
