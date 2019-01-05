
//for MySQL 8.0 Command Line Client - Unicode


- show all databases:                             show databases;
- create new database:                            create database [database];
- select database:                                use database [database];
- determine which database is in use:             select [database];
- create new table:                               create table [name] ([column1] int(11),[column2] varchar(255),[column3]
                                                  datetime);
- show all tables:                                show tables;
- show the structure of table:                    describe [table];
- describe all indexes on a table:                show index from [table];
- add a column:                                   alter table [name] add column [name] varchar(255);
- add a column with unique,auto-incrementing ID:  alter table [name] add column [name] int not null auto_increment primary key; 
- change a column to add UQ,AI ID: 
- delete a column from table:                     alter table [name] drop [column];
- delete a table:                                 drop table [table];
- delete all records from table(without deleting
  table itself):                                  delete from [table];
- delete all records in table:                    
- inserting a record:                             insert into [table] ([column1],[column2]) values ('[value1]','[value2]');
- update a record:                                update [table] set [column] = '[updated-value]' where [column] = [value];
- delete records:                                 delete from [table] where [column] = [value];
- delete database:                                drop database [database];


ddl
-create table triangle (a float,b float,
 c float as (sqrt(a*a+b*b)));
- insert into triangle (a,b) 
  values (12.5,7.5);
  
-create table fullnam (

select 

- select all records:                             select * from [table];
- select all record limited:                      select * from [table] limit 10;
- explain records:                                explain select * from [table];
- selecting parts of records:                     select [column], [another-column] from [table];
- count records:                                  select count ([column]) from [table];
- count and select grouped records:               select *, (select count([column]) from [table])
                                                  as count from [table] group by [column];
- select specific records:                        select * from [table] where [column] = [value];
- select records containing [value]:              select * from [table] where [column] like '%[value]%';
- select records starting with [value]:           select * from [table] where [column] like '[value]%';
- select records starting with val                select * from [table] where [column] LIKE '[val_ue]';
   and ending with ue:
- select a range:                                 select * from [table] where [column] between [value1] and [value2];
- select with custom order and only limit:        select * from [table] where [column] order by [column] asc limit [value];

- custom column output names:                     select [column] as [column_name_changed] from [table];
- MYSQL function for datetime input:              select now();
-log out:                                         exit;


aggregate functions

?- select but without duplicates:                select distinct name, email, acception 
                                                 from owners where acception = 1 and date >= 2015-01-01 00:00:00;
?- calculate total number of records:            select sum ([column]) from [table];
-count total number of [column]                  
 and group by [category-column]:                 select [category-column], sum([column]) from [table] group by [category-column];
 -get largest value in [column]:                 select max([column]) from [table];
 -get smallest value:                            select min([column]) from [table];
 -get average value:                             select avg([column]) from [table];
 ?-get rounded average value                     select [category-column],
 and group by [category-column]:                 round(avg([column]), 2)from [table] group by [category-column];
  
