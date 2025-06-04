# Employee-M.S.
# Dictionary to store employee data
employees = {
    101: {
        "name": "Alice",
        "age": 28,
        "department": "HR",
        "salary": 45000
    },
    102: {
        "name": "Bob",
        "age": 32,
        "department": "IT",
        "salary": 60000
    },
    103: {
        "name": "Charlie",
        "age": 25,
        "department": "Finance",
        "salary": 50000
    }
}

# Function to add employee
def add_employee():
    emp_id = int(input('Enter the employee id: '))
    if emp_id in employees:
        print("This Employee ID already exists")
        return
    name = str(input('Enter the Employee Name: '))
    age = int(input("Enter the age of the employee: "))
    department = str(input("Enter department: "))
    salary = float(input('Enter the salary: '))
    employees[emp_id] = {
        'name': name,
        'age': age,
        'department': department,
        'salary': salary
    }
    print("Employee has been added successfully.")

# Function to view all employees
def view_employees():
    if not employees:
        print("No employees found.")
        return
    for emp_id, info in employees.items():
        print(f"ID: {emp_id}, Name: {info['name']}, Age: {info['age']}, "
              f"Department: {info['department']}, Salary: Rs{info['salary']}")
    print()

# Function to search an employee
def search_employee():
    emp_id = int(input("Enter the Employee ID to search: "))
    if emp_id in employees:
        info = employees[emp_id]
        print(f"ID: {emp_id}, Name: {info['name']}, Age: {info['age']}, "
              f"Department: {info['department']}, Salary: Rs{info['salary']}")
    else:
        print("Employee not found.")

# Menu loop
while True:
    print("==== Employee Management System ====")
    print("1. Add Employee")
    print("2. View All Employees")
    print("3. Search for Employee")
    print("4. Exit")

    choice = input("Enter your choice (1-4): ").strip()

    match choice:
        case '1':
            add_employee()
        case '2':
            view_employees()
        case '3':
            search_employee()
        case '4':
            print("Exiting program")
            break
        case _:
            print("Invalid choice. Please enter a number between 1 and 4")
