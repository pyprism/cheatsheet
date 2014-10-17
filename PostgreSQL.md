Start PostgresSQL from terminal
```
sudo -i -u postgres
```
Create user
```
$ sudo su - postgres
createuser --interactive -P
```

Create database
```
createdb --owner ownername databasename
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

Type | Name
--------|-----------
Numerical | Integer,float,numeric,real , serial
Character | char , varchar , text
Logical | Boolean
Temporal | Date , Time , Timestamp ,Interval , Timestamptz
Binary | Bytea , Bit , Bit Varying
Geo-Spatial | Point , Path , Polygon , Circle , Line
Internet | Inet , Cidr , Macaddr
Special | Enum , Range , Json , Xml ,Oid
Array | []
Composite type | Type

###CLI
change to postgres user and open psql prompt
```
sudo -u postgres psql postgres
```
list databases
```
postgres=# \l
```
list roles
```
postgres=# \du
```
create role
```
postgres=#CREATE ROLE demorole1 WITH LOGIN ENCRYPTED PASSWORD 'password1' CREATEDB;
```
alter role
```
postgres=#ALTER ROLE demorole1 CREATEROLE CREATEDB REPLICATION SUPERUSER;
```
drop role
```
postgres=#DROP ROLE demorole1;
```
create database
```
postgres=#CREATE DATABASE demodb1 WITH OWNER demorole1 ENCODING 'UTF8';
```
grant privileges to new user
```
GRANT ALL PRIVILEGES ON DATABASE demodb1 TO demorole1;
```
drop database

```
postgres=#DROP DATABASE demodb1;
```
connect to database

```
\c <databasename>
```
list tables in connected database

```
\dt

```
list columns on table

```
\d <tablename>
```
backup database
```
pg_dump <databasename> > <outfile> 
```














