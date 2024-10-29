# EduConsultPro - Salesforce CRM Setup

This document outlines the setup process for the EduConsultPro Salesforce CRM solution.

## Object Creation

### Importing Objects from Spreadsheets

* **Course Object:**  A custom object named "Course" was created using the data provided in the 'Course' spreadsheet. Spreadsheet columns were mapped to corresponding Salesforce fields in the `Course` object.

* **Remaining Objects:**  Similar to the `Course` object, custom objects were created for `Consultant`, `Student`, `Appointment`, and `Registration` using their respective spreadsheets.  Careful field mapping ensured data integrity during the import process.

### Establishing Object Relationships

Lookup relationships were established to connect related data:

* **Appointment Object:**
    * `Appointment` → `Student` (Student lookup field)
    * `Appointment` → `Consultant` (Consultant lookup field)

* **Registration Object:**
    * A custom object, `Registration`, was created to store student and course details.
    * `Registration` → `Student` (Student lookup field)
    * `Registration` → `Course` (Course lookup field)

* **Student and Case:**
    * `Student` → `Case` (Case lookup field)


## Case Object Configuration

The standard `Case` object was configured with custom picklist values:

* **Type Field:**
    * `Immigration`
    * `Visa Application`

* **Status Field:**
    * `Open`
    * `In-Progress`
    * `Closed` (recommended for completeness)



## Lightning App Creation

A Lightning App named "EduConsultPro" was created to centralize access to all functionalities.  The app includes the following tabs:

* Home
* Students
* Courses
* Consultants
* Appointments
* Registrations
* Cases


The `EduConsultPro` app is accessible to users with the System Administrator profile.
