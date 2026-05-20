# Clean Money

**Target:** CM.010.001 (or CM.020.001 for pre-completed projects)

| Revision Date | Document Version | Description                                                | Tracking Notes | Approved By                                  |
| ------------- | ---------------- | ---------------------------------------------------------- | -------------- | -------------------------------------------- |
| 2026-05-20    | v1.4             | Add dashboard, balance tracking, and activity logging docs | CM.010.005     | Concoles, Cyril Jade M.<br>_Test Lead_       |
| 2026-04-27    | v1.3             | Add reporting workflow, archives, and entries docs         | CM.010.004     | Montera, Mhac Alester B.<br>_Lead Developer_ |
| 2025-03-11    | v1.2             | Add admin controls, activity logs, and reports page docs   | CM.010.003     | Concoles, Cyril Jade M.<br>_Test Lead_       |
| 2025-03-02    | v1.1             | Add navigation, authentication, and sidebar docs           | CM.010.002     | Montera, Mhac Alester B.<br>_Lead Developer_ |
| 2025-02-13    | v1.0             | First document version                                     | CM.010.001     | Tan, Ron Nicolas J.<br>_Project Manager_     |
| ...           | ...              | ...                                                        | ...            | ...                                          |

**Site Map**

- [Project Homepage](README.md)
- [Account Balance Overview](account-balance-overview.md)
- [Transaction Ledger](transaction-ledger.md)
- [Transaction Entry](transaction-entry.md)
- [Activity Monitoring](activity-monitoring.md)
- [Public Financial Report](public-financial-report.md)
- [Financial Report Generation](financial-report-generation.md)

---

[Project Homepage](README.md) > Transaction Ledger

---

# Transaction Ledger

The Transaction Ledger consists of two tables on the Dashboard — Income Entries and Expense Entries — displaying all recorded financial transactions for the active semester. Authorized users can view entries, delete individual or multiple entries, and edit an entry's description. All write actions are locked once the semester report has been published or the semester has ended.

## Use Case Scenarios

### Scenario 1: Viewing Income and Expense Entries

| Use Case Name      | Viewing Income and Expense Entries                                                                                                                                                                                                                                                                          |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The Dashboard displays two side-by-side scrollable tables — Expense Entries on the left and Income Entries on the right — showing all entries recorded for the active semester.                                                                                                                             |
| **Preconditions**  | User is authenticated. An active semester exists and initial balance has been set.                                                                                                                                                                                                                          |
| **Postconditions** | User can see all income and expense entries for the current semester.                                                                                                                                                                                                                                       |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to the Dashboard.<br>2. View the Expense Entries table on the left and Income Entries table on the right.<br>3. Each table displays the following columns: #, Description, Unit Price, Quantity, Total, and Date.<br>4. Scroll within each table to browse all entries. |
| **Exceptions**     | 1. If no entries have been recorded yet, the table displays "No entries found."                                                                                                                                                                                                                             |

---

### Scenario 2: Deleting an Entry

| Use Case Name      | Deleting an Entry                                                                                                                                                                                                                                                                                                                                                                         |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to delete a single entry or multiple entries at once using select mode.                                                                                                                                                                                                                                                                                |
| **Preconditions**  | User is authenticated. The semester report has not been published and the semester has not ended.                                                                                                                                                                                                                                                                                         |
| **Postconditions** | Deleted entries are removed from the system. The balance overview and totals are refreshed.                                                                                                                                                                                                                                                                                               |
| **Basic Flow**     | **Actor Action**<br><br>**Individual delete:** Click the delete action on an entry row. The entry is removed immediately.<br><br>**Bulk delete:** 1. Click the "Select" button on the table header to enter select mode.<br>2. Check one or more entries using row checkboxes, or use the header checkbox to select all.<br>3. Click "Delete (n)" to remove all selected entries at once. |
| **Exceptions**     | 1. The Select and Delete buttons are hidden when the semester report is published or the semester has ended.                                                                                                                                                                                                                                                                              |

---

### Scenario 3: Editing an Entry

| Use Case Name      | Editing an Entry                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to modify the description of an existing entry. Category, date, unit price, and quantity are locked after an entry is created.                                                                                                                                                                                                                            |
| **Preconditions**  | User is authenticated. The semester report has not been published and the semester has not ended.                                                                                                                                                                                                                                                                                            |
| **Postconditions** | The entry's description is updated in the system. An activity log entry is recorded.                                                                                                                                                                                                                                                                                                         |
| **Basic Flow**     | **Actor Action**<br><br>1. Click the edit action on an entry row.<br>2. The Entry sheet opens in edit mode showing the entry's control number and description fields.<br>3. Modify the description as needed (category, date, price, and quantity fields are read-only in edit mode).<br>4. Click "Save Changes".<br>5. The entry is updated and the change is recorded in the activity log. |
| **Exceptions**     | 1. If the description field is empty, the system highlights it and prevents saving.<br>2. The edit action is hidden when the semester report is published or the semester has ended.                                                                                                                                                                                                         |

---

## Related Use Cases

- [Transaction Entry](transaction-entry.md)
- [Financial Report Generation](financial-report-generation.md)

---

<div align="center">© 2026 Tera IV</div>
