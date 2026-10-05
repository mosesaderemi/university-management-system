# University Management System

A JavaFX desktop application that manages students, teachers, courses and subjects for a university. It provides three role-based interfaces for administrators, teachers and students, backed by MySQL.

## Features

- Login for users stored in the `users` table, with separate screens for Admin, Teacher and Student
- Administrator:
  - Dashboard with totals for students and teachers and charts
  - Add, update and delete students
  - Add, update, delete and import teachers, with department, status and gender lists and generated teacher IDs
  - Add, update and delete courses
  - Manage teacher salary records
- Teacher:
  - Add and remove students for the courses the teacher handles
  - Assign and remove subjects the teacher handles
- Student: view the teachers linked to the student
- Alert helper classes and custom CSS for the login and main forms

## Tech Stack

| Area | Technology |
| --- | --- |
| Language | Java |
| UI | JavaFX, FXML, CSS |
| Database | MySQL through JDBC |
| Libraries | FontAwesomeFX 8.2, MySQL Connector/J 5.1.48, ojdbc14 |
| IDE | Apache NetBeans project |

## Project Structure

```text
UniversitiyManagementSystem
├── build.xml
├── nbproject                       NetBeans project configuration
└── src
    ├── Design                      LoginForm.css, MainForm.css
    └── universitiymanagementsystem
        ├── UniversitiyManagementSystem.java   Application entry point
        ├── FXMLDocument.fxml / Controller     Login and role routing
        ├── AdminMainForm.fxml / Controller
        ├── TeacherMainForm.fxml / Controller
        ├── StudentMainForm.fxml / Controller
        ├── AddStudent.fxml / Controller
        ├── Database.java                      JDBC connection helper
        └── StudentData, TeacherData, CourseData, SubjectData, SalaryData, ListData ...
```

## Getting Started

### Prerequisites

- JDK 8 with JavaFX, or a JDK with a separate JavaFX SDK configured in your IDE
- Apache NetBeans
- MySQL or MariaDB

### Database

The connection is defined in `src/universitiymanagementsystem/Database.java` and expects a database named `university` on `localhost` with the user `root` and an empty password. The code uses the tables `users`, `student`, `teacher`, `course`, `subject`, `teacher_student`, `teacher_handle` and `salary`. Create the database and these tables before the first run and insert at least one administrator into `users`. Column names are defined by the SQL statements in the controller classes.

### Libraries

The compiled `dist` and `build` folders are not stored in this repository. Add `fontawesomefx-8.2.jar`, `mysql-connector-java-5.1.48.jar` and `ojdbc14-10.2.0.2.0.jar` under Project Properties, then Libraries. The stored paths point to the original development machine and must be re-added on a new computer.

### Run

1. Start MySQL and create the database and tables.
2. Open the `UniversitiyManagementSystem` folder as a project in NetBeans.
3. Add the libraries and run the project. The main class is `universitiymanagementsystem.UniversitiyManagementSystem`.

## Security Notes

Some queries are built with string concatenation and passwords are stored as entered. Use prepared statements and hashed passwords before any real deployment.

## Author

Aderemi Moses Timileyin
GitHub: [@mosesaderemi](https://github.com/mosesaderemi)
LinkedIn: [linkedin.com/in/mosesaderemi-6a70a5405](https://www.linkedin.com/in/mosesaderemi-6a70a5405)

## License

Released under the MIT License. See the `LICENSE` file for details.
