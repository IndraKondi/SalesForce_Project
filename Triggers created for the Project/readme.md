## Apex Triggers

Apex triggers are used to automate processes and enforce business logic within EduConsultPro. They are crucial for maintaining data integrity and streamlining workflows related to student and appointment management.  The following triggers are implemented:

### `StudentTrigger`

This trigger is executed after a new `Student__c` record is inserted. Its primary function is to automatically create a welcome case for each new student. This welcome case serves as a starting point for tracking the student's onboarding process and ensures that each new student receives appropriate follow-up.

**Functionality:**

1. **Case Creation:** Upon insertion of a new `Student__c` record, the trigger creates a new `Case` record.
2. **Case Details:** The case is populated with relevant information, including:
    * Subject: "Welcome to EduConsultPro"
    * Description: A welcome message and information about onboarding.
    * Status: "Open"
    * Origin: "New Student Registration"
    * Priority: "Normal"
    * Contact Email: The student's email address.
    * Student Lookup: A lookup relationship to the newly created `Student__c` record.
3. **Error Handling:**  The trigger includes error handling to catch potential `DMLException` errors during case insertion. If an error occurs, an error message is added to the `Student__c` record.

### `AppointmentTrigger`

This trigger is associated with the `Appointment__c` object and is executed before insert and update operations, as well as after insert operations.  It handles appointment validation and notification logic.

**Functionality:**

**Before Insert and Update:**

1. **Business Hours Validation:** Checks if the appointment's scheduled time falls within business hours (9 AM to 5 PM). If the appointment is outside these hours, an error message is displayed.
2. **Consultant Availability Check:**  Verifies that the selected consultant is not already booked for another appointment at the same time.  This check is performed both during the initial insertion of an appointment and when the consultant, date, or time of an existing appointment is updated.  If a conflict is found, an error message is displayed.


**After Insert:**

1. **Email Notifications:**  After a new `Appointment__c` record is successfully inserted, the trigger sends email notifications to both the student and the consultant.
2. **Email Content:** The emails include the appointment date and time.
3. **Error Handling:** The trigger includes error handling to manage potential exceptions during email sending.  Error messages are logged for debugging purposes.


These triggers are designed with bulkification in mind to handle multiple records efficiently.  They are also implemented with error handling to ensure data integrity and provide informative feedback to users.  Comprehensive unit tests are in place to validate the functionality and ensure code coverage.