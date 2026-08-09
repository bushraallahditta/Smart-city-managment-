 🏙️ Smart City Management System

[![C++](https://img.shields.io/badge/C++-17-blue.svg)](https://isocpp.org/)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20Mac-green.svg)](https://github.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)](https://github.com/)
[![Code Size](https://img.shields.io/badge/Code-1000%2B%20lines-orange.svg)](https://github.com/)

A comprehensive **C++ console-based application** for managing urban administration including citizen records, police reports (FIRs), property registrations, voter management, and medical records with dynamic memory management and data validation.

---

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Key Features](#-key-features)
- [Modules](#-modules)
- [Technology Stack](#-technology-stack)
- [Data Structures](#-data-structures)
- [Validation Rules](#-validation-rules)
- [Memory Management](#-memory-management)
- [How to Run](#-how-to-run)
- [Sample Output](#-sample-output)
- [File Storage](#-file-storage)
- [Project Structure](#-project-structure)
- [Author](#-author)
- [License](#-license)

---

## 📋 Project Overview

This **Smart City Management System** is a complete urban administration solution that manages five core modules:

| Module | Description |
|--------|-------------|
| **👤 Citizen Records** | Maintain demographic data of city residents |
| **📋 FIR Records** | Track police reports with status management |
| **🏠 Property Records** | Register and manage city properties |
| **🗳️ Voting Management** | Handle voter registration with eligibility checks |
| **🏥 Medical Records** | Store and retrieve patient medical history |

**Key Highlights:**
- ✅ Dynamic memory allocation with automatic array expansion/shrinking
- ✅ Comprehensive data validation for all inputs
- ✅ Duplicate prevention across modules
- ✅ File persistence for all records
- ✅ Memory leak prevention with automatic cleanup

---

## ✨ Key Features

### Core Functionality
- ✅ **Full CRUD Operations** - Create, Read, Update, Delete for all modules
- ✅ **Dynamic Memory Management** - Arrays grow 2x when full, shrink 1/2 when underutilized
- ✅ **Data Validation** - CNIC (13 digits), phone, name, age, year validation
- ✅ **Duplicate Prevention** - Prevents duplicate CNIC, FIR IDs, and Property IDs
- ✅ **File Persistence** - Data automatically saved to text files
- ✅ **User-Friendly Interface** - Intuitive menu-driven console interface
- ✅ **Memory Cleanup** - Automatic garbage collection on program exit

---

## 📂 Modules

### 1. 👤 Citizen Records Module
- Add citizens with name, CNIC, address, phone
- Search citizens by CNIC
- Display all registered citizens
- Update citizen information
- Delete citizen records
- **Data stored:** Name | CNIC | Address | Phone

### 2. 📋 FIR Records Module (Police Reports)
- Register FIRs with unique ID
- Track crime type, location, date
- Update FIR status (Solved/Pending)
- Search FIRs by ID
- View FIR statistics (solved/pending count)
- **Data stored:** FIR ID | Year | Name | CNIC | Crime Type | Location | Date | Status

### 3. 🏠 Property Records Module
- Register properties with unique ID
- Property types: House, Plot, Shop
- Track ownership via CNIC
- Monitor registration status (pending/done)
- Search and delete properties
- **Data stored:** Property ID | Owner | CNIC | Type | Address | Status

### 4. 🗳️ Voting Management Module
- Register single or multiple voters
- Automatic eligibility check (age ≥ 18)
- Search voters by age, year, or eligibility
- Display voting statistics with percentages
- Delete voter records
- **Data stored:** Age | Eligibility | Year

### 5. 🏥 Medical Records Module
- Add patient medical records
- Track diseases and doctor names
- Search by CNIC
- Delete medical records
- **Data stored:** Patient Name | CNIC | Disease | Doctor | Date

---

## 🛠️ Technology Stack

| Technology | Purpose |
|------------|---------|
| **C++17** | Core programming language |
| **Dynamic Arrays (Pointers)** | Memory management with expand/shrink |
| **File I/O (fstream)** | Data persistence to text files |
| **C-Strings (cstring)** | String manipulation using char arrays |
| **Structured Programming** | Modular function-based design |
| **Console I/O (iostream)** | User interaction interface |

---

## 📊 Data Structures

### 1. Citizen Records
```cpp
char** citizenRecords;  // 500 bytes per record
Fields: Name(100) | CNIC(100) | Address(200) | Phone(100)

2. FIR Records
cpp
int** firNumericData;   // [FIR ID, Year, Status]
char** firTextData;     // 500 bytes per record
Numeric: FIR ID | Year | Status
Text: Name | CNIC | Crime Type | Location | Date

3. Property Records
cpp
char** propertyRecords; // 700 bytes per record
Fields: Property ID(100) | Owner(100) | CNIC(100) | Type(100) | Address(200) | Status(100)

4. Medical Records
cpp
char** medicalRecords;  // 500 bytes per record
Fields: Name(100) | CNIC(100) | Disease(100) | Doctor(100) | Date(100)

5. Voting Records
cpp
int** votingRecords;    // [Age, Eligibility, Year]
Fields: Age | Eligibility (1=Eligible, 0=Not) | Year

✅ Validation Rules
Field	Validation Rule	Example
CNIC	Exactly 13 digits	1234567890123
Name	2-50 characters, letters/spaces/periods only	John Doe
Phone	10-15 digits, + or - allowed	+92-300-1234567
Age	0-150 years	25
Year	1900-2026	2024
FIR ID	Unique integer	1001
Property ID	Unique string	P-001
Status	1=Solved, 0=Pending	1
Voter Eligibility	Automatically calculated (age ≥ 18)	Eligible
🧠 Memory Management
Dynamic Array Strategy
Parameter	Value
Initial Capacity	10 records
Growth Factor	2x when full
Shrink Threshold	When records < 50% capacity
Shrink Factor	1/2 capacity
Key Functions
expand*Capacity() - Grows arrays when full

shrink*Capacity() - Shrinks arrays when underutilized

cleanupMemory() - Frees all allocated memory on program exit

deepCopy*() - Safely copies array data

Benefits
✅ Efficient Memory Usage - Uses only what's needed

✅ No Memory Leaks - Automatic cleanup

✅ Scalable - Handles 10 to thousands of records

✅ Performance - Reduces reallocation frequency

🚀 How to Run
Prerequisites
C++ Compiler (g++ recommended)

Windows / Linux / Mac OS

Terminal/Command Prompt

Step 1: Compile the Code
bash
g++ "smart city managment.cpp" -o smartcity
Step 2: Run the Program
bash
# Windows
smartcity.exe

# Linux/Mac
./smartcity
Step 3: Navigate the Menu
text
====================================
 SMART CITY MANAGEMENT SYSTEM
====================================
1. Citizen Records
2. FIR Records
3. Property Records
4. Voting Management
5. Medical Records
6. Exit
📸 Sample Output
Main Menu
text
====================================
 SMART CITY MANAGEMENT SYSTEM
====================================
1. Citizen Records
2. FIR Records
3. Property Records
4. Voting Management
5. Medical Records
6. Exit

Enter Choice: 1
Citizen Record Display
text
===== CITIZEN RECORDS =====
Current Capacity: 10 | Records: 3

Citizen #1
Name    : John Doe
CNIC    : 1234567890123
Address : 123 Main Street, City
Phone   : +92-300-1234567
-------------------------
Voting Eligibility Result
text
===== VOTER REGISTRATION =====
Enter Voter Name: Alice
Enter Age (0-150): 22
Enter Year (1900-2026): 2024

========== RESULT ==========
Voter Name : Alice
Age        : 22

STATUS: ELIGIBLE For Voting

Voter #1 Registered Successfully!
FIR Statistics
text
===== FIR STATISTICS =====
Total FIRs   : 15
Solved FIRs  : 10
Pending FIRs : 5
Property Record Display
text
===== PROPERTY RECORDS =====
Current Capacity: 10 | Records: 2

============================
Property ID     : P-001
Owner Name      : John Doe
Owner CNIC      : 1234567890123
Type            : House
Address         : 123 Main Street
Status          : done
============================
💾 File Storage
All data is automatically saved to text files in the program's directory:

File Name	Stores	Format
citizens.txt	Citizen records	Name|CNIC|Address|Phone
firs.txt	FIR reports	(Auto-created on save)
properties.txt	Property registrations	(Auto-created on save)
medical.txt	Medical records	(Auto-created on save)
voters.txt	Voting data	(Auto-created on save)
Format: Pipe-separated (|) for easy parsing

📁 Project Structure
text
Smart-city-management-/
│
├── smart city managment.cpp    # Main source code (1000+ lines)
├── README.md                   # Project documentation
├── .gitignore                  # Excluded files
├── LICENSE                     # MIT License
│
# Runtime files (auto-created):
├── citizens.txt                # Citizen data
├── firs.txt                    # FIR data
├── properties.txt              # Property data
├── medical.txt                 # Medical records
└── voters.txt                  # Voter data
🔮 Future Enhancements
□ GUI Interface - Windows Forms or Qt framework
□ Database Integration - MySQL/PostgreSQL
□ Web API - RESTful services for external access
□ Mobile App - Android/iOS applications
□ Cloud Storage - Google Cloud/AWS integration
□ Real-time Analytics - Data visualization dashboards
□ Multi-user Authentication - Admin/User roles
□ Reporting System - PDF/Excel report generation
□ Search Optimization - Faster search algorithms
□ Backup & Recovery - Automated backup system
🤝 Contributing
Contributions are welcome! Please follow these steps:

Fork the repository

Create a new branch (git checkout -b feature/AmazingFeature)

Commit changes (git commit -m 'Add AmazingFeature')

Push to branch (git push origin feature/AmazingFeature)

Open a Pull Request

❓ FAQ
Q: What compiler do I need?
A: Any C++ compiler (g++, clang, MSVC). g++ is recommended.

Q: Can I run this on Mac/Linux?
A: Yes! The code is cross-platform.

Q: How do I reset the database?
A: Delete the .txt files created by the program.

Q: What happens if I enter invalid data?
A: The program validates all inputs and prompts again.

Q: Is my data safe?
A: Data is saved to text files on your computer.

👩‍💻 Author
Bushra Allah Ditta

GitHub: @bushraallahditta

Project Link: Smart City Management

Email: bushra.allahditta@example.com

📝 License
This project is licensed under the MIT License - see the LICENSE file for details.

text
MIT License

Copyright (c) 2024 Bushra Allah Ditta

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions...
⭐ Show Your Support
If you found this project helpful, please give it a ⭐ on GitHub!

https://img.shields.io/github/stars/bushraallahditta/Smart-city-management-.svg?style=social
https://img.shields.io/github/followers/bushraallahditta.svg?style=social&label=Follow

📊 Project Statistics
Metric	Value
Lines of Code	1000+
Modules	5
Functions	40+
Data Validation Rules	6+
File Persistence	Yes
Memory Management	Dynamic
Platform Support	Windows, Linux, Mac
