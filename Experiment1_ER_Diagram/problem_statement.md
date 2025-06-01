# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Sachin B

## Scenario Chosen:
University

## ER Diagram:
![University ER diagram](https://github.com/user-attachments/assets/ad762c59-55cc-4276-90ac-fb4e66010135)

## Entities and Attributes:
 Entities and Attributes 
1. Student Attributes
    Student ID (Primary Key),
    Full Name,
    Date of Birth (DOB),
    Phone.
2. Instructor Attributes
    Instructor ID (Primary Key),
    Name,
    Phone.
3. Department Attributes
    Dept ID (Primary Key),
    Name.
4. Program Attributes
    Program ID (Primary Key),
    Dept ID (Foreign Key),
    Program Name (You can asume this based on context, even if not shown explicitly).
5. Course Attributes
    Course ID (Primary Key),
    Course Name,
    Credits.

## Relationships and Constraints:
1. Department – Program

    Relationship: A Department offers one or more Programs.

    Cardinality: One-to-Many (1 Department → Many Programs)

    Constraint: Dept ID is a foreign key in the Program entity, referencing Department.

2. Program – Student

    Relationship: A Student takes a Program.

    Cardinality: Many-to-One (Many Students → 1 Program)

    Constraint: Each student must be enrolled in exactly one program.

    Program ID is a foreign key in the Student entity.

3. Instructor – Student

    Relationship: An Instructor teaches one or more Students.

    Cardinality: Many-to-Many

    Constraint: Requires a junction table (e.g., Instructor_Student) with:

        Instructor ID (FK)

        Student ID (FK)

        Optional: Subject/Date/Time

4. Student – Course

    Relationship: A Student enrolls in one or more Courses.

    Cardinality: Many-to-Many

    Constraint: Requires a junction table (e.g., Enrollment) with:

        Student ID (FK)

        Course ID (FK)

        Optional: Grade, Semester, etc.

5. Instructor – Course

    Relationship: An Instructor handles a Course.

    Cardinality: One-to-Many (1 Instructor → Many Courses)

    Constraint: Instructor ID is a foreign key in the Course entity.

## Extension (Prerequisite / Billing):
Prerequisite

    Purpose: Links courses that must be completed before taking another.

    Type: Many-to-Many (Course ↔ Course).

    Attributes: Course ID, Prerequisite Course ID.

    Constraint: Both must exist in the Course table.

Billing

    Purpose: Tracks student payments/fees.

    Type: One-to-Many (Student → Billing).

    Attributes: Bill ID, Student ID, Amount, Date Issued, Status, Due Date.

    Constraint: Student ID is a foreign key.
## Design Choices:
Entities are clearly separated (e.g., Student, Instructor, Course) for clarity and normalization.

Primary and Foreign Keys ensure uniqueness and maintain relationships.

Relationships are well-defined using one-to-many or many-to-many (with junction tables).

Extensibility allows adding features like Prerequisites and Billing.

Constraints ensure data integrity and avoid redundancy or invalid links.








## RESULT
A complete ER model of a university system that defines students, courses, professors, and their interrelationships, including prerequisites, with proper constraints and rationale.
