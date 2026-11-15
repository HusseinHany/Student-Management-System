# 🎓 Student Grade Management System

<div align="center">

![Language](https://img.shields.io/badge/Language-C%2B%2B11-blue?style=for-the-badge&logo=cplusplus)
![Platform](https://img.shields.io/badge/Platform-Cross--Platform-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-Educational-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)

**A comprehensive, high-performance Student Management System with advanced algorithms, data structures, and interactive analytics.**

[Features](#features) • [Installation](#installation) • [Usage](#usage) • [Algorithms](#algorithms) • [Documentation](#documentation)

</div>

<p align="center">
  <img src="docs/demo.svg" width="760" alt="Recording of the program in a terminal: the main menu, loading 1,000 sample students, sorting them with quick sort, the GPA statistics screen, and the benchmark results.">
</p>

<p align="center"><sub>Real output from the program, shortened: load 1,000 sample students, sort them with quick sort, view the GPA statistics, then run the benchmark.</sub></p>

---

## 📋 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [Installation & Setup](#installation--setup)
- [Quick Start Guide](#quick-start-guide)
- [Main Menu & Operations](#main-menu--operations)
- [Algorithms Explained](#algorithms-explained)
- [Data Structures](#data-structures)
- [Advanced Features](#advanced-features)
- [Performance Benchmarking](#performance-benchmarking)
- [API Reference](#api-reference)
- [Screenshots & Examples](#screenshots--examples)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [Credits](#credits)

---

## 🎯 Overview

The **Student Grade Management System** is a full-featured desktop application designed to efficiently manage and analyze student academic records. Built entirely in C++, it demonstrates practical implementations of:

- **Classic Sorting Algorithms** (Bubble, Insertion, Selection, Merge, Quick Sort)
- **Search Algorithms** (Linear, Binary, Smart Multi-field)
- **Advanced Data Structures** (AVL Trees)
- **Algorithm Analysis** (Time complexity, comparisons, swaps)
- **Performance Benchmarking** (Real-time metrics across different data sizes)

Perfect for educational purposes, algorithm study, and practical record management.

---

## ⭐ Key Features

### 📚 CRUD Operations
```
✓ Add student records with validation
✓ Update student information (GPA, major, name)
✓ Delete records with confirmation
✓ Display all records with pagination
```

### 🔄 Sorting Algorithms
```
┌─────────────────────────────────────────────────────┐
│ Algorithm          │ Best      │ Avg       │ Worst  │
├─────────────────────────────────────────────────────┤
│ Bubble Sort (GPA)  │ O(n)      │ O(n²)     │ O(n²)  │
│ Insertion Sort     │ O(n)      │ O(n²)     │ O(n²)  │
│ Selection Sort     │ O(n²)     │ O(n²)     │ O(n²)  │
│ Merge Sort (Name)  │ O(n log n)│ O(n log n)│O(n logn)│
│ Quick Sort (GPA)   │ O(n logn) │ O(n logn) │ O(n²)* │
└─────────────────────────────────────────────────────┘
* Worst case avoided by median-of-three pivot strategy
```

### 🔍 Search Capabilities
```
✓ Linear Search     - Exact name match (O(n))
✓ Binary Search     - By ID (O(log n)) - requires pre-sorting
✓ Smart Search      - Partial match across name, ID, major
✓ Performance Stats - Comparisons & timing for each search
```

### 📊 Analytics & Statistics
```
✓ GPA Statistics    - Mean, median, std deviation, min, max
✓ GPA Distribution  - Visual bar charts by grade ranges
✓ Major Breakdown   - Students distribution by major
✓ Top-K Ranking     - Identify top performers
✓ Duplicate Detection - Find students with identical GPAs
```

### 🌳 Advanced Data Structures
```
✓ AVL Tree          - Self-balancing BST with O(log n) operations
✓ Tree Insertion    - Build balanced tree from all students
✓ Tree Search       - Efficient ID lookup
✓ Inorder Traversal - Display all students sorted by ID
```

### 📈 Benchmarking Engine
```
✓ 5 Algorithms × 4 Sizes × 3 Distributions = 60 runs
✓ Sizes: 50 | 1,000 | 10,000 | 100,000
✓ Types: Random | Nearly Sorted | Reverse Sorted
✓ Metrics: Time (ms), Comparisons, Swaps
✓ Visual Comparison Charts
```

### 💾 Data Management
```
✓ Auto-save to students.dat
✓ Load from file on startup
✓ Export to CSV format
✓ Persistent storage
✓ Handles up to 100,000 records
```

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                   MAIN APPLICATION                      │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  ┌────────────────────────────────────────────────┐     │
│  │         INTERACTIVE CONSOLE INTERFACE          │     │
│  │  • Main Menu  • Dashboard  • Pagination        │     │
│  └────────────────────────────────────────────────┘     │
│                         │                               │
│                ┌────────┼────────┐                      │
│                ▼        ▼        ▼                      │
│         ┌──────────┬──────────┬─────────┐               │
│         │  CRUD   │ALGORITHMS│ANALYTICS│                │
│         │Operations│          │         │               │
│         └──────────┴──────────┴─────────┘               │
│                         │                               │
│          ┌──────────────┼──────────────┐                │
│          ▼              ▼              ▼                │
│    ┌─────────────┬────────────┬──────────────┐          │
│    │   Sorting   │  Searching │  Statistics  │          │
│    │  Algorithms │ Algorithms │  & Analysis  │          │
│    └─────────────┴────────────┴──────────────┘          │
│                                                         │
│  ┌────────────────────────────────────────────────┐     │
│  │    DATA STRUCTURES & STORAGE LAYER             │     │
│  │  • Student Array  • AVL Tree  • File I/O       │      │
│  │  • students.dat (Persistent Storage)           │      │
│  └────────────────────────────────────────────────┘     │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Data Flow Diagram

```
        ┌─────────────┐
        │ Add Student │
        └──────┬──────┘
               │
        ┌──────▼──────────┐
        │  Validate Input  │
        │ (ID, Name, GPA) │
        └──────┬──────────┘
               │
        ┌──────▼──────┐
        │  Add to Array│
        └──────┬───────┘
               │
        ┌──────▼──────────────┐        ┌──────────┐
        │  Save to File (.dat) │◄───────│ CSV Export
        └──────┬──────────────┘        └──────────┘
               │
        ┌──────▼──────────────┐
        │ Update UI/Display   │
        └─────────────────────┘
```

---

## 💻 Installation & Setup

### System Requirements

| Component | Requirement |
|-----------|------------|
| **OS** | Windows, macOS, Linux |
| **Compiler** | GCC, Clang, MSVC (C++11 or newer) |
| **Libraries** | Standard C++ only (no external dependencies) |
| **Memory** | ~50MB for maximum capacity (100k students) |
| **Disk Space** | ~5MB for data file + executable |

### Building from Source

#### 1. **Clone the Repository**
```bash
git clone https://github.com/HusseinHany/Student-Management-System.git
cd Student-Management-System
```

#### 2. **Compile with G++ (Linux/macOS)**
```bash
g++ -std=c++11 -O2 -o student_system "Student Mangment System.cpp"
```

#### 3. **Compile with MSVC (Windows)**
```bash
cl /std:c++11 /O2 "Student Mangment System.cpp"
```

#### 4. **Run the Application**
```bash
./student_system              # Linux/macOS
student_system.exe            # Windows
```

### Project Structure

```
Student-Management-System/
├── Student Mangment System.cpp    # Main source file (~1400 lines)
├── students.dat                   # Data file (auto-created)
├── students_export.csv            # CSV export (auto-created)
├── README.md                      # This file
└── .gitignore                     # Git ignore file
```

---

## 🚀 Quick Start Guide

### First Launch

```
1. Run the application
   $ ./student_system

2. Select "14 - Load Sample Data" to populate with test records
   - Choose size (50, 1000, 10000, or 100000)
   - Choose mode: Append or Replace

3. Explore the Dashboard (Option 1)
   - View statistics and top students
   - Navigate with keyboard shortcuts

4. Try sorting (Option 6)
   - Select a sorting algorithm
   - View performance metrics

5. Experiment with search (Option 7)
   - Search by name, ID, or smart search
```

### Basic Workflow

```
┌─────────────────┐
│   Start App     │
└────────┬────────┘
         │
         ├─► Load existing data? ──► [YES] Load from students.dat
         │                          [NO]  Start with empty
         │
         ▼
    ┌─────────┐
    │ Dashboard│ ◄─────────┐
    └────┬────┘           │
         │                │
    ┌────┴────────────────────────────┐
    │                                 │
    ▼ Add    ▼ Search    ▼ Sort    ▼ View
    
    • Add/Update      • By name      • Bubble      • All
    • Delete          • By ID        • Insertion   • Paginated
                      • Smart        • Merge
                                     • Quick
    
    │                                 │
    └──► Save & Persist ──────────────┘
```

---

## 📋 Main Menu & Operations

### Main Dashboard (Option 1)

The interactive dashboard provides a comprehensive at-a-glance view:

```
══════════════════════════════════════════════════════
  DASHBOARD -- STUDENT GRADE MANAGEMENT SYSTEM
══════════════════════════════════════════════════════

  OVERVIEW
  ┌──────────────────────────────────────────────────┐
  │ Total students       : 1,000                      │
  │ Mean GPA             : 2.84 (C )                  │
  │ Highest GPA          : 4.00 (A+) -- Ali 1001     │
  │ Lowest GPA           : 0.25 (F ) -- Sara 1005    │
  │ Data file            : students.dat              │
  └──────────────────────────────────────────────────┘

  TOP 5 STUDENTS
  ┌──────┬──────┬────┬────────────────┬────────────────┐
  │ Rank │ GPA  │ Gr │ Name           │ Major          │
  ├──────┼──────┼────┼────────────────┼────────────────┤
  │ #1   │ 4.00 │ A+ │ Ali 1001       │ Computer Sci.  │
  │ #2   │ 3.99 │ A+ │ Sara 1002      │ Math           │
  │ #3   │ 3.98 │ A+ │ Omar 1003      │ Physics        │
  │ #4   │ 3.97 │ A+ │ Lina 1004      │ Chemistry      │
  │ #5   │ 3.96 │ A+ │ Hassan 1005    │ IT             │
  └──────┴──────┴────┴────────────────┴────────────────┘

  GPA DISTRIBUTION
  F  <1.0   [#########........................] 95  (9%)
  D  1-1.99 [###################...............] 198 (19%)
  C  2-2.99 [################################..] 301 (30%)
  B  3-3.49 [#########################.......] 267 (26%)
  A  3.5-4  [##################...............] 139 (13%)

  STUDENTS BY MAJOR
  Computer Science [###################........] 185 (18%)
  Mathematics      [##############.............] 145 (14%)
  Physics          [#############..............] 133 (13%)
  ...more majors...
```

**Dashboard Actions:**
- `S` - Search students
- `T` - Top-K ranking
- `A` - Add student
- `F` - Filter by major
- `D` - Detect duplicates
- `E` - Export to CSV
- `R` - Refresh
- `X` - Back to main menu

### CRUD Operations

#### Add Student (Option 2)
```
═══════════════════════════════════════════════════════
  ADD STUDENT
═══════════════════════════════════════════════════════

  ID    : 5001
  Name  : Ahmed Hassan
  GPA   (0.00 - 4.00) : 3.85
  Age   (16 - 100)    : 20
  
  SELECT MAJOR
  ────────────────────────────────────────────
   1. Computer Science
   2. Electrical Engineering
   3. Mechanical Engineering
   ...
  10. Architecture
  ────────────────────────────────────────────
  Choice (1-10): 1

  ┌──────┬──────┬───────────────┬──────┬────┬───┬─────────────────┐
  │ #    │ ID   │ Name          │ GPA  │ Gr │Age│ Major           │
  ├──────┼──────┼───────────────┼──────┼────┼───┼─────────────────┤
  │ 1001 │ 5001 │ Ahmed Hassan  │ 3.85 │ A  │20 │ Computer Science│
  └──────┴──────┴───────────────┴──────┴────┴───┴─────────────────┘

  [OK]   Added: Ahmed Hassan  GPA: 3.85 (A )
  [i]    Saved to students.dat
```

#### Display All (Option 5)
```
ALL STUDENTS
1,000 records total

┌───┬──────────┬─────────────────────┬──────┬────┬───┬────────────────┐
│ # │ ID       │ Name                │ GPA  │ Gr │Age│ Major          │
├───┼──────────┼─────────────────────┼──────┼────┼───┼────────────────┤
│ 1 │ 1001     │ Ali Ahmed           │ 4.00 │ A+ │23 │ Computer Sci.  │
│ 2 │ 1002     │ Sara Mohammed       │ 3.99 │ A+ │22 │ Mathematics    │
│ 3 │ 1003     │ Omar Hassan         │ 3.98 │ A+ │21 │ Physics        │
│ 4 │ 1004     │ Lina Saleh          │ 3.97 │ A+ │20 │ Chemistry      │
│ 5 │ 1005     │ Hassan Karim        │ 3.96 │ A  │24 │ IT             │
└───┴──────────┴─────────────────────┴──────┴────┴───┴────────────────┘

  Page 1 / 50   Rows 1-20 of 1000

  P  Prev    N  Next    X  Back
  Action: N
```

---

## 🧮 Algorithms Explained

### Sorting Algorithms

#### 1. **Bubble Sort** (by GPA, descending)
```
Algorithm: Compare adjacent elements, swap if out of order
Field: GPA (highest first)
Time Complexity:
  • Best: O(n) - Already sorted
  �� Average: O(n²) - Random data
  • Worst: O(n²) - Reverse sorted

Use Case: Educational, small datasets (n < 1000)

Visual Example:
Pass 1: [3.5, 4.0, 2.8, 3.2, 1.5] → [4.0, 3.5, 3.2, 2.8, 1.5]
Pass 2: [4.0, 3.5, 3.2, 2.8, 1.5] → [4.0, 3.5, 3.2, 2.8, 1.5]
```

#### 2. **Insertion Sort** (by ID, ascending)
```
Algorithm: Build sorted array by inserting elements one by one
Field: ID (lowest first)
Time Complexity:
  • Best: O(n) - Pre-sorted
  • Average: O(n²) - Random
  • Worst: O(n²) - Reverse sorted

Use Case: Nearly sorted data, online sorting

Visual Example:
[3, 1, 4, 1, 5] → [1, 1, 3, 4, 5]
  Builds left-to-right with each element placed correctly
```

#### 3. **Selection Sort** (by Age, ascending)
```
Algorithm: Find minimum, move to front, repeat
Field: Age
Time Complexity:
  • Best: O(n²)
  • Average: O(n²)
  • Worst: O(n²)

Use Case: When memory writes are expensive
         (minimal swaps: O(n))

Visual Example:
[25, 19, 22, 21, 23]
Find min (19) → [19, 25, 22, 21, 23]
Find min (21) → [19, 21, 25, 22, 23]
...
```

#### 4. **Merge Sort** (by Name, ascending)
```
Algorithm: Divide & Conquer - split, recursively sort, merge
Field: Name (A-Z)
Time Complexity:
  • Best: O(n log n)
  • Average: O(n log n)
  • Worst: O(n log n)

Space: O(n) - Requires temporary arrays

Advantages:
  ✓ Guaranteed O(n log n)
  ✓ Stable sort (maintains order of equal elements)
  ✓ Parallelizable

Visual Example:
[Alice, Bob, Charlie, David]
Split: [Alice, Bob] | [Charlie, David]
Sort:  [Alice, Bob] | [Charlie, David]
Merge: [Alice, Bob, Charlie, David]
```

#### 5. **Quick Sort** (by GPA, descending)
```
Algorithm: Partition + Recursively sort parts
Field: GPA (highest first)
Time Complexity:
  • Best: O(n log n) - Balanced partition
  • Average: O(n log n)
  • Worst: O(n²) - Avoided by median-of-three

Optimization: Median-of-Three Pivot
  • Compares first, middle, last elements
  • Chooses median as pivot
  • Dramatically reduces worst-case probability

Visual Example:
[3.5, 4.0, 2.8, 3.2] → Pivot: 3.5
Left (>3.5): [4.0]
Pivot: [3.5]
Right (<3.5): [2.8, 3.2]
Result: [4.0, 3.5, 3.2, 2.8]
```

### Searching Algorithms

#### 1. **Linear Search** (by Name)
```
Time Complexity: O(n)
Method: Check each student's name sequentially

Example:
Students: [Ali, Sara, Omar, Lina, Hassan]
Search for: "Omar"

Step 1: Ali == Omar? NO
Step 2: Sara == Omar? NO
Step 3: Omar == Omar? YES ✓ Found at index 2

Comparisons: 3
```

#### 2. **Binary Search** (by ID)
```
Time Complexity: O(log n)
Requirement: Data must be sorted by ID

Example:
Sorted IDs: [1001, 1003, 1005, 1007, 1009, 1011, 1013]
Search for: 1007

Step 1: Mid = 1007, Found! ✓

For 100,000 students:
Max comparisons = log₂(100,000) ≈ 17

Performance: 100x faster than linear search on large data
```

#### 3. **Smart Multi-field Search**
```
Searches: Name (partial, case-insensitive), ID, Major
Example:
Query: "comp"

Results:
1. Ali Ahmed - Computer Science
2. Sara Computer - Information Technology
3. Omar Compiler - Computer Engineering

Method: Converts to lowercase, finds substring matches
```

---

## 🌳 Data Structures

### Student Record

```c++
struct Student {
    int    id;           // Unique identifier (1-100000)
    string name;         // Full name (letters & spaces)
    double gpa;          // Grade Point Average (0.00 - 4.00)
    int    age;          // Student age (16-100)
    string major;        // Field of study
};
```

### AVL Tree (Self-Balancing BST)

```
Purpose: Efficient O(log n) searching by ID with balanced tree

Structure:
        ┌─────┐
        │ 1005│
        └──┬──┘
        /  \
    ┌──▼┐  ┌──▼┐
    │1003│  │1007│
    └────┘  └────┘
    /   \   /   \
  1001 1004 1006 1009

Height-Balanced Property:
  |height(left) - height(right)| ≤ 1

Operations:
  • Insert: O(log n) + auto-rebalance
  • Search: O(log n)
  • Delete: O(log n)
  • Inorder Traverse: O(n) - gives sorted order by ID
```

---

## 📊 Advanced Features

### Statistics & Analysis (Option 9)

```
GPA STATISTICS
┌──────────────────────────────────────────────────────┐
│ Total students   : 1,000                             │
│ Mean GPA         : 2.84 (C )                         │
│ Median GPA       : 2.91 (C )                         │
│ Std Deviation    : 0.98                              │
│ Highest GPA      : 4.00 -- Ali Ahmed                 │
│ Lowest GPA       : 0.25 -- Sara Mohammed             │
└──────────────────────────────────────────────────────┘

GPA DISTRIBUTION
F  <1.0    [#########........................] 95    (9%)
D  1-1.99  [###################...............] 198   (19%)
C  2-2.99  [################################..] 301   (30%)
B  3-3.49  [#########################.......] 267   (26%)
A  3.5-4   [##################...............] 139   (13%)

MAJOR BREAKDOWN
Computer Science   [####################.....] 245 (24%)
Mathematics        [#############............] 159 (15%)
Physics            [############.............] 148 (14%)
...
```

### Top-K Ranking (Option 8)

```
TOP 10 STUDENTS BY GPA

┌──────┬──────┬────┬──────────────────┬────┬──────────────────┐
│ Rank │ GPA  │ Gr │ Name             │Age │ Major            │
├──────┼──────┼────┼──────────────────┼────┼──────────────────┤
│ #1   │ 4.00 │ A+ │ Ali Ahmed        │ 23 │ Computer Science │
│ #2   │ 3.99 │ A+ │ Sara Mohammed    │ 22 │ Mathematics      │
│ #3   │ 3.98 │ A+ │ Omar Hassan      │ 21 │ Physics          │
│ #4   │ 3.97 │ A+ │ Lina Saleh       │ 20 │ Chemistry        │
│ #5   │ 3.96 │ A  │ Hassan Karim     │ 24 │ IT               │
│ #6   │ 3.95 │ A  │ Nour Fatima      │ 22 │ Biology          │
│ #7   │ 3.94 │ A  │ Yusuf Ali        │ 21 │ Engineering      │
│ #8   │ 3.93 │ A  │ Dina Hassan      │ 23 │ Architecture     │
│ #9   │ 3.92 │ A  │ Khaled Omar      │ 20 │ Civil Eng.       │
│ #10  │ 3.91 │ A  │ Maya Sara        │ 22 │ Electrical Eng.  │
└──────┴──────┴────┴──────────────────┴────┴──────────────────┘
```

### Filter by Major (Option 10)

```
FILTER BY MAJOR
────────────────────────────────────────────────────

SELECT MAJOR
 1. Computer Science
 2. Electrical Engineering
...
10. Architecture

Choice (1-10): 1

[i] 245 student(s) in Computer Science:

┌───┬────────┬──────────────────┬──────┬────┬───┬──────────────┐
│ # │ ID     │ Name             │ GPA  │ Gr │Age│ Major        │
├───┼────────┼──────────────────┼──────┼────┼───┼──────��─── ─┤
│ 1 │ 1001   │ Ali Ahmed        │ 4.00 │ A+ │23 │ Comp. Science│
│ 2 │ 1008   │ Fatima Ali       │ 3.88 │ A  │21 │ Comp. Science│
│ 3 │ 1015   │ Mohammed Hassan  │ 3.75 │ A  │22 │ Comp. Science│
│...│ ...    │ ...              │ ...  │ ...│...│ ...          │
└───┴────────┴──────────────────┴──────┴────┴───┴──────────────┘

Average GPA in this major: 3.42
```

### Duplicate Detection (Option 11)

```
DUPLICATE GPA DETECTOR

[i] Method: sort copy -> adjacent scan   O(n log n) + O(n)

[DUP #1] GPA 3.85  →  Ahmed Hassan  &  Fatima Ali
[DUP #2] GPA 3.75  →  Omar Hassan  &  Sara Mohammed
[DUP #3] GPA 2.50  →  Lina Saleh  &  Hassan Karim
[~]  3 duplicate pair(s) detected.
```

---

## 📈 Performance Benchmarking

### Benchmark Suite (Option 13)

The system includes a comprehensive benchmarking engine that compares all 5 sorting algorithms across:

```
Test Matrix:
┌──────────────────────────────────────────────────┐
│ Algorithms (5)                                   │
├──────────────────────────────────────────────────┤
│ 1. Bubble Sort      4. Merge Sort                │
│ 2. Insertion Sort   5. Quick Sort                │
│ 3. Selection Sort                                │
├──────────────────────────────────────────────────┤
│ Data Sizes (4)                                   │
├──────────────────────────────────────────────────┤
│ • 50 records       • 10,000 records              │
│ • 1,000 records    • 100,000 records             │
├──────────────────────────────────────────────────┤
│ Data Distributions (3)                           │
├──────────────────────────────────────────────────┤
│ • Random           • Nearly Sorted               │
│ • Reverse Sorted                                 │
└──────────────────────────────────────────────────┘

Total Runs: 60 (O(n²) algorithms skipped at n=100k)
```

### Sample Benchmark Output

Real output from one run (Random data), compiled with `clang++ -O1` on an Apple Silicon Mac. Times will differ on your machine; the comparison counts will be close.

```
Algorithm        | Size     | Type           | Time(ms)    | Comparisons   | Swaps
-----------------+----------+----------------+-------------+---------------+-----------
Bubble Sort      | 50       | Random         | 0.012       | 1189          | 617
Insertion Sort   | 50       | Random         | 0.004       | 645           | 599
Selection Sort   | 50       | Random         | 0.007       | 1225          | 39
Merge Sort       | 50       | Random         | 0.026       | 220           | 0
Quick Sort       | 50       | Random         | 0.004       | 228           | 164
Bubble Sort      | 1000     | Random         | 3.747       | 499329        | 233600
Insertion Sort   | 1000     | Random         | 1.180       | 248154        | 247161
Selection Sort   | 1000     | Random         | 2.816       | 499500        | 900
Merge Sort       | 1000     | Random         | 0.378       | 8706          | 0
Quick Sort       | 1000     | Random         | 0.123       | 9817          | 5450
Bubble Sort      | 10000    | Random         | 284.055     | 49954814      | 24807198
Insertion Sort   | 10000    | Random         | 66.348      | 25136212      | 25126218
Selection Sort   | 10000    | Random         | 158.179     | 49995000      | 9034
Merge Sort       | 10000    | Random         | 2.551       | 120454        | 0
Quick Sort       | 10000    | Random         | 0.871       | 228447        | 64995
Bubble Sort      | 100000   | Random         | SKIPPED     | SKIPPED       | SKIPPED
Insertion Sort   | 100000   | Random         | SKIPPED     | SKIPPED       | SKIPPED
Selection Sort   | 100000   | Random         | SKIPPED     | SKIPPED       | SKIPPED
Merge Sort       | 100000   | Random         | 31.727      | 1536136       | 0
Quick Sort       | 100000   | Random         | 15.907      | 13557431      | 727581

VISUAL COMPARISON  (n=10,000, Random data)
--------------------------------------------
Bubble Sort      [##########################] 284.055 ms
Insertion Sort   [######....................] 66.348 ms
Selection Sort   [##############............] 158.179 ms
Merge Sort       [..........................] 2.551 ms
Quick Sort       [..........................] 0.871 ms
```

### How the input is prepared

Each algorithm sorts by a different field (GPA, ID, age or name), so the input is arranged for each algorithm separately:

- **Random:** the records are shuffled, so no field is in order, IDs included.
- **Nearly Sorted:** the data is first sorted in that algorithm's own order, then about 5% of the records are swapped at random.
- **Reverse Sorted:** the data is sorted in that algorithm's own order and then reversed.

### Benchmark Insights

From the same run:

```
1. The O(n^2) cliff
   - n=1,000:    0.1 to 4 ms for every algorithm
   - n=10,000:   O(n^2) sorts take 66 to 284 ms; merge and quick sort stay under 3 ms
   - n=100,000:  O(n^2) sorts are skipped (about 90 s each); merge sort 32 ms, quick sort 16 ms

2. Comparisons tell the same story (n=10,000, Random)
   - Bubble and selection sort:  about 50,000,000  (n^2 / 2)
   - Insertion sort:             about 25,000,000  (n^2 / 4)
   - Merge sort:                 120,454
   - Quick sort:                 228,447

3. Input order matters most for insertion sort (n=10,000)
   - Random:          25,136,212 comparisons
   - Nearly Sorted:    3,027,901 comparisons
   - Reverse Sorted:  49,995,000 comparisons (its worst case)

4. Quick sort and repeated values
   - GPA has only 401 possible values, so large inputs contain many equal keys.
     At n=100,000 quick sort still finishes in 16 to 31 ms, but it makes far more
     comparisons than merge sort (13.6 million against 1.5 million on Random data).
```

---

## 📖 API Reference

### Core Functions

| Function | Purpose | Time Complexity |
|----------|---------|-----------------|
| `addStudent()` | Add new student record | O(1) amortized |
| `deleteStudent()` | Remove student by ID | O(n) |
| `updateStudent()` | Modify student info | O(n) search + O(1) update |
| `displayStudents()` | Show all records (paginated) | O(n) |
| `bubbleSortGPA()` | Sort by GPA descending | O(n²) |
| `insertionSortID()` | Sort by ID ascending | O(n²) |
| `selectionSortAge()` | Sort by age ascending | O(n²) |
| `mergeSortName()` | Sort by name ascending | O(n log n) |
| `quickSortGPA()` | Sort by GPA descending | O(n log n) avg |
| `linearSearchName()` | Find by exact name | O(n) |
| `binarySearchID()` | Find by ID (requires pre-sort) | O(log n) |
| `searchAllFields()` | Multi-field smart search | O(n) |
| `statistics()` | Calculate GPA stats | O(n) |
| `topK()` | Get top K students | O(n log n) |
| `avlIns()` | Insert to AVL tree | O(log n) |
| `avlSrch()` | Search AVL tree | O(log n) |

### File I/O

```cpp
void saveToFile();       // Save all records to students.dat
void loadFromFile();     // Load from students.dat on startup
void exportToCSV();      // Export records to CSV format
```

### Utility Functions

```cpp
string dbl(double v, int dec);  // Format decimal to string
string pad(const string& s, int w); // Pad string to width
string letterGrade(double gpa); // Convert GPA to letter grade
bool idExists(int id);    // Check if ID already exists
bool validName(const string& s); // Validate name format
```

---

## 📸 Screenshots & Examples

### Example 1: Adding a Student

```
ADD STUDENT
═══════════════════════════════════════════════════════

  ID    : 5001
  Name  : Ahmed Hassan
  GPA   (0.00 - 4.00) : 3.85
  Age   (16 - 100)    : 20
  
  SELECT MAJOR
  ────────────────────────────────────────────
   1. Computer Science
   2. Electrical Engineering
   3. Mechanical Engineering
   4. Civil Engineering
   5. Information Technology
   6. Mathematics
   7. Physics
   8. Biology
   9. Chemistry
  10. Architecture
  ────────────────────────────────────────────
  Choice (1-10): 1

  ┌───┬──────────┬───────────────┬──────┬────┬───┬──────────────┐
  │ # │ ID       │ Name          │ GPA  │ Gr │Age│ Major        │
  ├───┼──────────┼───────────────┼──────┼────┼───┼──────────────┤
  │ 1 │ 5001     │ Ahmed Hassan  │ 3.85 │ A  │20 │ Comp. Science│
  └───┴──────────┴───────────────┴──────┴────┴───┴──────────────┘

  [OK]   Added: Ahmed Hassan  GPA: 3.85 (A )
  [i]    Saved to students.dat
```

### Example 2: Sorting and Performance

```
DONE: Quick Sort -- GPA descending
════════════════════════════════════════════════════════

  Comparisons : 118,456
  Swaps       :     95,234
  Time        : 12.340 ms
════════════════════════════════════════════════════════

Preview (first 5 after sort):

┌───┬────────┬──────────────────┬──────┬────┬───┬──────────────┐
│ # │ ID     │ Name             │ GPA  │ Gr │Age│ Major        │
├───┼────────┼──────────────────┼──────┼────┼───┼──────────────┤
│ 1 │ 1001   │ Ali Ahmed        │ 4.00 │ A+ │23 │ Comp. Science│
│ 2 │ 1002   │ Sara Mohammed    │ 3.99 │ A+ │22 │ Mathematics  │
│ 3 │ 1003   │ Omar Hassan      │ 3.98 │ A+ │21 │ Physics      │
│ 4 │ 1004   │ Lina Saleh       │ 3.97 │ A+ │20 │ Chemistry    │
│ 5 │ 1005   │ Hassan Karim     │ 3.96 │ A  │24 │ IT           │
└───┴────────┴──────────────────┴──────┴────┴───┴──────────────┘
```

### Example 3: Search with Statistics

```
SEARCH STUDENTS
═══════════════════════════════════════════════════════

  1. By exact name  -- Linear Search   O(n)
  2. By ID          -- Binary Search   O(log n)
  3. Smart search   -- name / ID / major

  Choice: 1
  Exact name: Ali Ahmed

  FOUND:

  ┌───┬────────┬──────────────────┬──────┬────┬───┬──────────────┐
  │ # │ ID     │ Name             │ GPA  │ Gr │Age│ Major        │
  ├───┼────────┼──────────────────┼──────┼────┼───┼──────────────┤
  │ 1 │ 1001   │ Ali Ahmed        │ 4.00 │ A+ │23 │ Comp. Science│
   ───┴────────┴──────────────────┴──────┴────┴───┴──────────────┘

  Comparisons: 1   Time: 0.0023 ms
```

---

## 🔧 Troubleshooting

### Common Issues & Solutions

| Issue | Cause | Solution |
|-------|-------|----------|
| **File not found** | No `students.dat` file | Normal on first run; will be created after adding data |
| **Memory error** | Trying to load > 100k records | Increase `MAX` constant or reduce data |
| **Slow performance** | Running O(n²) on large dataset | Use Merge/Quick Sort instead; see benchmarks |
| **Compilation fails** | C++ version too old | Ensure C++11 or newer: `g++ -std=c++11` |
| **CSV export fails** | No write permissions | Check folder permissions; run in writable directory |
| **Segmentation fault** | Data corruption | Delete `students.dat` and rebuild data |

### Performance Tips

```
✓ For < 1,000 students:    Use any sorting algorithm
✓ For 1,000-10,000:        Use Merge Sort or Quick Sort
✓ For > 10,000:            Use Quick Sort (fastest average)
✓ For searching:           Use Binary Search on sorted data
✓ For recurring searches:   Use AVL Tree for O(log n) access
✓ For best benchmarks:     Run on unloaded system; close browsers
```

---

## 📝 Sample Data

### Majors (10)

1. Computer Science
2. Electrical Engineering
3. Mechanical Engineering
4. Civil Engineering
5. Information Technology
6. Mathematics
7. Physics
8. Biology
9. Chemistry
10. Architecture

### GPA to Grade Conversion

| GPA Range | Letter Grade | Description |
|-----------|--------------|-------------|
| 3.7-4.0 | A+ | Excellent |
| 3.3-3.69 | A | Very Good |
| 3.0-3.29 | B+ | Good |
| 2.7-2.99 | B | Satisfactory |
| 2.3-2.69 | C+ | Fair |
| 2.0-2.29 | C | Average |
| 1.5-1.99 | D | Below Average |
| 0-1.49 | F | Fail |

---

## 🎓 Educational Value

This project demonstrates:

- **Algorithm Design & Analysis**
  - Time/space complexity calculation
  - Performance comparison
  - Algorithm trade-offs

- **Data Structures**
  - Arrays and dynamic allocation
  - Binary Search Trees (AVL)
  - Tree balancing

- **Software Engineering**
  - Modular design
  - Input validation
  - Error handling
  - Persistent storage

- **Performance Analysis**
  - Benchmarking methodology
  - Metrics collection
  - Visual comparisons

---

## 🔄 Keyboard Shortcuts

| Key | Action | Context |
|-----|--------|---------|
| `P` | Previous page | Pagination |
| `N` | Next page | Pagination |
| `X` | Back/Exit | Any menu |
| `S` | Search | Dashboard |
| `T` | Top-K | Dashboard |
| `A` | Add | Dashboard |
| `D` | Delete | Main menu |
| `R` | Refresh | Dashboard |
| `E` | Export | Dashboard |
| `F` | Filter | Dashboard |
| `Enter` | Confirm | Input dialogs |

---

## 📦 File Formats

### students.dat (Internal Format)

```
<count>
<id>
<name>
<gpa>
<age>
<major>
<id>
<name>
...
```

Example:
```
3
1001
Ali Ahmed
4.00
23
Computer Science
1002
Sara Mohammed
3.99
22
Mathematics
```

### students_export.csv

```
ID,Name,GPA,Grade,Age,Major
1001,"Ali Ahmed",4.00,A+,23,"Computer Science"
1002,"Sara Mohammed",3.99,A+,22,"Mathematics"
```

---

## 🤝 Contributing

Contributions are welcome! Areas for enhancement:

- [ ] GUI implementation (Qt/wxWidgets)
- [ ] Database backend (SQLite)
- [ ] Network features (multi-user)
- [ ] Additional algorithms (Heap Sort, Radix Sort)
- [ ] Mobile app version
- [ ] Performance optimizations

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/enhancement`)
3. Make your changes
4. Test thoroughly
5. Submit a pull request

---

## 👥 Credits

**Developed by:** Code Hunters Team  
**Supervised by:** Eng. Sama & Eng. Yara  
**University:** [Your Institution]  
**Course:** Design & Analysis of Algorithms

---

## 📄 License

This project is provided for **educational purposes only**.

---

## 📞 Support & Contact

For issues, questions, or suggestions:

- 📧 Open an issue on GitHub
- 💬 Submit a discussion
- 🐛 Report bugs with reproduction steps

---

## 🎯 Future Roadmap

```
v1.0 (Current)
├─ Core CRUD operations
├─ 5 sorting algorithms
├─ 3 search methods
└─ Basic benchmarking

v1.1 (Planned)
├─ GUI interface
├─ More sorting algorithms
├─ Data import/export
└─ Enhanced statistics

v2.0 (Future)
├─ Database backend
├─ Multi-user support
├─ REST API
└─ Mobile app
```

---

<div align="center">

### ⭐ If you found this project helpful, please give it a star!

**Made with ❤️ by Code Hunters**
**Under Supervision Of Eng.Sama & Eng.Yara**

[↑ Back to Top](#-student-grade-management-system)

</div>
