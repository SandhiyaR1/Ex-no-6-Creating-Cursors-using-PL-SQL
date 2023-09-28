# Ex. No: 5 Creating Cursors using PL/SQL

### AIM:
To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:

### Create employee table
```
create table employeee((empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
insert into employeee values(1,'John','HR',50000);
insert into employeee values(2,'joe','IT',65000);
insert into employeee values(3,'Bob','Finance',55000);
```

### PLSQL Cursor code
```
 set serveroutput on
SQL> declare
  2  cursor employeee_cursor is
  3  select empid,empname,dept,salary
  4  from employeee;
  5  empid number;
  6  empname varchar(90);
  7  dept varchar(90);
  8  salary number;
  9  begin
 10  open employeee_cursor;
 11  loop
 12  fetch employeee_cursor into empid,empname,dept,salary;
 13  exit when employeee_cursor%notfound;
 14  dbms_output.put_line('Employee ID: '||empid);
 15  dbms_output.put_line('Employee Name: '||empname);
 16  dbms_output.put_line('Department: '||dept);
 17  dbms_output.put_line('Salary: '||salary);
 18  dbms_output.put_line('------------------------');
 19  end loop;
 20  close employeee_cursor;
 21  end;
 22  /
```

### Output:
![image](https://github.com/SandhiyaR1/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/113497571/090e25ef-d9fd-48a1-9467-5fc8cdba3287)

### Result:
Thus a cursor using PL/SQL is created successfully.
