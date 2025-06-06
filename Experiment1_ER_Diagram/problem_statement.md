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

# ER Diagram Submission - Student Name

## Scenario Chosen:
University / Hospital (choose one)

## ER Diagram:
![ER Diagram](er_diagram.png)

## Entities and Attributes:
1.Patient PatientID (Primary Key) FirstName LastName DateOfBirth Gender Address PhoneNumber Email

2.Doctor DoctorID (Primary Key) FirstName LastName Specialization Email PhoneNumber DepartmentID (Foreign Key)

3.Department DepartmentID (Primary Key) DepartmentName Location

4.Appointment AppointmentID (Primary Key) PatientID (Foreign Key) DoctorID (Foreign Key) AppointmentDate AppointmentTime Reason

5.MedicalRecord RecordID (Primary Key) PatientID (Foreign Key) DoctorID (Foreign Key) AppointmentID (Foreign Key) Diagnosis Treatment Notes RecordDate

6.Billing BillID (Primary Key) AppointmentID (Foreign Key) Amount BillingDate Status (Paid/Unpaid)

7.Payment PaymentID (Primary Key) BillID (Foreign Key) AmountPaid PaymentDate PaymentMethod (Cash, Card, Insurance, etc.)

## Relationships and Constraints:
Patient – Appointment Relationship: "Books" Constraint: One patient can have many appointments; each appointment is for one patient.

Doctor – Appointment Relationship: "Conducts" Constraint: One doctor can attend many appointments; each appointment involves one doctor.

Patient – MedicalRecord Relationship: "Has" Constraint: One patient can have multiple medical records; each record belongs to one patient.

Doctor – MedicalRecord Relationship: "Creates" Constraint: One doctor can create multiple records; each record is created by one doctor.

Appointment – MedicalRecord Relationship: "Generates" Constraint: One appointment generates exactly one medical record.

Appointment – Billing Relationship: "Triggers" Constraint: Each appointment generates one bill; each bill corresponds to one appointment.

Billing – Payment Relationship: "Settled by" Constraint: One bill can be paid via one or multiple payments (supporting split payments).

## Extension (Prerequisite / Billing):
Entity Name: PREREQUISITE Attributes: Course Code: Refers to the main course. Prerequisite Code: Refers to the required prerequisite course. Credits: May refer to the credit requirement for the prerequisite. Year: Could indicate the academic year the prerequisite is tied to.

Relationships: "requires" relationship connects the COURSE and PREREQUISITE entities. This implies that a course requires the course listed in Prerequisite Code to be completed before enrollment.

## Design Choices:
When selecting entities, relationships, and assumptions for a specific task or concept in Unreal Engine, I focus on the following key points:

Entities: These are the core components involved in the task. For example, when discussing Physical Material, I chose this entity because it directly relates to defining how objects behave in terms of physics—whether they are bouncy, slippery, or heavy. The material properties like friction and density are fundamental for interaction in a 3D environment.

Relationships: The relationship between entities is crucial for understanding how they interact with each other. For instance, Physical Material and surfaces/objects have a relationship where the material defines how an object behaves physically when it collides, slides, or interacts with other objects. This relationship helps define real-world-like interactions in a virtual scene.

Assumptions: Assumptions are used to simplify complex systems or to fill in gaps where more specific details aren't provided. For example, when selecting the impact of a Physical Material, I assumed that users might be looking for how it affects objects' physical interactions in the scene, as this is the primary function in Unreal Engine, which focuses on realistic simulations.

## RESULT
Those the ER DIAGRAM is implemented successfully
