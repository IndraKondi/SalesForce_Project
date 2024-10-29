
# Appointment Approval Process

This document details the configuration of the approval process for the `Appointment` object.

## Email Templates

Before configuring the approval process, email templates were created for the following stages:

* **Submission:**  This email notifies the submitter and the approver that the appointment request has been submitted.
* **Approval:** This email notifies the submitter that the appointment has been approved.
* **Rejection:** This email notifies the submitter that the appointment has been rejected.  It may also include the reason for rejection.


## Approval Process Configuration

The approval process for the `Appointment` object was configured with the following settings:

* **Approver:** The manager of the user submitting the appointment request is designated as the approver. This leverages the user hierarchy within Salesforce.

* **Record Editability:**
    * **During Approval Process:** Record editability is restricted.  Only administrators and the assigned approver can edit the `Appointment` record during the approval process. This maintains data integrity and prevents unauthorized modifications.

* **Approval Actions:** The following actions are configured for different stages of the approval process:

    * **Initial Submission Actions:**  Update the `Appointment` record status (e.g., to "Pending Approval") and send the "Submission" email notification.
    * **Final Approval Actions:** Update the `Appointment` record status (e.g., to "Approved") and send the "Approval" email notification.
    * **Final Rejection Actions:** Update the `Appointment` record status (e.g., to "Rejected") and send the "Rejection" email notification.


This configuration ensures a structured and controlled approval process for appointments, with clear communication at each stage.  The use of email templates keeps all parties informed and provides a record of the approval history.
