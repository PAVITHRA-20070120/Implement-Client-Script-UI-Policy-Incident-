# ServiceNow Incident – Client Scripts & UI Policies

## Project Overview

This project demonstrates the implementation of **Client Scripts and UI Policies** in the **ServiceNow Incident Management** module.

The configuration dynamically controls Incident form behavior based on user actions and Incident conditions, helping to improve data accuracy and consistency.

## Objectives

- Implement UI Policies for the Incident table.
- Dynamically control form fields based on Incident conditions.
- Automatically set Urgency for High Impact Incidents.
- Ensure Assigned To is provided before saving High Impact Incidents.
- Prevent State changes through list editing.
- Test and verify the implemented configurations.

## Features Implemented

### High Impact Control – UI Policy

A UI Policy named **High Impact Control** was created for the Incident table.

- **Table:** Incident
- **Condition:** Impact is High
- **Reverse if false:** Enabled

When the condition is no longer satisfied, the applied field controls are automatically reverted.

### Urgency Field Control

A **UI Policy Action** was configured for the Urgency field.

When Impact is High:

- Urgency becomes **Read-only**.
- Users cannot manually modify the Urgency value.

### Automatic Urgency Update

An **onChange Client Script** was created for the Impact field.

When Impact is changed to High:

- Urgency is automatically set to **High**.
- An informational message is displayed to the user.

### Assigned To Validation

An **onSubmit Client Script** was implemented to validate the Assigned To field.

For High Impact Incidents:

- Assigned To must be provided.
- The Incident cannot be saved when Assigned To is empty.
- An error message is displayed to the user.

### State Change Restriction

An **onCellEdit Client Script** was implemented for the State field.

When a user attempts to change the Incident State directly from the list view:

- The update is blocked.
- A warning message is displayed.
- The user is instructed to open the Incident record for updating.

## Testing

The implemented configurations were tested using the following scenarios:

| Test Scenario | Result |
|---|---|
| High Impact Incident field behavior | Pass |
| Automatic Urgency update | Pass |
| Assigned To validation | Pass |
| Successful Incident save | Pass |
| UI Policy reverse condition | Pass |
| State list-edit blocking | Pass |
| Form-based Incident update | Pass |

All configured behaviors were successfully verified in the ServiceNow instance.

## Technologies Used

- ServiceNow Incident Management
- Client Scripts
- UI Policies
- UI Policy Actions
- JavaScript
- GitHub

## Screenshots

Screenshots of the ServiceNow configuration and testing results are included in this repository as project evidence.

## Conclusion

The project successfully demonstrates the use of **ServiceNow Client Scripts and UI Policies** to improve Incident form behavior, enforce validation rules, automate field updates, and prevent incorrect data entry.

The implemented solution provides better control, validation, and consistency in **ServiceNow Incident Management**.
