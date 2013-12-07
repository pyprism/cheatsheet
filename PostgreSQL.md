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
\d
```
Insert data or new row in a table
```
insert into hiren(name) values('nis');
```
