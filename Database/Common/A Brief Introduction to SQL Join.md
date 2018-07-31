# A Brief Introduction to SQL Join
## 1 Background
Recently, my superior let me to export an excel table of the data from the production environment that stored in MySQL database. I didn't think I may come across some troubles before I found that I need to use the data from several tables.I became very confused because the only thing I had ever done is to do the natural join between two tables. So I write this message to introduce the difference between the different type of SQL joins.
 
## 2 Introduction
### 2.1 Inner Join
Inner join is the most common join, and it is the only join measure I can use before I read some references. It is the simplest, most understood join and is the most common. 
<center>

![Inner Join](https://www.codeproject.com/KB/database/Visual_SQL_Joins/INNER_JOIN.png)
</center>
This query will return all of the records in the left table(table A)  that have the matching record in the right table(table B). The join query is written as follows.

```SQL
SELECT <select_list>
FROM TABLE_A a
INNER JOIN TABLE_B b
ON a.key = b.key
```
This query can be written as follows too.
```SQL
SELECT <select_list>
FROM TABLE_A a,TABLE_B b
WHERE a.key = b.key
```
### 2.2 Left Join
Left Join is the most common join in the project of my corporation. 

<center>

![](https://www.codeproject.com/KB/database/Visual_SQL_Joins/LEFT_JOIN.png)
</center>

This query will return all of the records in the left table regardless if any of records have a match in the right table. It will also return any matching records in the right table. This Join is written as follows.
```SQL
SELECT <select_list>
FROM TABLE_A a
LEFT JOIN TABLE_B b
ON a.key = b.key
```
### 2.3 Right Join
Opposites to the Left Join, Right Join returns all of the records in the right table regardless if any of records have a match in the left table. It will also return any of the record matching in the left table.

<center>

![Right Join](https://www.codeproject.com/KB/database/Visual_SQL_Joins/RIGHT_JOIN.png)
</center>
The Join query is written as follows.
```SQL
SELECT <select_list>
FROM TABLE_A a
RIGHT JOIN TABLE_B b
ON a.key = b.key
```
### 2.4 Outer Join
Outer join is the complete set of the left table and the right table. This Join can also be refered to as a FULL OUTER JOIN or a FULL JOIN. 

<center>

![](https://www.codeproject.com/KB/database/Visual_SQL_Joins/FULL_OUTER_JOIN.png)
</center>

This query will return both of the tables, regardless if any of records have a match in the other table, joinning the records in the left table(table A) that match the records from the right table(table B). This Join's query is written as follows.
```SQL
SELECT <select_list>
FROM TABLE_A a
FULL OUTER JOIN TABLE_B b
ON a.key = b.key
```
### 2.5 Left Excluding Join
After this section(including this section), we will talk about some supplementary join apart from the common Joins described above.
Left Excluding Join returns the records in the left table(table A) that do not have any match records in right table(table B).
<center>

![](https://www.codeproject.com/KB/database/Visual_SQL_Joins/LEFT_EXCLUDING_JOIN.png)
</center>
The Join query can be written as follows.
```SQL
SELECT <select_list>
FROM TABLE_A a
LEFT JOIN TABLE_B b
ON a.key = b.key
WHERE b.key is NULL
```
### 2.6 Right Excluding Join
Right Excluding Join is the same as Left Excluding Join. It returns all the records in the right table(Table B) that do not match any records in the right table(Table A)
<center>

![](https://www.codeproject.com/KB/database/Visual_SQL_Joins/RIGHT_EXCLUDING_JOIN.png)
</center>

The Join's query is written as follows.
```SQL
SELECT <select_list>
FROM TABLE_A a
RIGHT JOIN TABLE_B b
ON a.key = b.key
WHERE a.key is NULL
```
### 2.7 Outer Excluding Join
Outer Excluding Join returns all the records in the left table(Table A) and right table(Table B), except the records that match between left table(Table A) and right table(Table B)

<center>

![](https://www.codeproject.com/KB/database/Visual_SQL_Joins/OUTER_EXCLUDING_JOIN.png)
</center>

By the Way, the author of the article that I refer to said that he or she have yet to have a need to use this Join.
This Join's query can be written as follows.

```SQL
SELECT <select_list>
FROM TABLE_A a
FULL OUTER JOIN TABLE_B b
ON a.key = b.key
WHERE a.key is NULL or b.key is NULL
```

### 2.8 Cross Join
Cross Join is to make cartesian product between left table(Table A) and right table(Table B). The query is written as follows.
```SQL
SELECT <select_list>
FROM TABLE_A a, TABLE_B b
```

## 3 References
[Visual Representation of SQL Joins](https://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins)

[Join(SQL)](https://en.wikipedia.org/wiki/Join_(SQL))
