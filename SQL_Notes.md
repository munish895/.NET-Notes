### SQL Notes

https://www.geeksforgeeks.org/sql-interview-questions/

1. What is SQL? 
SQL stands for Structured Query Language. It is a language used to interact with the database.
SQL is an ANSI(American National Standards Institute) standard.

2. What is a database? 
A Database is defined as a structured form of data storage in a computer.
Databases help us with easily storing, accessing, and manipulating data held on a computer. The Database Management System allows a user to interact with the database.

3. BETWEEN - fetch rows based on range of values, first and last excluded.

4. IN - values contained in specific sets, nothing is excluded.

5. Staring with, ending with, contains - LIKE is used.

6. char vs varchar
char - fixed length string. - char(5) - {1,2,3,4,5}
varchar - variable length string - nvarchar(5)- {2,3,9},{1},{1,2},{1,2,3,4,5}

<b>nchar</b> and <b>nvarchar</b> can store Unicode characters.
<b>char</b> and <b>varchar</b> cannot store Unicode characters.
<b>char</b> and <b>nchar</b> are fixed-length which will reserve storage space for number of characters you specify even if you don't use up all that space.
<b>varchar</b> and <b>nvarchar</b> are variable-length which will only use up spaces for the characters you store. It will not reserve storage like char or nchar.
<b>nchar</b> and <b>nvarchar</b> will take up twice as much storage space, so it may be wise to use them only if you need Unicode support.

7. Name different types of case manipulation functions available in SQL.
LOWER - LOWER(‘string’) - lowercase - akash
UPPER - UPPER(‘string’) - uppercase - AKASH
INITCAP - INITCAP(‘string’) - first letter capital and rest in lowercase - Akash

8.  What do you mean by data definition language?
Data definition language or DDL allows to execution of queries like CREATE, DROP, and ALTER. That is those queries that define the data.

9. What do you mean by data manipulation language?
 Data manipulation Language or DML is used to access or manipulate data in the database. 
It allows us to perform the below-listed functions: 

- Insert data or rows in a database
- Delete data from the database
- Retrieve or fetch data
- Update data in a database.

10. What is the difference between primary key and unique constraints? 
The primary key cannot have NULL values, the unique constraints can have NULL values. There is only one primary key in a table, but there can be multiple unique constraints. The primary key creates the clustered index automatically but the unique key does not.

11. clustered vs non clustured.