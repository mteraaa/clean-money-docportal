# Clean Money

**Target:** CL.010.001 (or CL.020.001 for pre-completed projects)

| Revision Date | Document Version | Description                                                    | Tracking Notes | Approved By                                          |
| ------------- | ---------------- | -------------------------------------------------------------- | -------------- | ---------------------------------------------------- |
| 2026-05-20    | v1.4             | Add dashboard, balance tracking, and activity logging docs     | CM.010.005     | Concoles, Cyril Jade M.<br>_Test Lead_               |
| 2026-04-27    | v1.3             | Add reporting workflow, archives, and entries docs             | CM.010.004     | Montera, Mhac Alester B.<br>_Lead Developer_         |
| 2025-03-11    | v1.2             | Add admin controls, activity logs, and reports page docs       | CM.010.003     | Concoles, Cyril Jade M.<br>_Test Lead_               |
| 2025-03-02    | v1.1             | Add navigation, authentication, and sidebar docs               | CM.010.002     | Montera, Mhac Alester B.<br>_Lead Developer_         |
| 2025-02-13    | v1.0             | First document version                                         | CM.010.001     | Tan, Ron Nicolas J.<br>_Project Manager_             |
| ...           | ...              | ...                                                            | ...            | ...                                                  |

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

The Activity Monitoring module displays a chronological log of all recorded system actions for the user's organization. The Activity Logs page shows the most recent 200 entries, each with a description, time, and date. Logs are scoped to the user's faculty or campus organization and are recorded automatically by the system whenever key actions are performed.

## Use Case Scenarios

### Scenario 1: Viewing the Activity Log

| Use Case Name      | Viewing the Activity Log                                                                                                                                                                                                                                 |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system displays a table of the 200 most recent activity log entries for the user's organization, ordered from most recent to oldest.                                                                                                                 |
| **Preconditions**  | User is authenticated.                                                                                                                                                                                                                                   |
| **Postconditions** | The user can review recent system activity for their organization.                                                                                                                                                                                       |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to the Activity Logs page from the sidebar.<br>2. View the activity log table with columns: Description, Time, and Date.<br>3. Entries are ordered by most recent first.<br>4. On smaller screens, the Time and Date columns are collapsed and shown inline under the Description. |
| **Exceptions**     | 1. If no activity has been recorded yet, the table displays "No activity recorded yet."                                                                                                                                                                  |

---

### Scenario 2: Automatic Logging on Entry Creation

| Use Case Name      | Automatic Logging on Entry Creation                                                                                                                                                                                                     |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system automatically records an activity log entry whenever a new income or expense transaction is added.                                                                                                                           |
| **Preconditions**  | User is authenticated and submits a new entry through the Add Entry sheet.                                                                                                                                                               |
| **Postconditions** | An activity log entry is created with a description in the format: "Added ₱[amount] to Income/Expenses for [description]".                                                                                                             |
| **Basic Flow**     | **Actor Action**<br><br>1. User saves a new entry via the Add Entry sheet.<br>2. The system inserts the entry into the database.<br>3. The system automatically records an activity log with the entry amount, category, and description.<br>4. The log appears on the Activity Logs page. |
| **Exceptions**     | None.                                                                                                                                                                                                                                   |

---

### Scenario 3: Automatic Logging on Balance Updates

| Use Case Name      | Automatic Logging on Balance Updates                                                                                                                                                                                                                                                                         |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Summary**        | The system automatically records an activity log entry whenever a balance action is performed, including bank deposits, withdrawals, interest additions, and collectibles additions.                                                                                                                         |
| **Preconditions**  | User is authenticated and performs a balance action from the Dashboard balance cards.                                                                                                                                                                                                                        |
| **Postconditions** | An activity log entry is created describing the specific action and amount. The log appears on the Activity Logs page.                                                                                                                                                                                       |
| **Basic Flow**     | **Actor Action**<br><br>The system logs the following actions automatically:<br>- **Deposit:** "Deposited ₱[amount] to Cash on Bank"<br>- **Withdrawal:** "Withdrew ₱[amount] from Cash on Bank"<br>- **Interest:** "Added ₱[amount] Interest Earnings to Cash on Bank"<br>- **Collectibles:** "Added ₱[amount] to Collectibles"<br>- **Fines to Collectibles:** "Added ₱[amount] to Collectibles" (from fines transfer) |
| **Exceptions**     | 1. If a balance action is undone, the corresponding activity log entry is deleted from the database.                                                                                                                                                                                                         |

---

## Related Use Cases

- [Transaction Entry](transaction-entry.md)
- [Account Balance Overview](account-balance-overview.md)

---

<div align="center">© 2026 Tera IV</div>
