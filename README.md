A comprehensive **C++ console-based application** for managing various city services including citizen records, FIRs, property records, voting management, and medical records.

---

## 📋 Table of Contents
- [Features](#-features)
- [Modules](#-modules)
- [Technologies Used](#-technologies-used)
- [How to Run](#-how-to-run)
- [File Structure](#-file-structure)
- [Data Validation](#-data-validation)
- [Memory Management](#-memory-management)
- [Screenshots](#-screenshots)
- [Author](#-author)
- [License](#-license)

---

## 🚀 Features

### Core Capabilities
- ✅ **Dynamic Memory Allocation** - Arrays grow/shrink automatically
- ✅ **Data Validation** - CNIC, phone, name, age, year validation
- ✅ **CRUD Operations** - Create, Read, Update, Delete for all modules
- ✅ **Duplicate Detection** - Prevents duplicate CNIC, FIR IDs, Property IDs
- ✅ **File Persistence** - Data saved to text files
- ✅ **Memory Management** - Automatic cleanup on exit
- ✅ **User-Friendly Interface** - Menu-driven console application

---

## 📂 Modules

### 1. 👤 Citizen Records
- Add new citizens with CNIC, name, address, phone
- Search citizens by CNIC
- Display all citizens
- Update citizen information
- Delete citizen records
- **Validation**: CNIC (13 digits), Name (2-50 chars, letters only), Phone (10-15 digits)

### 2. 📋 FIR Records (Police Reports)
- Register new FIRs with unique ID
- Search FIRs by ID
- Update FIR status (Solved/Pending)
- Display all FIRs with statistics
- Delete FIR records
- **Features**: Solved/Pending status tracking, crime statistics

### 3. 🏠 Property Records
- Register properties with unique ID
- Property types: House, Plot, Shop
- Track ownership with CNIC
- Search properties by ID
- Delete property records
- **Status**: Pending registration or Done

### 4. 🗳️ Voting Management
- Register single or multiple voters
- Automatic eligibility check (age ≥ 18)
- Search voters by age, year, or eligibility
- Display voting statistics
- Delete voter records
- **Feature**: Bulk voter registration with summary

### 5. 🏥 Medical Records
- Add patient medical records
- Track diseases and doctor names
- Search by CNIC
- Delete records
- **Data**: Patient name, CNIC, disease, doctor, report date

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| **C++** | Core programming language |
| **Dynamic Arrays** | Memory management |
| **File I/O** | Data persistence |
| **C-Strings** | String manipulation |
| **Structured Programming** | Modular code organization |

---

## 💻 How to Run

### Prerequisites
- C++ Compiler (g++ recommended)
- Windows / Linux / Mac OS

### Step 1: Compile the Code
```bash
g++ "smart city managment.cpp" -o smartcity
