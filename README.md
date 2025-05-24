use TA7EEL
go
create table clerk
(
Employee_Name varchar(20) primary key,
phone varchar(11) not null,
name_id int not null,
qualification varchar(25) not null,
type_1 decimal(4),
Occupation varchar (5),
constraint type_1_chk check (type_1 between 1000 and 2000)
);


create table client
(
name_id int primary key,
Name varchar(20) not null,
phone varchar(11) not null,
DATE_1 DATE not null,
degree varchar(25) not null,
type_1 varchar(25) not null,
Employee_Name varchar(20),
constraint Employee_Name_FOGN FOREIGN KEY (Employee_Name)
REFERENCES clerk (Employee_Name)
);


alter table ARMY
add id_army int;

alter table ARMY
alter column  id_army int;


alter table ARMY
drop column id_army;



alter table ARMY
add constraint name_id_fk foreign key (name_id)
references client (name_id) ;


CREATE TABLE ARMY2
(id_army int NOT NULL,
NAME VARCHAR(25),
AGE int ,
adress_name varchar,
name_id int);


alter table ARMY2
add constraint id_army_pk primary key (id_army);

alter table ARMY2
add constraint name_id_fk foreign key (name_id)
references client (name_id) ;

alter table ARMY2
drop constraint name_id_fk   ;

alter table ARMY2
drop constraint id_army_pk   ;

exec sp_rename 'ARMY2', 'ARMY';

exec sp_rename 'ARMY.adress_name', 'adress','column'	
