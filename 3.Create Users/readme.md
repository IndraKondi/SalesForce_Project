
# Student Admission Application Screen Flow

This document details the structure and components of the Student Admission Application Screen Flow.

## Flow Overview

The flow automates the student admission process, collecting student information, allowing course selection, creating necessary records, and sending a confirmation email.

## Flow Components

1. **Screen Element (Student Info):**
    * Collects student information using fields from the `Student` object.
    * Utilizes a record variable resource: `StudentRecordRes`.

2. **Create Records Element (Create Student Record):**
    * Creates a new `Student` record using the data collected from the "Student Info" screen.
    * Stores the newly created record in the `StudentRecordRes` variable.

3. **Screen Element (Course Screen):**
    * Presents a picklist for course selection (IELTS, GRE, GMAT, Duolingo, TOEFL).
    * Uses choice variables for each course option (e.g., `SelectedIELTS`, `SelectedGRE`, etc.).

4. **Decision Element (Selecting Course):**
    * Evaluates the selected course from the "Course Screen."
    * Routes the flow based on the selected course.
    * Defines outcomes for each course option (e.g., "Selected IELTS," "Selected GRE," etc.).

5. **Get Records Element (Retrieve Course Record):**
    * For each course outcome (e.g., "Selected IELTS"), a Get Records element retrieves the corresponding `Course` record based on the selected course name.

6. **Create Records Element (Create Registration Record):**
    * For each course outcome path, this element creates a `Registration` record.
    * Links the newly created `Student` record (from `StudentRecordRes`) and the retrieved `Course` record.

7. **Text Template Resources (Email Templates):**
    * Two text template resources are created:
        * `StuRegistrationEmailTextTempBody`:  Contains the email body content.
        * `StuRegistrationEmailTextTempSub`: Contains the email subject.


8. **Action Element (Send Email to Student):**
    * Sends a registration confirmation email to the student using an Email Alert action.
    * Utilizes the email templates: `StuRegistrationEmailTextTempBody` and `StuRegistrationEmailTextTempSub`.

9. **Screen Element (Success Screen):**
    * Displays a success message to the student upon completion of the flow.


## Flow Logic

The flow follows a linear path until the "Selecting Course" decision element. From there, it branches based on the selected course, retrieving the appropriate course record and creating the corresponding registration.  Finally, a confirmation email is sent, and a success message is displayed.


This structured approach ensures a smooth and efficient student admission application process.
