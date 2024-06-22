# Guvi Zen Class Database Model

This repository contains the database model for the Guvi Zen Class, designed to manage students, instructors, courses, classes, assignments, and grades.

## Entity-Relationship Diagram (ERD)
![ERD](path/to/your/erd/image.png)

## Entity Descriptions

### Student
- **student_id** (Primary Key)
- **first_name**
- **last_name**
- **email**
- **phone**
- **enrollment_date**

### Instructor
- **instructor_id** (Primary Key)
- **first_name**
- **last_name**
- **email**
- **phone**
- **hire_date**

### Course
- **course_id** (Primary Key)
- **course_name**
- **description**
- **credits**

### Class
- **class_id** (Primary Key)
- **course_id** (Foreign Key)
- **instructor_id** (Foreign Key)
- **start_date**
- **end_date**
- **schedule**

### Enrollment
- **enrollment_id** (Primary Key)
- **student_id** (Foreign Key)
- **class_id** (Foreign Key)
- **enrollment_date**

### Assignment
- **assignment_id** (Primary Key)
- **class_id** (Foreign Key)
- **title**
- **description**
- **due_date**

### Grade
- **grade_id** (Primary Key)
- **assignment_id** (Foreign Key)
- **student_id** (Foreign Key)
- **grade**

## Relationships

- Each student can enroll in multiple classes.
- Each class can have multiple students enrolled.
- Each class is taught by one instructor, but an instructor can teach multiple classes.
- Each course can have multiple classes.
- Each class can have multiple assignments.
- Each student can receive multiple grades for different assignments.

## Example Data

### Students

| student_id | first_name | last_name | email                  | phone         | enrollment_date |
|------------|------------|-----------|------------------------|---------------|-----------------|
| 1          | John       | Doe       | john.doe@example.com   | 123-456-7890  | 2024-01-15      |
| 2          | Jane       | Smith     | jane.smith@example.com | 098-765-4321  | 2024-01-16      |

### Instructors

| instructor_id | first_name | last_name | email                   | phone        | hire_date  |
|---------------|------------|-----------|-------------------------|--------------|------------|
| 1             | Alice      | Johnson   | alice.johnson@example.com | 555-123-4567 | 2023-01-10 |
| 2             | Bob        | Williams  | bob.williams@example.com | 555-987-6543 | 2023-01-11 |

### Courses

| course_id | course_name         | description                            | credits |
|-----------|---------------------|----------------------------------------|---------|
| 1         | Python Programming  | Learn the basics of Python programming.| 3       |
| 2         | Data Science        | Introduction to data science concepts and techniques. | 4       |

### Classes

| class_id | course_id | instructor_id | start_date | end_date   | schedule              |
|----------|-----------|---------------|------------|------------|-----------------------|
| 1        | 1         | 1             | 2024-02-01 | 2024-05-01 | Mon, Wed, Fri 10-11am |
| 2        | 2         | 2             | 2024-03-01 | 2024-06-01 | Tue, Thu 2-4pm        |

### Enrollments

| enrollment_id | student_id | class_id | enrollment_date |
|---------------|------------|----------|-----------------|
| 1             | 1          | 1        | 2024-02-01      |
| 2             | 2          | 2        | 2024-03-01      |

### Assignments

| assignment_id | class_id | title            | description                               | due_date   |
|---------------|----------|------------------|-------------------------------------------|------------|
| 1             | 1        | Python Basics    | Complete the basic Python exercises.      | 2024-03-01 |
| 2             | 2        | Data Analysis    | Analyze the given dataset and report findings. | 2024-04-01 |

### Grades

| grade_id | assignment_id | student_id | grade |
|----------|----------------|------------|-------|
| 1        | 1              | 1          | A     |
| 2        | 2              | 2          | B     |

## Setup Instructions

1. Clone the repository: `git clone https://github.com/your-username/guvi-zen-class.git`
2. Navigate to the project directory: `cd guvi-zen-class`
3. Import the SQL script (`guvi_zen_class_schema.sql`) into your MySQL database.
4. Execute the script to create the database and tables.
5. Optionally, load the provided example data.

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
