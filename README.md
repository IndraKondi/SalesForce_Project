# EduConsultPro - Salesforce CRM for Educational Institutions 

![Salesforce](https://img.shields.io/badge/Salesforce-00A1E0?style=for-the-badge&logo=Salesforce&logoColor=white)

## Overview

EduConsultPro is a tailored **Salesforce CRM solution** designed specifically for educational institutions to streamline the student lifecycle—from inquiry and enrollment to ongoing support. This **centralized platform** efficiently manages courses, consultants, student data, appointments, and communication, enhancing both operations and user experience.

## Demonstration

[![EduConsultPro Demo](http://img.youtube.com/vi/yS1hyQzMzxI/0.jpg)](https://youtu.be/9bbJLQog14g "EduConsultPro Demonstration Video")

Watch the video above to explore EduConsultPro’s features and functionality in action.

## Key Features

* **Student Admission Management:**
    * Automated application process
    * Course selection and registration
    * Real-time email notifications
    * Student data management and tracking

* **Appointment Scheduling:**
    * Consultant booking system with approval workflows  
    * Automated email alerts for key stages  
    * Integrated calendar to manage appointments  

* **Case Management:**
    * Immigration and visa support tracking  
    * Student support ticketing system for query resolution  

* **Course Management:**
    * Comprehensive course catalog  
    * Track student enrollment and progress  

## Technical Architecture

### Custom Objects

* `Student`
* `Course`
* `Consultant`
* `Appointment`
* `Registration`

### Object Relationships

* `Appointment` → `Student` (Lookup)
* `Appointment` → `Consultant` (Lookup)
* `Registration` → `Student` (Lookup)
* `Registration` → `Course` (Lookup)
* `Student` → `Case` (Lookup)

### Automation

* **Flows:**
    * **Student Admission Flow:** Manages student information collection, course selection, registration, and notifications.
    * **Appointment Booking Flow:** Verifies student details, consultant availability, and handles approvals.
    * **Combined Master Flow:** Directs students (new/existing) to relevant processes in a unified interface.

* **Approval Processes:**  
    * Manager-based approval workflow for appointment requests, with email alerts for each status change.

* **Apex Triggers:**
    * **`StudentTrigger`:** Creates a welcome case upon student record creation to manage the onboarding process.  
    * **`AppointmentTrigger`:**  
        * **Before Insert/Update:** Ensures appointments are within business hours and consultants are available.  
        * **After Insert:** Sends email confirmations to students and consultants.

### User Interface

* **Lightning Components:**
    * Custom Lightning App: "EduConsultPro"  
    * Optimized Home Page layout for quick access  
    * Intuitive tab-based navigation  

## Setup Instructions

1. **Object Creation:**
    * Import `Course`, `Consultant`, and `Student` objects with relationships.
2. **User Configuration:**
    * Create users with the "Standard Platform User" profile.
    * Configure approval hierarchies for appointment workflows.
3. **Flow Deployment:**
    * Deploy the `Student Admission`, `Appointment Booking`, and `Master Flows`.
4. **Lightning App Setup:**
    * Deploy and configure the `EduConsultPro` Lightning App.
    * Assign user permissions for access and smooth navigation.

## Custom Settings

### Case Object Configuration

* **Type Field Values:** `Immigration`, `Visa Application`
* **Status Field Values:** `Open`, `In-Progress`, `Closed`

## Features in Detail

### Student Admission Process

1. Students complete the admission form.
2. Courses are selected and registered.
3. A registration record is automatically created.
4. Confirmation email is sent to the student.
5. Student information is saved and tracked in Salesforce.

### Appointment Management

1. System verifies student details.
2. Consultant availability is checked.
3. Appointment is scheduled accordingly.
4. Appointment request goes for approval.
5. Email notifications are sent at every step.

## System Requirements

* Salesforce Enterprise Edition or higher  
* System Administrator profile for setup  
* Standard Platform User licenses for end users  

## Author

**Kondi Indra Veerababu**  
Gayatri Vidya Parishad College of Engineering (A), Visakhapatnam  
Roll Number: 21131A0573  
Email: 21131A0573@gvpce.ac.in  

## License

This project is licensed under the **MIT License** - see the [LICENSE.md](LICENSE.md) file for details.

## Acknowledgments

* Gayatri Vidya Parishad College of Engineering  
* Salesforce Development Team  
* Project Mentors and Guides  

---

*Note: This README is part of an academic project demonstrating the use of Salesforce CRM for educational institutions.* 
