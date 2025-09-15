# Employee-Database-Application

**Project Overview**

This project implements an Employee Database Application in Python, built as the final project for MIS 6382. The program applies object-oriented programming concepts (inheritance, polymorphism, multiple inheritance, encapsulation, exception handling) to manage different employee types and their data.
The database is interactive and allows users to add, search, analyze, and manage employee records. Employee data is stored in a binary file (empdata.dat) and updated into a new file (empdata_updated.dat) upon exit.

Features (Menu Options)

The application provides a menu with 7 options:

1. Add a new employee – Choose employee type and input details.
2. Display employee information – Show all or the first 5 employees.
3. Compute and print compensation – Weekly compensation for all employees.
4. Search employees by name – Case-insensitive search.
5. Basic statistics: Total employees, Highest weekly compensation, Mean weekly compensation, Number of employees with vehicles over 100,000 miles
6. Calculate reimbursement – Based on employee type and expenses.
7. Exit application – Saves all updates to empdata_updated.dat.

**Class Structure**
1. Vehicle
Attributes: make, model, year, mileage
Methods: getters, setters, __str__

2. Employee (Base Class)
Attributes: name, address, vehicle (Vehicle object)
Methods: getters, setters, __str__, abstract compute_compensation()

3. FullTimeEmployee (inherits Employee)
Extra Attribute: salary
Compensation: Annual salary – taxes (progressive rates), divided by 52 weeks
Reimbursement: Based on annual expense (100% up to $10k, 50% excess)

4. HourlyEmployee (inherits Employee)
Extra Attributes: hoursWorked, hourlyRate
Compensation: Regular pay + overtime (>40 hrs at 1.8× rate)
Reimbursement: Weekly expense (max $100)

5. Consultant (inherits Employee)
Extra Attributes: hoursWorked, projectType (1, 2, 3)
Compensation: Project-based hourly rate (55, 70, 85)
Reimbursement: Weekly expense × rate (100%, 90%, 80%)

6. Management (inherits FullTimeEmployee & Consultant)
Attributes: Combination of FullTime and Consultant
Compensation: Salary-based pay + consulting pay
Reimbursement: FullTime reimbursement + Consultant reimbursement

**Technical Details**
Language: Python (Jupyter Notebook)
Libraries: pickle (file handling), sys
Data Persistence:Reads initial employees from empdata.dat, Writes updated employees to empdata_updated.dat


**Example Workflow**

Add new employees (FullTime, Hourly, Consultant, Management).
Display first 5 employees.
Print all weekly compensations.
Search by name (GRACE, Zoey, etc.).
View statistics (employee count, max comp, mean comp, high-mileage cars).
Calculate reimbursements with user-provided expenses.
Exit → saves changes to empdata_updated.dat.

**Learning Outcomes**

Mastered class design and inheritance (single & multiple).
Applied encapsulation with private attributes and getter/setter methods.
Implemented polymorphism via compute_compensation() and compute_reimbursement().
Worked with file I/O (pickle) for persistent storage.
Practiced exception handling in user input validation.
