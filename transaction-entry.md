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

[Project Homepage](README.md) > Transaction Entry

---

# Transaction Entry

The Transaction Entry feature allows authorized users to record new financial transactions through a slide-in entry sheet. Each entry captures a control number (auto-generated), category, description, date, unit price, and quantity. Multiple entries can be submitted in a single session. Receipt uploads are available for expense entries. All entry actions are locked once the semester report has been published or the semester has ended.

## Use Case Scenarios

### Scenario 1: Adding a New Entry

| Use Case Name      | Adding a New Entry                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to record a new income or expense transaction by filling in entry details in the Add Entry sheet.                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Preconditions**  | User is authenticated. An active semester exists. The semester report has not been published and the semester has not ended.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Postconditions** | The new entry is saved to the system. The Income or Expense Entries table is refreshed. The balance overview is updated. An activity log entry is recorded.                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Basic Flow**     | **Actor Action**<br><br>1. Click the "Add Entry" button on the Dashboard.<br>2. The Add Entry sheet opens.<br>3. Select Category: **Income** or **Expense**.<br>4. Select a Description from the preset dropdown:<br>&nbsp;&nbsp;- **Income:** Membership Fee, Donations, Fines, Collectibles, Special Projects/Fund Raising, Others<br>&nbsp;&nbsp;- **Expense:** Special Projects/Fund Raising, Reimbursement, Others<br>5. If "Others" is selected, type a custom description. If expense "Special Projects/Fund Raising" is selected, enter a project name. If "Reimbursement" is selected, enter a payee name and description.<br>6. Select a date using the calendar picker.<br>7. Enter the Unit Price (₱) and Quantity. The Total is computed automatically (Unit Price × Quantity).<br>8. For expense entries, optionally upload a receipt (image or PDF) and enter a receipt number.<br>9. Click "Save". The entry is recorded and a success toast is shown. |
| **Exceptions**     | 1. If required fields (Category, Description, Date, Unit Price, Quantity) are missing, the system highlights them in red and prevents saving.<br>2. If Category has not been selected, the Description dropdown is disabled.                                                                                                                                                                                                                                                                                                                                                                                    |

---

### Scenario 2: Adding Multiple Entries at Once

| Use Case Name      | Adding Multiple Entries at Once                                                                                                                                                                                                                                 |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to add more than one entry in a single session before saving, with each entry assigned its own auto-incremented control number.                                                                                              |
| **Preconditions**  | User is authenticated. The Add Entry sheet is open in add mode.                                                                                                                                                                                                  |
| **Postconditions** | All entries in the batch are saved. The control number counter is incremented separately for income and expense entries. The entries tables and balance overview are refreshed.                                                                                  |
| **Basic Flow**     | **Actor Action**<br><br>1. Fill in the first entry form as described in Scenario 1.<br>2. Click "Add Another Entry" at the bottom of the sheet.<br>3. A new blank entry form appears. Each form's control number auto-increments based on the category (income and expense control numbers are tracked separately).<br>4. Fill in additional entry forms as needed.<br>5. Click "Save" to submit all entries at once. |
| **Exceptions**     | 1. If any entry in the batch fails validation, the system highlights the invalid fields and prevents saving the entire batch.<br>2. Individual entries in the batch can be removed by clicking "Remove" on that entry's form.                                    |

---

### Scenario 3: Editing an Existing Entry

| Use Case Name      | Editing an Existing Entry                                                                                                                                                                                                                                                                |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to update the description of an existing entry. Category, date, unit price, and quantity cannot be changed after the entry is created.                                                                                                               |
| **Preconditions**  | User is authenticated. The semester report has not been published and the semester has not ended.                                                                                                                                                                                        |
| **Postconditions** | The entry's description is updated. An activity log entry is recorded.                                                                                                                                                                                                                  |
| **Basic Flow**     | **Actor Action**<br><br>1. Click the edit action on an entry row in the Income or Expense Entries table.<br>2. The Entry sheet opens in edit mode. The control number, category, date, unit price, and quantity fields are read-only.<br>3. Modify the Description fields (preset and/or custom text) as needed.<br>4. Click "Save Changes".<br>5. The entry is updated in the system and the change is recorded in the activity log. |
| **Exceptions**     | 1. If the description field is left empty, the system highlights it and prevents saving.                                                                                                                                                                                                 |

---

## Related Use Cases

- [Transaction Ledger](transaction-ledger.md)
- [Activity Monitoring](activity-monitoring.md)

---

<div align="center">© 2026 Tera IV</div>
