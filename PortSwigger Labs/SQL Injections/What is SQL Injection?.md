SQL Injection: 
SQL injection is a type of web application vulnerability that occurs when an attacker can insert user input directly into an SQL query without proper validation. The attacker can manipulate the SQL queries by injecting SQL code which then allow the attacker to bypass login, retrieve hidden data, modify database records and can also execute administration operations.
HOW SQL OCCURS:
A website has a login form, when user enters the data the SQL query executes and validate the user. The attacker can bypass login by breaking the query flow and create their own version of the query that the server will receive. There are some operations that are most commonly performed by the attacker:
1.	‘ : This comma breaks the query as it closes the original string, after this the attacker can design whatever they want to receive
2.	1=1: This is condition check that always remains true as 1 = 1. This is used when the attacker need to prove something is true to gain access.
3.	OR / AND: These are the logical operators that determine the result of query execution. OR is when either of the statements is true, execute the command. AND is when either of the statement is false, ignore the command. This is mostly use alongside the crafted query to make it execute in all circumstances.
4.	--: These dashes are used to ignore the query slice that is written after them. And only execute the query that exist before it.
