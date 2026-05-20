# Clean Money

**Target:** CL.010.001 (or CL.020.001 for pre-completed projects)

| Revision Date | Document Version | Description            | Tracking Notes | Approved By                           |
| ------------- | ---------------- | ---------------------- | -------------- | ------------------------------------- |
| 2025-02-13    | v1.0             | First document version | CL.010.001     | Tan, Ron Nicolas<br>_Project Manager_ |
| ...           | ...              | ...                    | ...            | ...                                   |

**Site Map**

- [Project Homepage](README.md)
- [Account Balance Overview](account-balance-overview.md)
- [Transaction Ledger](transaction-ledger.md)
- [Transaction Entry](transaction-entry.md)
- [Activity Monitoring](activity-monitoring.md)
- [Public Financial Report](public-financial-report.md)
- [Financial Report Generation](financial-report-generation.md)

---

[Project Homepage](README.md) > Activity Monitoring

---

# Activity Monitoring

The Activity Monitoring module automatically records and displays a comprehensive log of all user actions within the CLARO system, including logins, logouts, transaction entries, and modifications. It enables administrators to review system usage, maintain accountability, and detect suspicious behavior.

## Use Case Scenarios

### Scenario 1: Viewing User Activity Logs

| Use Case Name      | Viewing User Activity Logs                                                                                                                                                                                                                                                                                                                    |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system displays all recorded user activities including login/logout, transaction entries, and modifications for audit purposes.                                                                                                                                                                                                           |
| **Preconditions**  | User is authenticated with administrative privileges. Activity logs exist in the system.                                                                                                                                                                                                                                                      |
| **Postconditions** | Complete activity history is displayed. User has visibility into all system activities for accountability.                                                                                                                                                                                                                                    |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to Activity Monitoring page.<br>2. View activity log table showing timestamp, user ID/username, activity type, activity details, and IP address.<br>3. Filter activities by date range, user, or activity type if needed.<br>4. Search for specific activities.<br>5. Export activity logs to CSV or PDF. |
| **Exceptions**     | 1. If filter criteria returns no results, the system displays "No activities found" message.                                                                                                                                                                                                                                                  |

---

### Scenario 2: Automatic Activity Logging on Login

| Use Case Name      | Automatic Activity Logging on Login                                                                                                                                                                                                                                     |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system automatically records user login activity with timestamp and IP address for security tracking.                                                                                                                                                               |
| **Preconditions**  | User has valid credentials.                                                                                                                                                                                                                                             |
| **Postconditions** | Login activity is recorded in activity log. User session is active.                                                                                                                                                                                                     |
| **Basic Flow**     | **Actor Action**<br><br>1. Enter username and password.<br>2. System validates and authenticates successfully.<br>3. System automatically records login activity with user ID, timestamp, activity type "Login", and IP address.<br>4. User is redirected to dashboard. |
| **Exceptions**     | None.                                                                                                                                                                                                                                                                   |

---

### Scenario 3: Automatic Activity Logging on Logout

| Use Case Name      | Automatic Activity Logging on Logout                                                                                                                                                            |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system automatically records user logout activity for session tracking.                                                                                                                     |
| **Preconditions**  | User is currently logged in.                                                                                                                                                                    |
| **Postconditions** | Logout activity is recorded in activity log. User session is terminated.                                                                                                                        |
| **Basic Flow**     | **Actor Action**<br><br>1. Click logout button.<br>2. System automatically records logout activity with user ID, timestamp, and activity type "Logout".<br>3. User is redirected to login page. |
| **Exceptions**     | None.                                                                                                                                                                                           |

---

### Scenario 4: Automatic Activity Logging on Transaction Entry

| Use Case Name      | Automatic Activity Logging on Transaction Entry                                                                                                                                                                                                                       |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system automatically records when transactions are created for audit trail purposes.                                                                                                                                                                              |
| **Preconditions**  | User is authenticated and creating a transaction.                                                                                                                                                                                                                     |
| **Postconditions** | Transaction entry activity is recorded. Activity log is updated with transaction creation details.                                                                                                                                                                    |
| **Basic Flow**     | **Actor Action**<br><br>1. Submit a new transaction.<br>2. System saves the transaction successfully.<br>3. System automatically records activity with user ID, timestamp, activity type "Transaction Entry", and details including transaction ID, type, and amount. |
| **Exceptions**     | None.                                                                                                                                                                                                                                                                 |

---

### Scenario 5: Automatic Activity Logging on Transaction Modification

| Use Case Name      | Automatic Activity Logging on Transaction Modification                                                                                                                                                                                                                                                          |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system automatically records transaction modifications with details of changed fields for complete audit trail.                                                                                                                                                                                             |
| **Preconditions**  | User is authenticated and editing an existing transaction.                                                                                                                                                                                                                                                      |
| **Postconditions** | Transaction modification activity is recorded. Activity log contains complete audit trail of changes.                                                                                                                                                                                                           |
| **Basic Flow**     | **Actor Action**<br><br>1. Modify an existing transaction.<br>2. System updates the transaction successfully.<br>3. System automatically records activity with user ID, timestamp, activity type "Transaction Modification", and details including transaction ID, fields modified, old values, and new values. |
| **Exceptions**     | None.                                                                                                                                                                                                                                                                                                           |

---

### Scenario 6: Detecting Suspicious Activity

| Use Case Name      | Detecting Suspicious Activity                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Summary**        | The system monitors activity logs for suspicious patterns and flags them for administrator review.                                                                                                                                                                                                                                                                                               |
| **Preconditions**  | Activity monitoring system is active. Unusual patterns are detected.                                                                                                                                                                                                                                                                                                                             |
| **Postconditions** | Suspicious activities are identified and flagged. Administrator is alerted to potential security issues.                                                                                                                                                                                                                                                                                         |
| **Basic Flow**     | **Actor Action**<br><br>1. System continuously monitors activity logs.<br>2. System detects suspicious patterns (multiple failed login attempts, unusual transaction modifications, access attempts outside normal hours).<br>3. System flags suspicious activities in the activity log.<br>4. Administrator reviews flagged activities.<br>5. Administrator takes appropriate action if needed. |
| **Exceptions**     | None.                                                                                                                                                                                                                                                                                                                                                                                            |

---

## Related Use Cases

- [Transaction Entry](transaction-entry.md)
- [Authentication](authentication.md) _(if applicable)_

---

<div align="center">© 2026 Tera IV</div>
