What is a trigger in SQL?


Mainly looked at [trusted MS docs](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-trigger-transact-sql?view=sql-server-ver16 "https://docs.microsoft.com/en-us/sql/t-sql/statements/create-trigger-transact-sql?view=sql-server-ver16"):

Triggers  
- It is special type of sql commands set to run (to be triggered) each time an occasion such as new data is persisted into a specific table occurs or even changed/removed and even when the table itself is dropped. So for all data manipulation (DML) actions and data definition (DDL), these set of procedures (triggers) may be defined in a db server.

The syntax is a bit weird (advanced SQL)

Some advantages:
- Speed and consistency
- API doesn't cause unnecessary traffic
- Manual change to database records will cause triggers to run (audits and others will be created)
- Triggers ensure that all Inserts, Updates and Deletes are tracked (CRUD) without the R
- No maintainance of code is crucial


-- SQL Server Syntax  
-- Trigger on an INSERT, UPDATE, or DELETE statement to a table or view (DML Trigger)  
  
CREATE [ OR ALTER ] TRIGGER [ schema_name . ]trigger_name   
ON { table | view }   
[ WITH <dml_trigger_option> [ ,...n ] ]  
{ FOR | AFTER | INSTEAD OF }   
{ [ INSERT ] [ , ] [ UPDATE ] [ , ] [ DELETE ] }   
[ WITH APPEND ]  
[ NOT FOR REPLICATION ]   
AS { sql_statement  [ ; ] [ ,...n ] | EXTERNAL NAME <method specifier [ ; ] > }  
  
<dml_trigger_option> ::=  
    [ ENCRYPTION ]  
    [ EXECUTE AS Clause ]  
  
<method_specifier> ::=  
    assembly_name.class_name.method_name*


* DML trigger statements use two special tables: the [_deleted_ and _inserted_ tables](https://docs.microsoft.com/en-us/sql/relational-databases/triggers/use-the-inserted-and-deleted-tables?view=sql-server-ver16). SQL Server automatically creates and manages these tables. They are  temporary, memory-resident tables

* Encloses a block of SQL statements to be executed
BEGIN  
    { sql_statement | statement_block }   
END

[SQL Server CREATE TRIGGER (sqlservertutorial.net)](https://www.sqlservertutorial.net/sql-server-triggers/sql-server-create-trigger/)
