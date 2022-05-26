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
  
  **Continent**                                                                                                      
  
  ![image](https://user-images.githubusercontent.com/29271635/170472125-8974a20e-df8c-48e7-aa86-85d40b50097e.png)       
  
  **Country**
  
  ![image](https://user-images.githubusercontent.com/29271635/170472210-fc7a9736-6a7a-41f3-8876-0117ee1a6126.png)


  
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
It is not based on matching any column. ON is not required
Result row count is number of records in left table multiplied by number of records in right table (Cartesian product)
    
```
SELECT cr.CountryName, ct.ContinentName
FROM Country cr
CROSS JOIN  Continent ct ON ct.ContinentId = cr.ContinentId;
```  
Result:  
    
![image](https://user-images.githubusercontent.com/29271635/170476367-dcf9e737-4819-4066-9afa-37256a31ec9b.png)

    
</li> 
</ol> 
  
</li> 
 </ol> 
