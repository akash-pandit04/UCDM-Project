# University Curriculum Data Manager (UCDM)

**UCDM** is a robust Command Line Interface (CLI) Java application designed to manage university academic records. It handles the lifecycle of students, courses, instructors, enrollments, and grading systems with persistent data storage using CSV files.

## 🚀 Features

### 🎓 Student Management
* **Registration & Profiles:** Register new students with unique IDs and manage their profiles.
* **Search:** Find students by name, registration number, or email using Java Streams API.
* **Transcripts:** Generate detailed transcripts that include enrolled courses, grades, and automatically calculated GPA.

### 📚 Course Management
* **Course Creation:** specific Flexible course creation using the **Builder Design Pattern**.
* **Advanced Filtering:** Search courses by Instructor, Department, or Semester (SPRING, SUMMER, FALL).
* **Credit System:** Enforces a maximum credit limit (default 24) per semester to prevent overloading.

### 📝 Enrollment & Grading
* **Enrollment Logic:** Handles student course registration while checking for duplicate enrollments.
* **Grading Scale:** Records marks and automatically converts them to letter grades (S, A, B, C, D, E, F) and grade points.

### 💾 Data Persistence & System
* **CSV Import/Export:** Seamlessly import and export data for Students and Courses (`students.csv`, `courses.csv`).
* **Backup System:** Automated backup functionality that creates timestamped snapshots of the data directory.
* **Singleton Configuration:** Centralized management of application settings (e.g., data directory paths).

---

## 🛠️ Technical Concepts

This project demonstrates proficiency in Core Java and Object-Oriented Programming (OOP) principles:

* **Design Patterns:**
    * **Singleton:** Used in `AppConfig` to manage global application state.
    * **Builder:** Used in `Course.Builder` to construct complex Course objects cleanly.
* **OOP Pillars:**
    * **Inheritance:** `Student` and `Instructor` extend the abstract `Person` class.
    * **Polymorphism:** Overriding methods like `getProfile()` and `toString()`.
    * **Abstraction:** Usage of interfaces like `Searchable<T>` and `Persistable`.
* **Modern Java Features:**
    * **Java Streams:** Used extensively for filtering lists and processing collections.
    * **Switch Expressions:** concise control flow in the CLI menu.
    * **Java NIO:** Efficient file handling for backups and CSV parsing.

---

## 💻 Installation & Usage

### Prerequisites
* **Java Development Kit (JDK):** Version 14 or higher (required for switch expressions).

### Steps to Run

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Pranavsingal/University-Curriculum-Data-Manager-UCDM-.git](https://github.com/Pranavsingal/University-Curriculum-Data-Manager-UCDM-.git)
    cd University-Curriculum-Data-Manager-UCDM-
    ```

2.  **Compile the source code:**
    ```bash
    javac ucdm.java
    ```

3.  **Run the application:**
    ```bash
    java ucdm
    ```

4.  **Menu Navigation:**
    The application will launch a main menu:
    ```text
    --- Main Menu ---
    1. Manage Students
    2. Manage Courses
    3. Manage Enrollments
    4. Manage Grades
    5. Import/Export Data
    6. Backup Operations
    7. Generate Reports
    0. Exit
    ```

---

## 📂 Data Format

The application reads and writes data to the `ucdm_data` directory.

### 1. Students (`students.csv`)
**Format:** `ID,RegNo,Name,Email,IsActive,CreatedDate`
```csv
S001,2023001,Pranav Singal,pranav.singal@student.edu,true,2025-11-21T22:27:03
S002,2023002,Sarvagya Joshi,sarvagya.joshi@student.edu,true,2025-11-21T22:27:03
