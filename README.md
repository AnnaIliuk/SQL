# SQL
-----------------
##Первая часть

SQL_DDLПервая часть.

**Таблица employees**

	1.	Создать таблицу employees: id. serial,  primary key,- employee_name. Varchar(50), not null  
	2.	Наполнить таблицу employee 70 строками  

```
1. create table employees (  
		id serial primary key,  
		employee_name varchar(50) not null  
	);  
	
2. insert into employees (id, employee_name) values 
	(1, 'Anna'),
	(2, 'Katya'),
	(3, 'Sonya'),
	(4, 'Oleg'), 
	(5, 'Roma'), 
	(6, 'Sveta'), 
	(7, 'Vadim'),
	(8, 'Sonya'), 
	(9, 'Pasha'),
	(10, 'Tanya'),
	(11, 'Dima'), 
	(12, 'Vera'),
	(13, 'Tolya'), 
	(14, 'Anna'),
	(15, 'Nika'),
        (16, 'Anna'),
	(17, 'Katya'),
	(18, 'Sonya'),
	(19, 'Oleg'), 
	(20, 'Roma'), 
	(21, 'Sveta'), 
	(22, 'Vadim'),
	(23, 'Sonya'), 
	(24, 'Pasha'),
	(25, 'Tanya'),
	(26, 'Dima'), 
	(27, 'Vera'),
	(28, 'Tolya'), 
	(29, 'Anna'),
	(30, 'Nika'),
        (31, 'Anna'),
	(32, 'Katya'),
	(33, 'Sonya'),
	(34, 'Oleg'), 
	(35, 'Roma'), 
	(36, 'Sveta'), 
	(37, 'Vadim'),
	(38, 'Sonya'), 
	(39, 'Pasha'),
	(40, 'Tanya'),
	(41, 'Dima'), 
	(42, 'Vera'),
	(43, 'Tolya'), 
	(44, 'Anna'),
	(45, 'Nika'),
        (46, 'Anna'),
 	(47, 'Katya'),
	(48, 'Sonya'),
	(49, 'Oleg'), 
	(50, 'Roma'), 
	(51, 'Sveta'), 
	(52, 'Vadim'),
	(53, 'Sonya'), 
	(54, 'Pasha'),
	(55, 'Tanya'),
        (56, 'Dima'), 
	(57, 'Vera'),
	(58, 'Tolya'), 
	(59, 'Anna'),
	(60, 'Nika'),
	(61, 'Sveta'), 
	(62, 'Vadim'),
	(63, 'Sonya'), 
	(64, 'Pasha'),
	(65, 'Tanya'),
	(66, 'Dima'), 
	(67, 'Vera'),
	(68, 'Tolya'), 
	(69, 'Anna'),
	(70, 'Nika');
```

**Таблица salary**

	1.	Создать таблицу salary: id. Serial  primary key,- monthly_salary. Int, not null
	2.	Наполнить таблицу salary 16 строками: - 1000- 1100- 1200- 1300- 1400- 1500- 1600- 1700- 1800- 1900- 2000- 2100- 2200- 2300- 2400- 2500

```
create table salary(
         id serial primary key,
          int not null       
);

insert into salary (id, monthly_salary) values
   (1,1000),
   (2,1100),
   (3,1200),
   (4,1300),
   (5,1400),
   (6,1500),
   (7,1600),
   (8,1700),
   (9,1800),
   (10,1900),
   (11,2000),
   (12,2100),
   (13,2200),
   (14,2300),
   (15,2400),
   (16,2500);

```

**Таблица employee_salary**

	1.	Создать таблицу employee_salary: id. Serial  primary key,- employee_id. Int, not null, unique
- salary_id. Int, not null
	2.	Наполнить таблицу employee_salary 40 строками:- в 10 строк из 40 вставить несуществующие employee_id


| id |  employee_id  |  salary_id  |
|----|---------------|-------------|
1|	3|	7|
2|	1|	4|
3|	5|	9|
4|	40|	13|
5|	23|	4|
6|	11|	2|
7|	52|	10|
8|	15|	13|
9|	26|	4|
10|	16|	1|
11|	33|	7|
...	...	...

