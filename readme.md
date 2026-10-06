# 🎓 University Companion

A modern, offline-first Android application designed to help university students manage **attendance, daily classes, notes, academic documents, and backups** in one place.

The application is designed to work across different universities, departments, and academic systems rather than being tied to a specific university.

---

## ✨ Features

### 📊 Attendance Management

Track attendance for every course independently.

- Mark classes as **Present** or **Absent**
- Automatic attendance percentage calculation
- Configurable minimum attendance requirement
- Default minimum requirement: **60%**
- Change the requirement to suit your university, such as 40%, 50%, 60%, 70%, etc.
- Course-wise attendance statistics
- Attendance warning system
- Calculate how many classes can still be missed
- Calculate how many consecutive classes are required to recover attendance

Example:

```text
Classes Held: 20
Present: 14
Absent: 6

Attendance: 70%
Required: 60%

Status: Safe
```

---

### 📅 Today's Classes

The main daily workflow is designed to be extremely simple.

Students can see the classes scheduled for the current day and immediately mark their attendance.

```text
Today's Classes

10:00 AM
Public Administration

[ Present ] [ Absent ]

12:00 PM
Administrative Law

[ Present ] [ Absent ]
```

This avoids manually navigating through every course whenever attendance needs to be recorded.

---

### 🗓️ Yearly & Semester Support

The application does not assume a particular academic structure.

Students can choose:

- **Yearly**
- **Semester**

#### Yearly example

```text
1st Year
2nd Year
3rd Year
4th Year
```

#### Semester example

```text
1st Semester
2nd Semester
3rd Semester
...
```

The number of courses is also completely flexible.

A student may have:

- 8 courses
- 9 courses
- 10 courses
- 12 courses
- or any other number

No course limit is hard-coded into the application.

---

### 📚 Class Notes

Keep notes organized by **course and class date**.

Each class can contain multiple types of materials:

- 📝 Text notes
- 📷 Camera photos
- 🖼️ Images
- 📄 PDF files
- 📎 Other documents
- 🔗 Links

Example:

```text
Public Administration
│
├── 06 October 2026
│   ├── Board Photo
│   ├── Lecture PDF
│   └── My Notes
│
├── 04 October 2026
│   ├── Slides
│   └── My Notes
│
└── 01 October 2026
    └── Lecture PDF
```

This makes it easy to find exactly what was taught on a particular day.

---

## 🏗️ Architecture

The application follows a modern Android architecture designed to remain maintainable as the project grows.

```text
                    University Companion
                           │
             ┌─────────────┴─────────────┐
             │                           │
        Academic Data                Documents
             │                           │
      ┌──────┼──────┐             ┌──────┴──────┐
      │      │      │             │             │
   Courses Classes Attendance    Images       PDFs
             │
             ▼
        Local Database
             │
             ▼
       Backup / Sync
```

The core data model is intentionally generic:

```text
Academic System
      │
Academic Period
      │
    Course
      │
 Class Session
      │
 ┌────┴───────────────┐
 │                    │
Attendance           Notes
                       │
                 Attachments
```

This allows the same application to support different universities and academic structures without changing the core logic.

---

## 🛠️ Technology Stack

The project is built for Android using modern Android development technologies.

- **Kotlin**
- **Gradle**
- **Jetpack Compose**
- **Material 3**
- **Room Database**
- **DataStore**
- **WorkManager**
- Android Storage APIs

The architecture is designed to support offline-first operation and future expansion.

---

## 🔐 Offline First

The application should remain useful even without an internet connection.

Students can:

- View their courses
- View today's classes
- Mark attendance
- Write notes
- View previously saved notes
- Access locally available attachments

Synchronization and backup can happen when connectivity becomes available.

This is particularly important for classroom environments where internet connectivity may not always be reliable.

---

## 🎯 Design Goals

The application is built around several principles:

### 1. Simple

Daily attendance should require only a few taps.

### 2. Generic

The application should not be tied to one university or department.

### 3. Flexible

Different academic systems, course counts, and attendance requirements should be supported.

### 4. Offline-first

Core functionality should not depend on an internet connection.

### 5. Reliable

Academic records should be protected through backup and restore mechanisms.

### 6. Expandable

The architecture should allow additional academic features without rebuilding the core system.

---

## 🚀 Planned Features

The project can be expanded with additional modules such as:

- 🗓️ Timetable management
- 📝 Assignment tracking
- 🎓 Exam schedule
- 🔔 Academic reminders
- 🔍 Global search
- ⭐ Important notes
- 📈 Academic statistics
- ☁️ Improved cloud synchronization
- 📷 OCR from classroom/board photographs
- 🤖 AI-powered study assistance
- 🤖 Ask questions from personal notes
- 🧠 Automatic note summarization
- 📝 AI-generated practice questions

These features can be introduced progressively without changing the fundamental attendance and notes architecture.

---

## 📱 Intended Users

University students who want a single application for managing their academic activities.

The application is intended to support students from different:

- Universities
- Departments
- Bachelor's programs
- Academic years
- Semester systems
- Yearly systems

The project is **not limited to a specific university**.

---

## 📂 Core Modules

```text
Dashboard
│
├── Today's Classes
│
├── Attendance
│   ├── Course Attendance
│   ├── Attendance History
│   └── Attendance Statistics
│
├── Notes
│   ├── Course Notes
│   ├── Class Notes
│   └── Attachments
│
├── Academic Setup
│   ├── University
│   ├── Department
│   ├── Academic System
│   ├── Academic Period
│   └── Courses
│
└── Settings
    ├── Attendance Requirement
    └── Backup & Restore
```

---

## 🔢 Attendance Calculation

Attendance is calculated from actual class records rather than storing only a percentage.

```text
Attendance % = Present Classes / Classes Held × 100
```

For example:

```text
Present = 15
Classes Held = 20

15 / 20 × 100 = 75%
```

The result is then compared with the student's configured minimum attendance requirement.

```text
Attendance = 75%
Required   = 60%

75% ≥ 60% → Safe
```

If the requirement is changed to 80%:

```text
Attendance = 75%
Required   = 80%

75% < 80% → Warning
```

The underlying attendance records remain unchanged.

---

## 🤝 Contributing

Contributions, suggestions, bug reports, and feature requests are welcome.

If you would like to contribute:

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Test the application.
5. Submit a pull request.

For major changes, please open an issue first to discuss the proposed changes.

---

## 📄 License

This project is open source. See the repository's `LICENSE` file for the applicable license.

---

## 💡 Project Vision

University students often manage attendance, class notes, PDFs, photographs, assignments, and academic schedules across multiple applications and storage locations.

**University Companion** aims to bring these everyday academic tasks together into one simple, reliable application.

> **One student. One academic workspace.**
