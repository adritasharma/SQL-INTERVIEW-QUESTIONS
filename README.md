# SQL-INTERVIEW-QUESTIONS

<ol>
  
<li>
  
**Keys in DBMS**
  
KEYS in DBMS is an attribute or set of attributes which helps you to identify a row(tuple) in a relation(table)
  
</li> 
  
<ol>  

<li>
  
**Primary key**
  
 Primary key is a set of one or more columns of a table that uniquely identify a record in a database table. It can not accept null, duplicate values.
  
</li> 

<li>
  
**Candidate key**
  
A Candidate Key is a set of one or more columns that can identify a record uniquely in a table. There can be multiple Candidate Keys in one table. Only one Candidate Key can be Primary Key
  
</li> 

<li>
  
**Unique key**
  
A unique key is a set of one or more columns of a table that uniquely identify a record in a database table. It is like Primary key but it can accept only one null value and it cannot have duplicate values
  
</li> 
  
  <li>
  
**Alternate key**
  
An Alternate key is a key that can be work as a primary key. Basically, it is a candidate key that currently is not a primary key.

Example: In a table, RollNo and EnrollNo become Alternate Keys when we define ID as Primary Key.
  
</li> 
  
 <li>
  
**Super key**
  
Super key is a set of one or more than one keys that can be used to identify a record uniquely in a table. Example: Primary key, Unique key, Alternate key are a subset of Super Keys.
  
</li>
  
<li>
  
**Composite/Compound Key**
  
Composite Key is a combination of more than one fields/columns of a table. It can be a Candidate key, Primary key.
  
</li>
  
 <li>
  
**Foreign Key**
  
Foreign Key is a field in a database table that is Primary key in another table
  
</li>
    
 </ol>
 
<li>
  
**SQL Joins**
  
 SQL Join statement is used to combine data or rows from two or more tables based on a common field between them.
  
