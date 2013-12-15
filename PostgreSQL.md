Start PostgresSQL from terminal
```
sudo -i -u postgres
```
Create database
```
createdb hiren
```
Connect to a database
```
psql hiren
```
Create Table
```
create table hiren(name varchar(100));
```
Show relations
```
\d hiren
```
Insert data or new row in a table
```
insert into hiren(name) values('nis');
```
Add primary key to existing table
```
alter table hiren add column hiren_id serial primary key;
alter table hiren add column xyz varchar(100) not null;
```
Update
```
update <table name> set <row name>=<value> where <row name> = <value>
```
Data Types

Numerical | Integer,float,numeric,real , serial
Character | char , varchar , text
Logical | Boolean
Temporal | Date , Time , Timestamp ,Interval , Timestamptz