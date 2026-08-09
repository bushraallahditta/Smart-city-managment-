
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

### 1. Citizen Records
