note:1.The semicolon is not strictly required for single statements, however, as it is
       properly a statement separator and not a statement terminator. When passing SQL
       commands into the programming API, the semicolon is not required unless you are
       passing more than one command statement within a single string.
      
    2. 3VL : 3 Value Logic = True ,False , Null. (Null flag for the unknown value or unresolved value )
      3VL also dictates how comparisons work. For example, any equality check (=) involving
      a NULL will evaluate to NULL, including NULL = NULL. Remember that NULL is not a
      value, it is a flag for the unknown, so the expression NULL = NULL is asking, “Does this
      unknown equal that unknown?” The only practical answer is, “That is unknown.”
      It might, but it might not. Similar rules apply to greater-than, less-than, and other
      comparisons.
      
  #####  Here are the truth tables for the 3VL operators NOT, AND, and OR: #####
     
    Value   NOT Value
    True    False
    False   True
    NULL    NULL

    3VL AND    TRUE      FALSE       NULL
    TRUE       TRUE      FALSE       NULL
    FALSE      FALSE     FALSE       FALSE
    NULL       NULL      FALSE       NULL

    3VL OR     TRUE      FALSE       NULL
    TRUE       TRUE      TRUE        TRUE
    FALSE      TRUE      FALSE       NULL
    NULL       TRUE      NULL        NULL


   ##Simple Operators:
   
   Binary operator ::
      -+ : These adjust the sign of a value
      ~  : As in the C language, the “~” operator performs a bit-wise inversion
      NOT : The NOT operator reverses a Boolean expression using 3VL
      ||  : String concatenation.
      + - * / %  : Standard arithmetic operators for addition, subtraction, multiplication, division,
                   and modulus (remainder).
      | & << >>  : The bitwise operators or, and, and shift-high/shift-low
      < <= => >  : Comparison test operators
      = == != <> : Equality test operators. Both “=” and “==” will test for equality, while both “!=”
                   and “<>” test for inequality. Being logic operators, these tests are subject to SQL’s
                   3VL regarding NULLs. Specifically, value = NULL will always return NULL.
      IN LIKE GLOB MATCH REGEXP : These five keywords are logic operators, returning, true, false, or NULL state
      AND OR : Logical operators. Again, they are subject to SQL’s 3VL
      
   Unary prefix operators :: -    +    ~    NOT
                          note : The + is a no-op. It does not do anything. The - unary operator changes positive 
                                 values to  negative and vice versa.      
      
     ## SQLite Storage Class : NULL,Integer,Float,Text,Blob (Binary Large OBject) .Text and BLOB values are always variable length.
     
     
     
   $$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
   

 ### Data Type ::>
 NULL - The value is a NULL value
 INTEGER a signed integer
 REAL - a floating point value
 TEXT - a text string
 BLOB - a blob of data


################################ Commands ################################

help :: .help
quit :: .exit  or .quit 
show attached databases :: .databases
lists the available tables :: .tables
Creating a database :: sqlite3 databasename.db
CREATE table :: CREATE table testing(id integer primary key);
.schema command shows the formal definition of the table ::  .schema testing
show table :: .table  or .tables 
drop table :: drop table testing;

      :::ALTER TABLE :::
   The ALTER TABLE command in SQLite allows the user to rename a table or to add a new column to an existing table. It is not
   possible to rename a column, remove a column, or add or remove constraints FROM a table.
   
