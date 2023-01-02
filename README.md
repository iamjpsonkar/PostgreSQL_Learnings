# SQL and PostgreSQL

## Introduction
SQL - It is the Structured Query Language. It is a programming language.
- 1974
- Manage data held in a Relational Database.
- Data stored in Table, (Column, Row)

PostgreSQL - It is the Database Engine.
- Object-Relational Database Management System

## PostgreSQL

## Installation

Visit https://www.postgresql.org/ and download your OS-specific version

## Running the Server

Start SQL Shell (psql) 

## Commands

```bash
\? : Quit
\help : Help
psql --help : Help
\l : List all the databases
\c dbname : to connect to a database
\d : List of Relations
\dt : List of Tables
```

## Database

What is a Database?
- Store
- Manipulate
- Retrieve

### Creating test database

```sql
CREATE DATABASE test;
```

### Connecting to test database
```sql
~ psql -h localhost -p 5432 -U postgre test
~ \c dbname
```

### Deleting Database
```sql
~ DROP DATABASE test;
```

## Datatypes in PSQL

| **Name**                                    	| **Aliases**            	| **Description**                                                      	|
|-----------------------------------------	|--------------------	|------------------------------------------------------------------	|
| bigint                                  	| int8               	| signed eight-byte integer                                        	|
| bigserial                               	| serial8            	| autoincrementing eight-byte integer                              	|
| bit [ (n) ]                             	|                    	| fixed-length bit string                                          	|
| bit varying [ (n) ]                     	| varbit [ (n) ]     	| variable-length bit string                                       	|
| boolean                                 	| bool               	| logical Boolean (true/false)                                     	|
| box                                     	|                    	| rectangular box on a plane                                       	|
| bytea                                   	|                    	| binary data (“byte array”)                                       	|
| character [ (n) ]                       	| char [ (n) ]       	| fixed-length character string                                    	|
| character varying [ (n) ]               	| varchar [ (n) ]    	| variable-length character string                                 	|
| cidr                                    	|                    	| IPv4 or IPv6 network address                                     	|
| circle                                  	|                    	| circle on a plane                                                	|
| date                                    	|                    	| calendar date (year, month, day)                                 	|
| double precision                        	| float8             	| double precision floating-point number (8 bytes)                 	|
| inet                                    	|                    	| IPv4 or IPv6 host address                                        	|
| integer                                 	| int, int4          	| signed four-byte integer                                         	|
| interval [ fields ] [ (p) ]             	|                    	| time span                                                        	|
| json                                    	|                    	| textual JSON data                                                	|
| jsonb                                   	|                    	| binary JSON data, decomposed                                     	|
| line                                    	|                    	| infinite line on a plane                                         	|
| lseg                                    	|                    	| line segment on a plane                                          	|
| macaddr                                 	|                    	| MAC (Media Access Control) address                               	|
| macaddr8                                	|                    	| MAC (Media Access Control) address (EUI-64 format)               	|
| money                                   	|                    	| currency amount                                                  	|
| numeric [ (p, s) ]                      	| decimal [ (p, s) ] 	| exact numeric of selectable precision                            	|
| path                                    	|                    	| geometric path on a plane                                        	|
| pg_lsn                                  	|                    	| PostgreSQL Log Sequence Number                                   	|
| pg_snapshot                             	|                    	| user-level transaction ID snapshot                               	|
| point                                   	|                    	| geometric point on a plane                                       	|
| polygon                                 	|                    	| closed geometric path on a plane                                 	|
| real                                    	| float4             	| single precision floating-point number (4 bytes)                 	|
| smallint                                	| int2               	| signed two-byte integer                                          	|
| smallserial                             	| serial2            	| autoincrementing two-byte integer                                	|
| serial                                  	| serial4            	| autoincrementing four-byte integer                               	|
| text                                    	|                    	| variable-length character string                                 	|
| time [ (p) ] [ without time zone ]      	|                    	| time of day (no time zone)                                       	|
| time [ (p) ] with time zone             	| timetz             	| time of day, including time zone                                 	|
| timestamp [ (p) ] [ without time zone ] 	|                    	| date and time (no time zone)                                     	|
| timestamp [ (p) ] with time zone        	| timestamptz        	| date and time, including time zone                               	|
| tsquery                                 	|                    	| text search query                                                	|
| tsvector                                	|                    	| text search document                                             	|
| txid_snapshot                           	|                    	| user-level transaction ID snapshot (deprecated; see pg_snapshot) 	|
| uuid                                    	|                    	| universally unique identifier                                    	|
| xml                                     	|                    	| XML data                                                         	|

# Table

### Table Creation

<blockquote>
CREATE TABLE table_name {
  Column_name + Data_type + Constraint if any,
};
</blockquote>

<br/>

#### Creating a Table (without constraint)
```sql
test=# CREATE TABLE person(
  id INT,
  first_name VARCHAR(50),
  last_name VARCHAR(50),
  gender VARCHAR(7),
  date_of_birth DATE );
```

<img src=".\Images\Create_Table_without-constraint.png" alt="Terminal snapshot Table Creation without constraint" />

#### Creating a Table (with constraint)
```sql
test=# CREATE TABLE person(
  id BIGSERIAL NOT NULL PRIMARY KEY,
  first_name VARCHAR(50) NOT NULL,
  last_name VARCHAR(50) NOT NULL,
  gender VARCHAR(7) NOT NULL,
  date_of_birth DATE NOT NULL,
  email VARCHAR(150));
```

<img src=".\Images\Create_Table_with-constraint.png" alt="Terminal snapshot Table Creation with constraint" />
<img src=".\Images\Table_with_constraint.png" alt="Terminal snapshot Table Creation with constraint" />


## List Table of Connected Database

- \b: To describe the tables of connected database
- \b table_name: To know the details of the table_name

<img src=".\Images\Table_Info.png" alt="Terminal snapshot for Table Infor"/>

<br/>

## Delete Table
<blockquote>
DROP TABLE table_name;
</blockquote>

<br/>

<img src=".\Images\Drop_table.png" alt="Terminal snapshot for Delete Table"/>
