# Banking_dbmsproject
PROBLEM STATEMENT:

To stimulate banking applications from the admin perspective.
To demonstrate banking transactions from admin perspective on fields like:
   1- Branch
   2- Employee
   3- Customer
   4-Loan

This proto-type is an overview of the banking transactions and how they can be made feasible using real world technologies.

NORMALISATION OF TABLES:

1st Normal Form(1NF):
As per the rule of first normal form, an attribute (column) of a table cannot hold multiple values.
 It should hold only atomic values.
No row/column intersections contain multivalued fields.
2nd Normal Form(2NF):
Table is in 1NF (First normal form)
No non-prime attribute is dependent on the proper subset of any candidate key of table.
An attribute that is not part of any candidate key is known as non-prime attribute.
3rd Normal Form(3NF):
Table must be in 2NF
Transitive functional dependency of non-prime attribute on any super key should be removed.
An attribute that is not part of any candidate key is known as non-prime attribute.


NORMALISED TABLES:
1-Branch Table:


BranchId
BName
IFSC
TelePh
City
PIN
1
Karvenagar
BOCK7894561235
9874561235
Pune
411052
2
Bandra
BOCB9632581825
9822057894,
Mumbai
400050





1NF
All the attributes are atomic hence it is in 1NF as we have taken a single value for telephone no.
2 NF
No non-prime attribute is dependent on the proper subset of any candidate key of table , hence it is in 2 NF.
3NF
There are no transitive functional dependencies,hence it is in 3NF.


2-Employee Table:


EmpId
BId
EName
age
PhNo
dept
salary


101
1
Riya Sharma
28
9856321478
Loan
25000


501
5
Hiya Mehrotra
35
9741258963
Accounts
46000






1NF
All the attributes are atomic hence it is in 1NF as we have taken a single value for telephone no.
2 NF
No non-prime attribute is dependent on the proper subset of any candidate key of table , hence it is in 2 NF.
3NF
There are no transitive functional dependencies,hence it is in 3NF.

3-Customer Table:


AccNo
BrId
Name
Age
Gender
PhNo
AadharNo
AccType
Balance
City
PIN
478512369785
1
John Acharya
15
M
7895632145
238523698416
Minor
7000
Pune
411052
478512369489
1
Shanti Ahuja
35
F
8895622205
256314789520
Major
45000
Pune
411052


1NF
All the attributes are atomic hence it is in 1NF as we have taken a single value for telephone no.
2 NF
No non-prime attribute is dependent on the proper subset of any candidate key of table , hence it is in 2 NF.
3NF
There are no transitive functional dependencies,hence it is in 3NF.



4-Applies Table:


accno
LNo
DOA
sanctioned
478512369785
1
2021-02-19
Y
478512369489
1
2020-05-12
Y


1NF
All the attributes are atomic hence it is in 1NF as we have taken a single value for telephone no.
2 NF
No non-prime attribute is dependent on the proper subset of any candidate key of table , hence it is in 2 NF.
3NF
There are no transitive functional dependencies,hence it is in 3NF.



5-Loan Table:


accno
LNo
DOI
Type
DurationInMonth
ROI
Amount
478512369785
1
2021-02-19
Education
25
9.37
400000
478512369489
2
2020-05-12
Home
17
8.4
500000




1NF
All the attributes are atomic hence it is in 1NF as we have taken a single value for telephone no.
2 NF
No non-prime attribute is dependent on the proper subset of any candidate key of table , hence it is in 2 NF.
3NF
There are no transitive functional dependencies,hence it is in 3NF.









DATABASE REQUIREMENTS:
FRONTEND : 
1-FLASK-Graphical User Interface(GUI)
2-HTML-Creating Webpage
3-CSS-Styling the page
BACKEND:
       1-MYSQL-Database Creation
       2-PYTHON-Functionality for dynamic database operations
CONNECTION : 
1-Mysql–connector–python






TABLE
REQUIREMENTS
1-Branch 
It contains details of  various branches of the bank which include: Id,Name,IFSC code,Telephone no.,City and PIN code.
This is for ease of access to the admin end for management purposes. 
Moreover it keeps a record of all existing branches and helps to insert new branches as well as update specific branch information.
2-Employee
It contains information regarding the employees working in the bank specific to attributes like : Name,Age,Phno,Salary,department
Moreover it provides details about the employee regarding particular department working in as well as the branch centric details.
It is also used to maintain records of currently working employees as well as to admit a new employee as well as to update information of an employee.
3-Customer
It contains information regarding various customers in different branches of the bank.
It contains customer information regarding attributes like Name,Age,Account no. , Aadhar no. , Balance, city, PIN, gender and account type.
It also contains details regarding branch of the customer account.
At the admin end it is used to view customer details as well as to add or update them. 
4- Applies
It contains details regarding the applicants of loan and has attributes like name, account no. , loan id and date of application of the loan.
It also contains a sanctioned column to inform whether the loan has been approved or not.
5-Loan
It contains details about customers whose loan has been approved.
It contains details like customer account no. , loan id, duration , amount , rate of interest ,date of issue as well as type of loan issued.





ERD DIAGRAM:



CONVERSION OF ERD TO TABLES:




1-Branch Table:
Attributes: 
BranchId—Primary Key
Branch Name— Not null
IFSC Code— Unique
Telephone no.— Unique
City—Not null
PIN Code— Unique


BranchId
BName
IFSC
TelePh
City
PIN
1
Karvenagar
BOCK7894561235
9874561235
Pune
411052
2
Bandra
BOCB9632581825
9822057894,
Mumbai
400050

                      
                  
2-Employee Table:
Attributes:
Employee Id — Primary Key
Branch Id— Foreign Key referenced from Branch Table
Employee Name
Age 
Phone number— Unique
Department
Salary


EmpId
BId
EName
age
PhNo
dept
salary


101
1
Riya Sharma
28
9856321478
Loan
25000


501
5
Hiya Mehrotra
35
9741258963
Accounts
46000




                  
3-Customer Table:
Attributes:
Account no. — Primary Key
Branch Id— Foreign Key referenced from Branch Table
Name
Age
Gender
Phone number
Aadhar number
Account Type 
City
PIN Code


AccNo
BrId
Name
Age
Gender
PhNo
AadharNo
AccType
Balance
City
PIN
478512369785
1
John Acharya
15
M
7895632145
238523698416
Minor
7000
Pune
411052
478512369489
1
Shanti Ahuja
35
F
8895622205
256314789520
Major
45000
Pune
411052


4-Applied Table:
Attributes:
Account no. — Foreign key referenced from Customer Table
Loan number—Primary key, Foreign key referenced from Loan Table
Date of Application— Not null


accno
LNo
DOA
sanctioned
478512369785
1
2021-02-19
Y
478512369489
1
2020-05-12
Y



5-Loan Table:
Attributes:
Loan Id— Primary key
Account no. — Foreign key referenced from Customer table
Type of Loan
Duration (in months)
Rate of interest
Date of Issue
Amount


accno
LNo
DOI
Type
DurationInMonth
ROI
Amount
478512369785
1
2021-02-19
Education
25
9.37
400000
478512369489
2
2020-05-12
Home
17
8.4
500000