```
1. create table employee_salary(
         id serial primary key,
         employee_id int not null unique,
         salary_id int not null,
         foreign key(employee_id)
            references employees(id),
         foreign key (salary_id)
            references salary(id)
);

2. insert into employee_salary(id,employee_id,salary_id) values 
             (1,3,7),
             (2,1,4),
             (3,5,9),
             (4,40,13),
             (5,23,4),
             (6,11,2),
             (7,52,10),
             (8,15,13),
             (9,26,4),
             (10,16,1),
             (11,33,7),
             (12,2,16),
             (13,4,14),
             (14,6,3),
             (15,7,11),
             (16,8,9),
             (17,9,4),
             (18,10,13),
             (19,12,11),
             (20,13,5),
             (21,14,1),
             (22,17,3),
             (23,18,10),
             (24,19,7),
             (25,20,14),
             (26,21,8),
             (27,22,16),
             (28,24,7),
             (29,25,9),
             (30,27,2);
             
            
 insert into employee_salary(id,employee_id,salary_id) values             
	         (31,41,17),
	         (32,63,22),
	         (33,66,66),
	         (34,77,77),
	         (35,88,88),
	         (36,99,99),
	         (37,65,65),
	         (38,56,67);
```

**Таблица roles**

	1.	Создать таблицу roles- id. Serial  primary key,- role_name. int, not null, unique
	2.	Поменять тип столба role_name с int на varchar(30)
	3.	Наполнить таблицу roles 20 строками:

| id |       role_name                 |
|----|---------------------------------|
1|	Junior Python developer|
2|	Middle Python developer|
3|	Senior Python developer|
4|	Junior Java developer|
5|	Middle Java developer|
6|	Senior Java developer|
7|	Junior JavaScript developer|
8|	Middle JavaScript developer|
9|	Senior JavaScript developer|
10|	Junior Manual QA engineer|
11|	Middle Manual QA engineer|
12|	Senior Manual QA engineer|
13|	Project Manager|
14|	Designer|
15|	HR|
16|	CEO|
17|	Sales manager|
18|	Junior Automation QA engineer|
19|	Middle Automation QA engineer|
20|	Senior Automation QA engineer|

```
1. create table roles(
        id serial primary key,
        role_name int not null unique
);
      

2. alter table roles 
alter column role_name type varchar(30);
	        
3. insert into roles (id,role_name) values 
            (1,'Junior Python developer'),
            (2,'Middle Python developer'),
            (3,'Senior Python developer'),
            (4,'Junior Java developer'),
            (5,'Middle Java developer'),
            (6,'Senior Java developer'),
            (7,'Junior JavaScript developer'),
            (8,'Middle JavaScript developer'),
            (9,'Senior JavaScript developer'),
            (10,'Junior Manual QA engineer'),
            (11,'Middle Manual QA engineer'),
            (12,'Senior Manual QA engineer'),
            (13,'Project Manager'),
            (14,'Designer'),
            (15,'HR'),
            (16,'CEO'),
            (17,'Sales manager'),
            (18,'Junior Automation QA engineer'),
            (19,'Middle Automation QA engineer'),
            (20,'Senior Automation QA engineer');


insert into roles_employee (id, employee_id, role_id) values
           (1,7,2),
           (2,20,4),
           (3,3,9),
           (4,5,13),
           (5,23,4),
           (6,11,2),
           (7,10,9),
           (8,22,13),
           (9,21,3),
           (10,34,4),
           (11,6,7),
           (12,70,20),
           (13,51,12),
           (14,52,11),
           (15,53,9),
           (16,54,8),
           (17,55,7),
           (18,56,13),
           (19,57,6),
           (20,58,5),
           (21,59,4),
           (22,60,1),
           (23,61,17),
           (24,62,18),
           (25,63,16),
           (26,64,19),
           (27,65,13),
           (28,66,9),
           (29,67,1),
           (30,40,3),
           (31,41,4),
           (32,42,6),
           (33,43,14),
           (34,44,15),
           (35,45,16),
           (36,46,17),
           (37,47,20),
           (38,48,19),
           (39,49,2),
           (40,33,20);
```        
















