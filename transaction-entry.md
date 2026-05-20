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

The Transaction Entry feature allows authorized users to record new financial transactions — both income and expenses. Each entry captures key details such as amount, date, category, description, and an optional or required receipt upload for full accountability and audit trail compliance.

## Use Case Scenarios

### Scenario 1: Recording Income Transaction

| Use Case Name      | Recording Income Transaction                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Summary**        | The system allows users to input income transaction details including amount, date, category, description, and optional receipt upload.                                                                                                                                                                                                                                                                                  |
| **Preconditions**  | User is authenticated and authorized to create transactions. User has transaction details ready.                                                                                                                                                                                                                                                                                                                         |
| **Postconditions** | New income transaction is recorded in the system. Transaction appears in the Transaction Ledger. Activity log is updated with the new entry. Receipt is stored if uploaded.                                                                                                                                                                                                                                              |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to Transaction Entry page.<br>2. Select "Income" as transaction type.<br>3. Enter transaction details: amount, date, category (e.g., Student Fees, Event Revenue, Sponsorship), description, and payer/source.<br>4. Optionally upload receipt/proof of transaction (image or PDF).<br>5. Review entered information.<br>6. Submit the transaction.<br>7. View success confirmation. |
| **Exceptions**     | 1. If required fields are missing or invalid, the system displays an error message and highlights problematic fields.<br>2. If receipt upload fails, user can retry or proceed without receipt.                                                                                                                                                                                                                          |

---

### Scenario 2: Recording Expense Transaction

| Use Case Name      | Recording Expense Transaction                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows users to input expense transaction details with mandatory receipt upload for accountability.                                                                                                                                                                                                                                                                                                            |
| **Preconditions**  | User is authenticated and authorized to create transactions. User has transaction details and receipt ready.                                                                                                                                                                                                                                                                                                              |
| **Postconditions** | New expense transaction is recorded in the system. Transaction appears in the Transaction Ledger. Activity log is updated. Receipt is stored in the system.                                                                                                                                                                                                                                                               |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to Transaction Entry page.<br>2. Select "Expense" as transaction type.<br>3. Enter transaction details: amount, date, category (e.g., Event Expenses, Office Supplies, Honorarium), description, and payee/recipient.<br>4. Upload receipt/proof of payment (required for expenses).<br>5. Review entered information.<br>6. Submit the transaction.<br>7. View success confirmation. |
| **Exceptions**     | 1. If receipt is not uploaded for an expense, the system displays an error requiring receipt attachment.<br>2. If similar transaction exists (same amount, date, description), the system warns user of potential duplicate.                                                                                                                                                                                              |

---

### Scenario 3: Editing Transaction Entry

| Use Case Name      | Editing Transaction Entry                                                                                                                                                                                                                   |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to modify existing transaction details and update receipts.                                                                                                                                              |
| **Preconditions**  | User is authenticated with edit permissions. Transaction to be edited exists in the system.                                                                                                                                                 |
| **Postconditions** | Transaction is updated with new information. Change is recorded in activity log with timestamp and user ID. Updated transaction reflects in Transaction Ledger.                                                                             |
| **Basic Flow**     | **Actor Action**<br><br>1. Search for and select the transaction to edit.<br>2. View current transaction details.<br>3. Modify necessary fields.<br>4. Upload new receipt if needed.<br>5. Submit changes.<br>6. View success confirmation. |
| **Exceptions**     | 1. If validation fails on updated data, the system displays an error message.                                                                                                                                                               |

---

## Related Use Cases

- [Transaction Ledger](transaction-ledger.md)
- [Activity Monitoring](activity-monitoring.md)

---

<div align="center">© 2026 Tera IV</div>