Rename table :: alter table testing rename to testings;
Add a new colom to the table :: alter table testings add column email text;    
    
     
     ::: Inserting, updating and deleting data ::: 
   
  CREATE newtable :: sqlite> CREATE TABLE Books(id integer primary key, title text, author text, 
                        ...> isbn text default 'not available');
  Insert value    :: sqlite> INSERT INTO Books(id, title, author, isbn) 
                        ...> VALUES(1, 'War and Peace', 'Leo Tolstoy', '978-0345472403');
                     sqlite> INSERT INTO Books(title, author, isbn) 
                        ...> VALUES('The Brothers Karamazov', 'Fyodor Dostoyevsky', '978-0486437910'); --id column r auto increment bcoz
                                                                                                       --they ar SELECTed as
                                                                                                       --'primary key'
                     sqlite> INSERT INTO Books VALUES(3, 'Crime and Punishment', 'Fyodor Dostoevsky', 
                        ...> '978-1840224306');  --In this SQL statement, we did not specify any column names after the 
                                                 --table name. In  such a case, we have to supply all values.
                      sqlite>INSERT INTO Books(id, title) VALUES(4, 'Paradise Lost');
  
  replace value :: sqlite> INSERT OR REPLACE INTO Books VALUES(4, 'Paradise Lost', 'John Milton',
                      ...> '978-0486442877');
  CREATE temporary table :: sqlite> CREATE TEMP TABLE BooksTemp(id integer primary key, title text, 
                               ...> author text, isbn text);
                            sqlite>INSERT INTO BooksTemp SELECT * FROM Books;
  Deleting data :: sqlite> DELETE FROM BooksTemp WHERE id = 1; --delete row 1
                   sqlite> DELETE FROM BooksTemp; --delete everything FROM the table
  Update data :: sqlite> UPDATE Books SET author='Lev Nikolayevich Tolstoy' WHERE id=1; --here we update row 1
  search row ::  sqlite> SELECT * FROM Books WHERE id = 4;
  show null value :: .nullvalue null  --u can set any word LIKE .nullvalue fazil
  To view the full table :: sqlite> SELECT * FROM Books;
  
   
   ::: SELECT statement :::
   
  Retrieving all data FROM specific table :: sqlite> SELECT * FROM books;
  SELECTing specific columns :: sqlite> SELECT author FROM books;
                                sqlite> SELECT title FROM books;
  Renaming column names :: sqlite> SELECT title,author as paglakobi FROM books; --just rename author column
  Limiting data output :: sqlite> SELECT * FROM books limit 2;
                       The OFFSET clause following LIMIT specifies how many rows to skip at the beginning of
                       the result set :: sqlite >> SELECT * FROM books limit 2 offset 1;
  Orderig data :: The ASC keyword sorts the data in ascending order, the DESC in descending order.
                 sqlite > SELECT title FROM books order by title asc;
                 sqlite> SELECT title FROM books order by title desc;
  Search specific pattern :: sqlite > SELECT title FROM books WHERE title LIKE 'c%';
  Removing duplicate items :: sqlite > SELECT DISTINCT title FROM books WHERE title LIKE 'c%';
  
   :::Grouping data:::
  GROUP BY clause :: sqlite> SELECT sum(OrderPrice) AS Total, Customer FROM Orders GROUP BY Customer; --The sum() function returns 
                                                                                                      --the total sum of a numeric      
                                                                                                      --column
  
                     sqlite> SELECT sum(OrderPrice) AS Total, Customer FROM Orders   --We cannot use the WHERE clause when aggregate 
                         --> GROUP BY Customer HAVING sum(OrderPrice)>1000;          --functions were used.We use the 
                                                                                     --HAVING clause instead.
                     sqlite> SELECT sum(OrderPrice) AS Total, Customer FROM Orders 
                         --> GROUP BY Customer HAVING sum(OrderPrice)>1000;    --The above SQL statement selects customers whose total 
                                                                               --orders where greater than 1000 units.
  
  
     ::: Constraints :::
   
     |--> NOT NULL
     |--> UNIQUE
type-|--> PRIMARY KEY
     |--> FOREIGN KEY
     |--> CHECK
     |--> DEFAULT                   
  NOT NULL constraint :: A column with a NOT NULL constraint, cannot have NULL values.
                        sqlite> CREATE TABLE People(Id integer, LastName text NOT NULL,
                                 FirstName text NOT NULL, City text);
  UNIQUE constraint :: The UNIQUE constraint ensures, that all data are unique in a column.
                       sqlite> CREATE TABLE Brands(Id integer, BrandName text UNIQUE);
       note: Note that a PRIMARY KEY constraint automatically has a UNIQUE constraint defined on it.                     
  
  Primary key :: sqlite> CREATE TABLE Brands(Id integer PRIMARY KEY, BrandName text);
       note : In SQLIte if a column is integer and primary key, it is also autoincrement.
       
  Foreign key :: A FOREIGN KEY in one table points to a PRIMARY KEY in another table. It is a referential constraint between two tables.
              sqlite> CREATE TABLE Authors(AuthorId integer PRIMARY KEY, Name text);
               sqlite> CREATE TABLE Books(BookId integer PRIMARY KEY, title text, AuthorId integer, 
                   --> FOREIGN KEY(AuthorId) REFERENCES Authors(AuthorId));
           We create the Books table. Here we have an AuthorId column name, which acts as a foreign key. It references to the primary  
           key of the Authors table.  

 Check constraint ::   
  
  sqlite> .schema Orders
           CREATE TABLE Orders(Id integer PRIMARY KEY, OrderPrice integer CHECK(OrderPrice>0), 
                    Customer text);
  We look at the definition of the Orders table. We see a CHECK constraint imposed on the OrderPrice column. Logically, the price of an
   order must be a positive value.
  
  Default constraint :: 
  sqlite> CREATE TABLE Hotels(Id integer PRIMARY KEY, Name text, 
                            City text DEFAULT 'not available');
  The DEFAULT constraint inserts a default value into the column, if no value is available.
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
      
      
      
      
      
      
      
