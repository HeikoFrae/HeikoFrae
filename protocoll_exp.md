# Day 28, 11.06.2024 
<span style="color:grey">   
  
  Protocol writer: **Ankit**  
  Next protocol writer: **Abinaya**  
  ___
## <span style="color:black"> __Basic Overview__ </span>
  On this day(s) the focus was on SQL.

---
##  __Schedule__
<span style="color:grey">  

### 11.06.2024  
|Time|Content|
|---|---|
|09:00 - 09:30|Daily Protocol for 06.06.2024 and 10.06.2024|
|09:30 - 09:45|Validating new Postgres credentials and solving connection issues.|
|09:45 - 11:00|Introduction to Structured Query Language (SQL)|
|11:00 - 11:30|Excerise Q1 to Q3 |
|11:30 - 11:45|Discuss Q1 to Q3 queries|
|11:45 - 12:15|Flitering Data in SQL|
|11:15 - 12:45|Excerise Q4 to Q7 |
|12:45 - 13:45|Lunch Break|
|13:45 - 15:00|Aggregating Data in SQL| 
|15:00 - 17:00|Excerise Q8 to Q20|

---
## <span style="color:black"> __Structured Query Language__ </span>
<span style="color:grey">    
  
### 1. What is this?  
* SQL is a standard language for storing, manipulating and retrieving data in databases. SQL is a computer language used to interact with relational database systems. SQL is a tool for organizing, managing, and retrieving archived data from a computer database.

### 2. Type of SQLs:  
* Data Definition Language - SQL commands used to create the database structure are known as data definition language (DDL). Based on the needs of the business, database engineers create and modify database objects using DDL. The CREATE command, for instance, is used by the database engineer to create database objects like tables, views, and indexes.Example commands are Create, Alter, Drop, etc.

* Data Manipulation Language - A relational database can be updated with new data using data manipulation language (DML) statements. The INSERT command, for instance, is used by an application to add a new record to the database. Example commands are Select, Insert, Update, Delete.

* Data Control language - Data control language (DCL) is a programming language used by database administrators to control or grant other users access to databases. For instance, they can allow specific applications to manipulate one or more tables by using the GRANT command. Example commands are Grant and Revoke.

### What can SQL do?
SQL can
* create new databases
* create new tables in a database
* create stored procedures in a database
* create views in a database
* execute queries against a database
* retrieve data from a database
* insert records in a database
* update records in a database
* delete records from a database
* set permissions on tables, procedures, and views

</span>

---
## <span style="color:black"> SQL Query Structure </span>

<span style="color:grey">  

* How does the structure of SQL look like?
  Below is the format of a simple SQL query  
  ```
  Select <column_name>  
  from <table_name>  
  where <condition>  
  group by <column_name>  
  having <condition>  
  order by <column_name> <sort_order>
  ```
  
  SELECT - Returns the final data  
  FROM - Choose tables to get base data  
  WHERE - Filters the base data  
  GROUP BY - Aggregates the base data  
  HAVING - Filters the aggregated data  
  ORDER BY - Sorts the final data  
  LIMIT - Limits the returned data to a row count

  Example:

  Select *  
  from airports  
  where city = 'Berlin'

  ---
## <span style="color:black"> DDL and DML Commands </span>

<span style="color:grey">  

* Below is the table against which all the queries are ran.
  <img width="1117" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/c51a01da-fd80-4437-907a-25da9e5802c3">

* Selecting all data from table  
  ```
  Select *
  from airports
  ```

  Output:
  <img width="1150" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/6c07c34a-2a2a-410f-b4eb-b5bb002e7cfa">

* Selecting a column data from table  
  ```
  Select name
  from airports
  ```

  Output:  
  <img width="420" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/972a1f85-d538-4ad4-9362-cd55eafe76b2">

* Selecting multiple columns data from table  
  ```
  Select faa,name
  from airports
  ```

  Output:  
  <img width="472" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/64e71160-e46a-46b4-8b7c-e722bac970f5">

* Get unique values in a column  
  ```
  Select distinct(country) 
  from airports
  ```

  Output:  
  <img width="274" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/dac6f539-07b3-43d1-9862-5c339e113acd">

* Count values in a column  
  ```
  Select count(name) 
  from airports
  ```

  Output:  
  <img width="252" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/0b79c787-95fc-4141-8354-eb0196413521">

* Filter data on column - Where clause followed by a condition helps to filter data. Below are list of operand available for condtion checking.

  |Operator|Description|  
  |---|---|
  |= |Equal|
  |> |Greater than|
  |< |Less than|
  |>= |Greater than or equal|
  |<= |Less than or equal|
  |<> or != |Not equal|
  |BETWEEN |Between a certain range|
  |LIKE |Search for a pattern (use %, _ etc. sign as wildcard)|
  |IN |To specify multiple possible values for a column|  

  ```
  Select * 
  from airports
  where city = 'Berlin'
  ```

  Output:  
  <img width="1051" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/d99b8be6-e0de-4c72-88ca-7f20c9871ce1">