![image](https://user-images.githubusercontent.com/29271635/170478784-2769facd-2d30-47e8-9e57-bbf932247de1.png)



  
<ol>
  <li>
    
**INNER JOIN**
  
The INNER JOIN keyword selects all rows from both the tables as long as the condition satisfies
    
```
SELECT cr.CountryName, ct.ContinentName
FROM Country cr
INNER JOIN  Continent ct ON ct.ContinentId = cr.ContinentId;
```  
Result:
    
![image](https://user-images.githubusercontent.com/29271635/170473385-e5c3e28f-3b48-4406-851d-fb3d82dacd80.png)
    
    
  </li> 
  
<li>
    
**LEFT JOIN**
  
The LEFT JOIN returns all the rows of the table on the left side of the join and matching rows for the table on the right side of join.
  
 ```
SELECT cr.CountryName, ct.ContinentName
FROM Country cr
LEFT JOIN  Continent ct ON ct.ContinentId = cr.ContinentId;
```  
Result: 
 
![image](https://user-images.githubusercontent.com/29271635/170473458-44142a13-cd59-4a99-87bd-0411f8ef534c.png)
    
</li>
  
 <li>
    
**RIGHT JOIN**
  
The RIGHT JOIN returns all the rows of the table on the right side of the join and matching rows for the table on the left side of join.
   
 ```
SELECT cr.CountryName, ct.ContinentName
FROM Country cr
RIGHT JOIN  Continent ct ON ct.ContinentId = cr.ContinentId;
```  
Result:
   
![image](https://user-images.githubusercontent.com/29271635/170473559-785e16af-c732-4681-b27f-000a3ec805ef.png)
    
</li> 
  
  <li>
    
**FULL JOIN**
  
The FULL JOIN returns all the rows from both the tables. The rows for which there is no matching, the result-set will contain NULL
    
```
SELECT cr.CountryName, ct.ContinentName
FROM Country cr
FULL JOIN  Continent ct ON ct.ContinentId = cr.ContinentId;
```  
Result:  
    
![image](https://user-images.githubusercontent.com/29271635/170473671-526b6d46-c89c-47a8-90e5-21e412943bce.png)
    
</li>  
 
<li>
    
**CROSS JOIN**
  
CROSS JOIN joins all the records from left table with all the records from right table. 
It is not based on matching any column. ON is not required.
Result row count is number of records in left table multiplied by number of records in right table (Cartesian product)
    
```
SELECT cr.CountryName, ct.ContinentName
FROM Country cr
CROSS JOIN  Continent ct ;
```  
Result:  
    
![image](https://user-images.githubusercontent.com/29271635/170476941-74177a58-6c2b-46f4-a07f-e352a274d1d0.png)

</li>  
 
<li> 
	
**NATURAL JOIN**
  
NATURAL JOIN is similar to INNER join but we do not need to use the ON clause during the join. 
SQL joins two tables based on the common column name in these two tables.  
Both tables must have columns with same name and  same data type. (eg: Here ContinentId)
  
It is not allowed in MS SQL Server
    
```
SELECT cr.CountryName, ct.ContinentName
FROM Country cr
NATURAL JOIN  Continent ct
```  
  
Result:
  
 ![image](https://user-images.githubusercontent.com/29271635/170480512-d0964128-a944-4639-b7c6-7bc4f505c0ab.png)

<li> 
  
**SELF JOIN**
  
SELF JOIN is when we join a table to itself. We just use the normal INNER/LEFT join to do a self join with the table having different alias name. 

  ![image](https://user-images.githubusercontent.com/29271635/170652268-cf249825-1f61-4373-8378-a4d114c83bd5.png)

  ```
	SELECT
		emp.EmployeeName as Employee,
		mng.EmployeeName as Manager
	FROM Employee emp 
	JOIN Employee mng ON emp.ManagerId = mng.EmployeeId
```  
  
Result:

  ![image](https://user-images.githubusercontent.com/29271635/170652407-e4fae467-523c-42ea-b9ed-781cfa7e63d2.png)

  
  ```
	SELECT
		emp.EmployeeName as Employee,
		mng.EmployeeName as Manager
	FROM Employee emp 
	LEFT JOIN Employee mng ON emp.ManagerId = mng.EmployeeId
```  
  
Result:
  
 ![image](https://user-images.githubusercontent.com/29271635/170652316-3f60f1b5-df6c-48da-b7d0-2ceb76e6da56.png)
    
  </li>
    
</li> 
</ol> 
</li> 

<li>

**Difference between DROP and DELETE/TRUNCATE** 
	
DROP is used to remove the entire table screma from the DB whereas DELETE/TRUNCATE is used to only remove records	

</li>

<li>

**Difference between DELETE and TRUNCATE** 	
	
<table>
	<tr>
		<td>Delete can be used to remove either few or all the records from a table</td>
		<td>Truncate will always remove all the records from the table. Truncate cannot have WHERE condition</td>
	</tr>
	<tr>
		<td>Delete is a DML statement hence we will need to commit the transaction in order to save the changes to database</td>
		<td>Truncate is a DDL statement hence no commit is required</td>
	</tr>
	<tr>
		<td>Speed is slow because it maintains transaction logs for each deleted record.</td>
		<td>It's execution is fast because it deletes entire data at a time without maintaining transaction logs.</td>
	</tr>
	<tr>
		<td>Doesn't reset the table identity because it only deletes the data</td>
		<td>It always resets the table identity.</td>
	</tr>
	<tr>
		<td>Requires DELETE permission to use this command.</td>
		<td>Requires ALTER permission to use this command.</td>
	</tr>
</table>	
	
</li>

<li>

**Difference between UNION and UNION ALL** 

UNION and UNION ALL are SQL operators used to concatenate 2 or more result sets. This allows us to write multiple SELECT statements, retrieve the desired results, then combine them together into a final, unified set.

The main difference between UNION and UNION ALL is that:

- **UNION**: only keeps unique records
- **UNION ALL**: keeps all records, including duplicates
	
![image](https://user-images.githubusercontent.com/29271635/174777799-af0138e2-847c-4e1f-aad3-f15a88aad4d6.png)

	
![image](https://user-images.githubusercontent.com/29271635/174777914-bb59030a-42d9-4745-8af4-14654faece6b.png)
	
```
SELECT City FROM Student  
UNION  
SELECT City FROM Teacher  
ORDER BY City;  
	
```
  
Result:
	
![image](https://user-images.githubusercontent.com/29271635/174778885-43b5b901-b485-4f24-a321-2a6aa43ca548.png)
	
```
SELECT City FROM Student  
UNION ALL
SELECT City FROM Teacher  
ORDER BY City;  
	
```
  
Result:
	
![image](https://user-images.githubusercontent.com/29271635/174779067-6c6171ad-8fb5-4a0c-b98e-0b9675a719f3.png)

<li> 

**Window functions in SQL**
	
Window functions applies aggregate and ranking functions over a particular window (set of rows). OVER clause is used with window functions to define that window. OVER clause does two things : 

- Partitions rows into form set of rows. (PARTITION BY clause is used) 
- Orders rows within those partitions into a particular order. (ORDER BY clause is used) 	
	
Basic Syntax :  

	SELECT coulmn_name1, 
	 window_function(cloumn_name2),
	 OVER([PARTITION BY column_name1] [ORDER BY column_name3]) AS new_column
	FROM table_name;


	window_function= any aggregate or ranking function    
	column_name1= column to be selected
	coulmn_name2= column on which window function is to be applied
	column_name3= column on whose basis partition of rows is to be done
	new_column= Name of new column
	table_name= Name of table	
	
	
<ol>
<li>	
	
**Ranking Window Functions** : 
	
Ranking functions are, RANK(), DENSE_RANK(), ROW_NUMBER() 
	
**RANK()** function will assign a rank to each row within each partitioned result set. If multiple rows have the same value then each of these rows will share the same rank. However the rank of the following (next) rows will get skipped. Meaning for each duplicate row, one rank value gets skipped.
Rank is assigned such that rank 1 given to the first row and rows having same value are assigned same rank.	
	
**DENSE_RANK()** assigns rank to each row within partition. Just like rank function first row is assigned rank 1 and rows having same value have same rank. 
The difference between RANK() and DENSE_RANK() is that in DENSE_RANK(), for the next rank after two same rank, consecutive integer is used, no rank is skipped.
	
**ROW_NUMBER()** assigns consecutive integers to all the rows within partition. Within a partition, no two rows can have same row number.
	
**ApplicationIssue**
	
![image](https://user-images.githubusercontent.com/29271635/176471885-a51d4898-7881-46a1-b938-e107a20a57b2.png)

	
	SELECT *,
	  RANK() OVER(ORDER BY IssueCount DESC) AS ranks,
	  DENSE_RANK() OVER(ORDER BY IssueCount DESC) AS dense_ranks,
	  ROW_NUMBER() OVER(ORDER BY IssueCount DESC) AS row_numbers
	FROM ApplicationIssue;

Output:
	
![image](https://user-images.githubusercontent.com/29271635/176472370-91184d8f-6da3-4a7a-87c6-923991533215.png)

	
</li>	
</ol> 
	
</li>	
</ol> 
