---
title: "Backup Mysql Database"
source: "Backup MySQL Database.docx"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "MySQL Import and Export using MySQL Dump Why we cannot just copy data or rename databases Traditionally MySQL data used by Newline has always sto..."
long_description: "MySQL Import and Export using MySQL Dump"
---

MySQL Import and Export using MySQL Dump

Why we cannot just copy data or rename databases

Traditionally MySQL data used by Newline has always stored data in MyISAM tables, these whilst very functional for certain operations doesn’t support transactions (See ACID Compliancy) and triggers. InnoDB supports these features but stores data differently.

You can read a stack of info on the differences between the 2 table types but a brief overview here is:

Pros

MyISAM is best suited for high “select” query rate, and non transactional operations.

InnoDB is best suited for parallel insert/update/delete operations (because of row level locking), and transactional operations (because of roll back feature).

Memory engine (HEAP) is best suited for on the fly fast data access, as everything is stored in the RAM.

InnoDB is crash safe meaning if data is being written to a table and a crash occurs the log information allows the operation to be replayed or continued.

Cons

MyISAM is worst for high “insert/update” query rate. (because of table level locking).

InnoDB is worst when there is combination of non-transactional and read only operations.

Memory engine is worst for long term usage (because Of data integrity issues) and transactional operations.

MyISAM is not crash safe meaning if data is being written to a table and a crash occurs the data will need repairing

http://www.thegeekstuff.com/2014/02/myisam-innodb-memory/

http://www.thecreativedev.com/what-are-the-main-differences-between-innodb-and-myisam/

Additionally, Newline are making use of stored procedures which although can be used in a database or indeed databases aren’t stored within the database.

To backup a database using MySQLDump navigate to the BIN folder within the MySQL installation and run the following command

MySQLDump --triggers --routines --Lock-Tables=False --u=root --p NewlineSQL > c:\nldata\mysqldump.sql

Should this fail on an old version of MySQL 4 run the following:

MySQLDump --Lock-Tables=False --u=root --p NewlineSQL > c:\nldata\mysqldump.sql

This will backup the NewlineSQL database to a file called C:\NLData\MySQLDump.sql

To restore this database using dbForge perform the following: