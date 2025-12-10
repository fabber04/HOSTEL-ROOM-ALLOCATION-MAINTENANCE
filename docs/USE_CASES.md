# Use Cases Document
## Hostel Room Allocation and Maintenance Management System

## 1. Introduction

This document describes the use cases for the Hostel Room Allocation and Maintenance Management System. Use cases define the interactions between users (actors) and the system.

## 2. Actors

### 2.1 Primary Actors
- **Student**: End user who requests rooms and submits maintenance requests
- **Staff/Warden**: Administrator who allocates rooms and manages maintenance work orders

### 2.2 Secondary Actors
- **System**: Automated processes and notifications

## 3. Use Cases

### UC-1: Student Requests Room Allocation

**Actor**: Student  
**Preconditions**: Student is logged into the system  
**Main Flow**:
1. Student navigates to "Request Room" page
2. Student selects preferred hostel
3. Student selects room type (Single/Double/Triple/Quad)
4. Student selects semester
5. Student optionally adds special requirements
6. Student submits the request
7. System displays confirmation message
8. System redirects to status page showing "Pending" status

**Alternative Flow**:
- 3a. If required fields are missing, system displays error message
- 3b. Student corrects errors and resubmits

**Postconditions**: Room request is created with "Pending" status

---

### UC-2: Student Views Room Allocation Status

**Actor**: Student  
**Preconditions**: Student has submitted a room request  
**Main Flow**:
1. Student navigates to "My Status" page
2. System displays current request status
3. Student can see:
   - Request details (hostel, room type, semester)
   - Current status (Pending/Allocated/Rejected)
   - Allocation date (if allocated)
   - Room number (if allocated)

**Alternative Flow**:
- 2a. If no request exists, system displays "No active requests"

**Postconditions**: Student is informed of their request status

---

### UC-3: Staff Allocates Room to Student

**Actor**: Staff/Warden  
**Preconditions**: Staff is logged in and pending requests exist  
**Main Flow**:
1. Staff navigates to "Allocate Room" page
2. System displays list of pending room requests
3. Staff reviews request details (student ID, hostel, room type, semester)
4. Staff clicks "Allocate" button for a request
5. System displays success modal
6. System updates request status to "Allocated"
7. System notifies student (simulated in prototype)

**Alternative Flow**:
- 4a. If no rooms available, staff can reject the request
- 4b. System updates status to "Rejected" and notifies student

**Postconditions**: Room is allocated to student, status updated

---

### UC-4: Student Submits Maintenance Request

**Actor**: Student  
**Preconditions**: Student is logged in  
**Main Flow**:
1. Student navigates to "Maintenance" page
2. Student selects maintenance category (Plumbing/Electrical/HVAC/Furniture/Other)
3. Student enters description of the issue
4. Student selects urgency level (Low/Medium/High/Urgent)
5. Student optionally specifies room number
6. Student submits the request
7. System displays confirmation message
8. System creates maintenance ticket with "Open" status

**Alternative Flow**:
- 2a. If required fields are missing, system displays error
- 2b. Student corrects and resubmits

**Postconditions**: Maintenance request is created and visible to staff

---

### UC-5: Staff Views Maintenance Work Orders

**Actor**: Staff/Warden  
**Preconditions**: Staff is logged in  
**Main Flow**:
1. Staff navigates to "Work Orders" page
2. System displays list of all maintenance requests
3. Staff can see:
   - Request ID
   - Student information
   - Category and description
   - Urgency level
   - Current status
   - Date submitted

**Postconditions**: Staff has overview of all maintenance requests

---

### UC-6: Staff Updates Maintenance Work Order Status

**Actor**: Staff/Warden  
**Preconditions**: Staff is viewing work orders page  
**Main Flow**:
1. Staff selects a maintenance request
2. Staff updates status (Open → In Progress → Completed)
3. Staff optionally adds notes
4. Staff saves changes
5. System updates the work order status
6. System notifies student of status change (simulated)

**Alternative Flow**:
- 2a. Staff can assign request to a technician
- 2b. Staff can add internal notes not visible to student

**Postconditions**: Work order status is updated

---

### UC-7: Student Views Dashboard

**Actor**: Student  
**Preconditions**: Student is logged in  
**Main Flow**:
1. Student navigates to dashboard
2. System displays:
   - Welcome message
   - Quick action buttons (Request Room, View Status)
   - Recent activity summary
   - Current allocation status (if any)

**Postconditions**: Student has overview of their account status

---

### UC-8: Staff Views Dashboard

**Actor**: Staff/Warden  
**Preconditions**: Staff is logged in  
**Main Flow**:
1. Staff navigates to dashboard
2. System displays:
   - Overview of pending allocations
   - Overview of open maintenance requests
   - Quick navigation to key functions
   - Summary statistics

**Postconditions**: Staff has overview of system status

---

## 4. Use Case Diagram

```
                    ┌─────────┐
                    │ Student │
                    └────┬────┘
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
   [Request Room]  [View Status]  [Submit Maintenance]
        │                │                │
        └────────────────┼────────────────┘
                         │
                    ┌────┴────┐
                    │ System │
                    └────┬────┘
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
   [Allocate Room]  [View Work Orders]  [Update Status]
        │                │                │
        └────────────────┼────────────────┘
                         │
                    ┌────┴────┐
                    │  Staff │
                    └─────────┘
```

## 5. Non-Functional Requirements

### 5.1 Usability
- All use cases should be completable by first-time users without training
- Interface should be intuitive and self-explanatory
- Error messages should be clear and actionable

### 5.2 Performance
- Page load time should be under 2 seconds
- Form submissions should provide immediate feedback
- Status updates should be visible in real-time

### 5.3 Accessibility
- Sufficient color contrast for readability
- Keyboard navigation support
- Screen reader compatibility (future implementation)

## 6. Future Use Cases

1. **Room Swapping**: Students can request to swap rooms
2. **Waitlist Management**: Automatic waitlist when rooms are full
3. **Automated Allocation**: System automatically allocates based on rules
4. **Payment Integration**: Handle accommodation fees
5. **Reporting**: Generate allocation and maintenance reports
6. **Notifications**: Email/SMS notifications for status changes
7. **Multi-semester Planning**: Plan room allocations for multiple semesters

---

**Document Version**: 1.0  
**Last Updated**: December 10, 2025  
**Author**: Software Engineering Team

