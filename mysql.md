####Connect from terminal
```
mysql -u <user> -p
```
####Create database
```
create database <databaseName>
```
####Show databases
```
show databases
```
####Connect to a database
```
use <databaseName>
```
####Create table
```
create table <name>(
    <col-name> <col-type>,
    <col-name> <col-type>
    );
```
####Table deffinition
```
explain <tableName>
```

              ################    MySQL   Data    Type  ####################
              
                      :::MySQL text types:::
     Text type        Maximum number of bytes
       Tinytext       255
       Text           65,535
       Mediumtext     6,777,215
       Longtext       4,294,967,295
    
                     :::MySQL integer types:::
   Type             Signed range                                                                      Unsigned range
   Tinyint          −128 to 127                                                                       0 to 255
   Smallint         −32,768 to 32,767                                                                 0 to 65,535
   Mediumint        −8,388,608 to 8,388,607                                                           0 to 16,777,215
   Int              −2,147,483,648 to 2,147,483,647                                                   0 to 4,294,967,295
   Bigint           −9,223,372,036,854,775,808 to 9,223,372,036,854,775,807                           0 to 18,446,744,073,709,551,615
   
   
                      :::MySQL floating-point types::::
       Type                                Numeric range
       Float(p,s)                          −3.402823466E+38 to −1.175494351E-38
                                           and 1.175494351E-38 to 3.402823466E+38
                                           
       Double(p,s)                         −1.7976931348623157E+308 to −2.2250738585072014E-308
                                           and 2.2250738585072014E-308 to 1.7976931348623157E+308
                                           
       
                      :::MySQL temporal types:::
       
     Type            Default format                    Allowable values
     Date            YYYY-MM-DD                        1000-01-01 to 9999-12-31
     Datetime        YYYY-MM-DD HH:MI:SS               1000-01-01 00:00:00 to 9999-12-31 23:59:59
     Timestamp       YYYY-MM-DD HH:MI:SS               1970-01-01 00:00:00 to 2037-12-31 23:59:59
     Year            YYYY                              1901 to 2155
     Time            HHH:MI:SS                         −838:59:59 to 838:59:59
     
     
                      :::Date format components:::
     Component        Definition                    Range
     YYYY             Year, including century       1000 to 9999 
     MM               Month                         01 (January) to 12 (December)
     DD               Day                           01 to 31
     HH               Hour                          00 to 23
     HHH              Hours (elapsed)               −838 to 838
     MI               Minute                        00 to 59
     SS               Second                        00 to 59
     
     $$$$$$$$$$$$$$$$$$$$$ From CBT Nugget  $$$$$$$$$$$$$$$$$$$$$$
                      :::MySQL String Datatype:::
     
     >>char:fixed length,non-binary           0-255 
     >>varchar:variable length,non-binary     0-65,535
     >>text,tinytext,mediumtext,longtext
     >>binary:fixed length,binary             0-255       
     >>varbinary:variable length,binary       0-65,535                   
     >>blob(BLOB=Binary Large Obeject Data),tinyblob,mediumblob,longblob  (blob used for encrypted data)
     >>enum:integer list(select one)
     >>set:binary list(select >=1) 
     
                       :::MySQL Floating Point:::
     >>Float : single precision
     >>Double : Double precision
     >> Decimal : var. precision
     
                       :::MySQL Temomporal Data ::
        Type   Storage-Required     Range
     >>Date        3 bytes          1000-01-01 to 9999-12-31
     >>time        3 bytes          -838:59:59 to 838:59:59
     >>datetime    8 bytes          1000-01-01 00:00:00 to 9999-12-31 23:59:59
     >>timestamp   4 bytes          1970-01-01 00:00:00 to mid-year 2037
     >>year        1 byte            1901 to 2155(for year(4)) , 1970 to 2069(for year(2))
     
############################### MySQL Commond ########################################

login :  mysql -u root -p
show available database : SHOW DATABASES;
Create database : CREATE DATABASE databasename;
select database : use databasename;
show table of previously selected database : SHOW TABLES;
use the describe command (or desc for short) to look at the table definition:  DESC tablename; |or|  describe tablename;
Table create : CREATE TABLE tablename ( data type declare );

###########################@@@@@@###############

Show table definition : explain tablename;
INSERT DATA : insert into tablename values(DATA);
OR  insert into tablename(column) value (data);
Select data : select * from tablename;
or select columnName,columnName2 from tablename;

Data Type :
varchar  = create table person( name varchar(100)) ;
text = create table emai ( body text);
int  = create table person (age integer);
int  = create table person (age integer unsigned );  # expected +ve value
*There is also tinyint and mediumint 
decimal = create table student(av g_score deimal(10,5) ; #decimal(precision ,scope)
auto_increment = create table student( id integar auto_increment) ;
date , time ,datetime :
date  = 'YYYY-MM-DD'
time = '[H]HH:MM:SS'
datetime =  'YYYY-MM-DD HH:MM:SS'
ex. create table order(order_date date) ;
Bool : 0 is false and non-0 is true 
ex. create table order (fulfilled boolean);
Default values : create table order ( coupon varchar(100) default "no discount" ) ;

Primary key : create table hiren( id int primary key auto_increment);


Alter:
Alter table : alter table tableName rename newTableName ;
Alter Column : alter table cases add columnName varchar(100);
Alter ..............


Delete And Drop:
Drop table : Drop table tableName ; 
delete : delete from tableName ; 

Update :
update ..................................

Where ,limit:
Select * from tableName where x = "a";
operators for where :-
=            ALL        NOT
>            AND       OR
<            ANY        SOME
>=          Between   IN 
<=          EXITS      LIke
<>
!=

select * from tableName Limit 5;
