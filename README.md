# -63_Student_Performance_Analyzer_Ru-26-02051_1O_Sumit_Kumar
Vehicle Service Management System 🚗

Project Overview

The Vehicle Service Management System is a Python-based console application used to manage vehicle service records. It allows users to add, view, update, and delete service records using Object-Oriented Programming (OOP).

The system calculates service costs with 18% GST and manages service status.

Features

- Add new vehicle service records
- View all service records
- Update service status
- Delete service records
- Automatic service cost calculation with 18% GST
- Registration number-based record management
- Input validation and exception handling

Technologies Used

- Python 3
- Object-Oriented Programming (OOP)
- Dictionaries
- Lists
- File Handling
- CRUD Operations

Available Services

Service| Price (₹)
Oil Change| 1,500
Wheel Alignment| 800
Full Service| 4,500
Brake Repair| 2,200

GST Calculation

The system adds 18% GST to the selected service cost.

Formula:

Total Cost = Service Price × 1.18

Example:

Oil Change = ₹1,500

GST = ₹270

Total Cost = ₹1,770

Service Status

- Pending
- In Progress
- Completed

CRUD Operations

- Create: Add a new service record.
- Read: View existing service records.
- Update: Update service status.
- Delete: Remove a service record.

How to Run

1. Clone or download this repository.
2. Open the project folder.
3. Run the Python file using:

python main.py

Test Cases

1. Normal Input: Add a service record with valid details and calculate cost including GST.
2. Boundary Input: Update the service status from Pending to Completed.
3. Invalid Input: Enter an invalid service type and handle the error.
4. Valid Delete Scenario: Delete an existing record and verify successful deletion.

