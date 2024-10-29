# Appointment Record-Triggered Flow

This document describes the configuration of a record-triggered flow that automates the appointment submission process.

## Flow Trigger

The flow is configured as a record-triggered flow with the following trigger settings:

* **Object:** `Appointment`
* **Trigger Event:**  A record is created.
* **Entry Conditions:**  No specific entry conditions are defined, meaning the flow runs every time a new `Appointment` record is created.


## Flow Components

The flow consists of the following components:

1. **Start Element:** Configured to trigger when an `Appointment` record is created.

2. **Action Element (Submit for Approval):**
    * This action element utilizes the "Submit for Approval" core action.
    * It automatically submits the newly created `Appointment` record for approval.
    * This action integrates with the previously configured approval process, routing the request to the assigned approver (the submitting user's manager).



## Flow Logic

The flow's logic is straightforward: whenever a new `Appointment` record is created, the flow triggers and immediately submits the record for approval. This automation streamlines the appointment scheduling process and eliminates the need for manual submission.
