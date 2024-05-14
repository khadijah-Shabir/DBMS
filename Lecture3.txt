SQLite version 3.45.1 2024-01-30 16:01:20 (UTF-16 console I/O)
Enter ".help" for usage hints.
Connected to a transient in-memory database.
Use ".open FILENAME" to reopen on a persistent database.
sqlite> CREATE TABLE employee(empId char(4),empname varchar(30),empfName varchar(30), empage int, empsal int, empdept char(4));
sqlite> INSERT INTO employee VALUES('E001','Ali ahmad','Ahmad Hassan',27,70000,'D003');
sqlite>  INSERT INTO employee VALUES('E002','Sana javed','Javed Ahmad',21,60000,'D001');
sqlite>  INSERT INTO employee VALUES('E003','Kamran Ali','Ali Ahmed',24,75000,'D002');
sqlite> INSERT INTO employee VALUES('E004','Kashif Ali','Ali Kamran',25,80000,'D001');
sqlite>  INSERT INTO employee VALUES('E005','Hina Munir','Munir Ahmed',22,65000,'D004');
sqlite> INSERT INTO employee VALUES('E006','Hamna Ali','Hassan Ali',27,75000,'D002');
sqlite> INSERT INTO employee VALUES('E007','Obaid Ali','Ali Ahmed',32,90000,'D001');
sqlite> INSERT INTO employee VALUES('E008','Muhammad Kamran','Kamran Ali',35,95000,'D004');
sqlite> INSERT INTO employee VALUES('E009','Muhammad Ali','Ali Hassan',21,55000,'D001');
sqlite> .header on
sqlite> .mode column
sqlite> SELECT*FROM employee;
empId  empname          empfName      empage  empsal  empdept
-----  ---------------  ------------  ------  ------  -------
E001   Ali ahmad        Ahmad Hassan  27      70000   D003
E002   Sana javed       Javed Ahmad   21      60000   D001
E003   Kamran Ali       Ali Ahmed     24      75000   D002
E004   Kashif Ali       Ali Kamran    25      80000   D001
E005   Hina Munir       Munir Ahmed   22      65000   D004
E006   Hamna Ali        Hassan Ali    27      75000   D002
E007   Obaid Ali        Ali Ahmed     32      90000   D001
E008   Muhammad Kamran  Kamran Ali    35      95000   D004
E009   Muhammad Ali     Ali Hassan    21      55000   D001
sqlite> SELECT empname,empage,empdept FROM employee;
empname          empage  empdept
---------------  ------  -------
Ali ahmad        27      D003
Sana javed       21      D001
Kamran Ali       24      D002
Kashif Ali       25      D001
Hina Munir       22      D004
Hamna Ali        27      D002
Obaid Ali        32      D001
Muhammad Kamran  35      D004
Muhammad Ali     21      D001
sqlite> SELECT empId,empname,empage FROM employee WHERE empage<30;
empId  empname       empage
-----  ------------  ------
E001   Ali ahmad     27
E002   Sana javed    21
E003   Kamran Ali    24
E004   Kashif Ali    25
E005   Hina Munir    22
E006   Hamna Ali     27
E009   Muhammad Ali  21
sqlite> SELECT empname FROM employee WHERE empsal>70000;
empname
---------------
Kamran Ali
Kashif Ali
Hamna Ali
Obaid Ali
Muhammad Kamran
sqlite> SELECT empname empage FROM employee WHERE empage>25 AND empsal<90000;
empage
---------
Ali ahmad
Hamna Ali
sqlite> SELECT empname,empage FROM employee WHERE empage>25 AND empsal<90000;
empname    empage
---------  ------
Ali ahmad  27
Hamna Ali  27