* Sorting data on column - 'Order by' clause followed by a column  name and sorting data is used to sort data in table. Sort data can be either ASC (Ascending) or DESC 
  (Descending). By default it is ASC. Instead of column name you can also provide column index.


  Sorting by column name  
  ```
  Select * 
  from airports
  order by faa
  ```

  Output:  
  <img width="1084" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/0ecdd58c-ddf0-412d-a535-f09bbf831c03">

  Sorting by column index. In the airports table, the columns will have index starting from 1 to last column. That means in out example, as per the current order of columns the faa will have index 1 and name will have index 2 and so on.  
  ```
  Select * 
  from airports
  order by 2 desc
  ```

  Output:  
  <img width="1082" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/d40e3877-85a7-48a8-98c1-334901b983bb">

* Aliasing column or table name - It allows you to give a column or a table a new temporary name within the query. An alias is created with the AS keyword

  Sorting by column name  
  ```
  Select faa as Airpot_code, name as Airport_name 
  from airports as a
  ```

  Output:  
  <img width="525" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/8f8d7472-271f-4486-b3fd-9c3b8faaa105">

* Aggregating Data
  * Min - Returns minimum value in the column
    ```
    Select min(alt)
    from airports
    ```

    Output:  
    <img width="293" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/cc4e8b96-7f21-4c50-8d47-f5f971ad580f">

  * Max - Returns maximum value in the column
    ```
    Select max(alt)
    from airports
    ```

    Output:  
    <img width="248" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/28bedc39-abec-4b6b-ba62-424e22ea8b0a">

  * Avgerage (AVG) - Returns average of values in the numeric column
    ```
    Select avg(alt)
    from airports
    ```

    Output:  
    <img width="269" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/0c270bc9-97c5-44be-b4ec-7273cfd14aa9">

  * Sum - Returns sum  of values in the numeric column
    ```
    Select sum(alt)
    from airports
    ```

    Output:  
    <img width="229" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/079b607a-4e74-4334-9742-396e40afebe9">

  * Arithmetic Operators - Arithmetic operators can perform addition, subtraction, multiplication and division on numeric values.
    |Operator|Meaning|  
    |---|---|
    |+ |Addition|
    |- |Subtraction|
    |* |Multiplication|
    |/ |Division|
    |% |Modulo|

    * Addition Operation
      ```
      Select name, alt, alt+100 AS Corrected_alt
      from airports
      ```

      Output:  
      <img width="611" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/30e0cfa6-cece-4f3e-a5ec-07fdee42959d">

    * Subtraction Operation
      ```
      Select name, alt, alt-100 AS Corrected_alt
      from airports
      ```

      Output:  
      <img width="607" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/c84315a8-7215-4744-b205-e5fa4eb8087d">

    * Multiplication Operation
      ```
      Select name, alt, alt*100 AS Corrected_alt
      from airports
      ```

      Output:  
      <img width="585" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/4248d201-f9e5-430b-a181-a688b1df5c22">

    * Division Operation
      ```
      Select name, alt, alt/100 AS Corrected_alt
      from airports
      ```

      Output:  
      <img width="599" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/eb2ac399-583b-414c-85f2-12a68ac2b30f">

    * Modulus Operation
      ```
      Select name, alt, alt%100 AS Corrected_alt
      from airports
      ```

      Output:  
      <img width="597" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/f1bec47e-4930-4141-9a73-1fe2a70536e5">

 
  * Group By - Lets you arrange identical data across rows into groups. This can be used in combination with aggregate functions (MIN(), MAX(), AVG(), COUNT(),
    SUM()) to create summary reports across columns.
     ```
    Select count(*)
    from airports
     group by country
    ```

    Output:  
    <img width="310" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/19a88ad2-5f00-4c50-9ea5-33f7e8258c62">


  * Having - Aggregate functions can’t be used to filter data inside the WHERE clause, instead use HAVING.
     ```
    Select count(*)
    from airports
     group by country
     having count(*) > 50
    ```

    Output:  
    <img width="348" alt="image" src="https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/assets/48177723/1e969fb5-749b-450c-a8b9-ebd8318179a5">


___
## 11.06.2024 Attendance

![Our group photo from 11.06.2024](https://github.com/neuefische/cgn-analytics-24-2-daily-protocol/blob/8de80b3a4fb5e257ec75beaa855f44347bd2853d/Screenshots_images/Screenshot%202024-06-11%20at%2009.18.20.png)  

---
