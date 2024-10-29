# Combined Master Flow

This document describes a Screen Flow that serves as a central entry point, combining the New Student Admission and Existing Student Appointment Booking flows.

## Flow Overview

The Combined Master Flow acts as a dispatcher, directing users to the appropriate subflow based on their status (new or existing student). This provides a unified user experience and simplifies navigation.

## Flow Components

1. **Screen Element (Welcome Screen):**
    * Displays a welcome message to the user.

2. **Screen Element (Existing or New Student Confirmation Screen):**
    * Asks the user if they are an existing student (e.g., using a radio button or checkbox).

3. **Decision Element (Decision 1):**
    * Evaluates the user's input from the previous screen.
    * Creates two outcomes: "Existing Student" and "New Student."

4. **Subflow Element (Existing Student Flow):**
    * This subflow element is executed if the "Existing Student" outcome is chosen.
    * Calls the **Existing Student Appointment Booking flow** (described in a previous response).

5. **Subflow Element (New Student Flow):**
    * This subflow element is executed if the "New Student" outcome is chosen.
    * Calls the **Student Admission Application flow** (described in a previous response).


## Flow Logic

The flow starts with a welcome message and then prompts the user to identify themselves as either a new or existing student. Based on their selection, the corresponding subflow is invoked. This centralized approach streamlines the user experience by presenting a single entry point for all student-related processes.


## Benefits of Using a Master Flow

* **Unified User Experience:** Provides a single starting point for all student-related processes.
* **Improved Navigation:** Simplifies access to different functionalities.
* **Easy Maintenance:**  Changes to individual subflows are automatically reflected in the master flow.
* **Enhanced Scalability:**  New functionalities can be added as subflows without modifying the master flow's core logic.
