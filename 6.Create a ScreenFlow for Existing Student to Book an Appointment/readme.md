# Existing Student Appointment Booking Screen Flow

This document describes a Screen Flow designed for existing students to book appointments and optionally create cases.

## Flow Overview

The flow facilitates appointment booking for existing students, retrieving their information, allowing them to select a consultant and schedule an appointment.  It also includes a branching path for case creation, which requires further definition.

## Flow Components

1. **Screen Element (Get Student Info):**
    * Collects the existing student's name and email address.

2. **Get Records Element (Get Student Record):**
    * Retrieves the `Student` record that matches the entered name and email.
    * Stores the retrieved record in a record variable resource (e.g., `StudentRecord`).

3. **Screen Element (Choose Action):** *(This was implied but not explicitly mentioned in the original instructions)*
    * Presents the student with choices: "Book Appointment" or "Create Case."
    * Stores the selected choice in a variable (e.g., `ChosenAction`).

4. **Decision Element (Appointment or Case):**
    * Evaluates the value of the `ChosenAction` variable.
    * Creates two outcomes: "Book Appointment" and "Create Case."

5. **(Appointment Path)**

    * **Screen Element (Appointment Booking Screen):**
        * Displays fields from the `Appointment` object for the student to complete.
        * Uses a record variable resource (e.g., `AppointmentRecordRes`).

    * **Get Records Element (Get Consultant Record):**
        * Retrieves the `Consultant` record based on the selected consultant name.
        * Stores the retrieved record in a variable (e.g., `ConsultantRecord`).

    * **Create Records Element (Create Appointment):**
        * Creates an `Appointment` record using the details provided by the student and links it to the retrieved `Student` and `Consultant` records.

    * **Screen Element (Confirmation Screen):**
        * Displays a confirmation message with the appointment details.

6. **(Case Path)**

    * **Subflow Element (Create Student Case):**
        * This subflow handles the creation of a `Case` record related to the student.  The subflow should collect the necessary case details and create the `Case` record linked to the `Student` record.  **



## Flow Logic

The flow begins by gathering student information and retrieving the matching `Student` record.  It then presents the student with the choice to book an appointment or create a case.  Depending on the student's selection, the flow follows the appropriate path. The appointment booking path gathers appointment details, retrieves the consultant information, creates the appointment, and displays a confirmation. The case creation path utilizes a subflow to handle case creation.  This branching structure allows for flexibility and caters to different student needs within a single flow.
