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

[Project Homepage](README.md) > Transaction Ledger

---

# Transaction Ledger

The Transaction Ledger provides a complete, real-time display of all recorded financial transactions within the CLARO system. Authorized users can view, filter by date range or category, search for specific entries, and export the full transaction history for auditing and accountability purposes.

## Use Case Scenario

| Use Case Name      | Transaction Ledger                                                                                                                                                                                                                                                                                                                                                                          |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system performs a complete display of all recorded financial transactions, allowing users to view, filter, and export the transaction history.                                                                                                                                                                                                                                          |
| **Preconditions**  | User is authenticated and logged into the system. Transactions have been entered into the system.                                                                                                                                                                                                                                                                                           |
| **Postconditions** | Transaction ledger is displayed with all recorded entries. User has access to complete financial history.                                                                                                                                                                                                                                                                                   |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to the Transaction Ledger section.<br>2. View the complete transaction ledger showing transaction ID, date/time, type, amount, category, description, and user who entered the transaction.<br>3. Filter transactions by date range, type, or category if needed.<br>4. Search for specific transactions.<br>5. Export the ledger to CSV or PDF format. |
| **Exceptions**     | 1. If no transactions have been recorded, the system displays a message indicating the ledger is empty.                                                                                                                                                                                                                                                                                     |

---

## Related Use Cases

- [Transaction Entry](transaction-entry.md)
- [Financial Report Generation](financial-report-generation.md)

---

<div align="center">© 2026 Tera IV</div>
