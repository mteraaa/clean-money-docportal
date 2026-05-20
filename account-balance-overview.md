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

[Project Homepage](README.md) > Account Balance Overview

---

# Account Balance Overview

The Account Balance Overview is displayed on the Dashboard and shows the organization's current financial position through a set of balance cards: Total Balance, Cash On-Bank, Cash On-Hand, Collectibles, and Fines. The Total Balance equals Cash On-Bank plus Cash On-Hand. Authorized users can perform bank deposits, withdrawals, interest additions, and collectibles updates directly from the cards. All balance actions are locked once the semester report has been published or the semester has ended.

## Use Case Scenarios

### Scenario 1: Viewing the Account Balance

| Use Case Name      | Viewing the Account Balance                                                                                                                                                                                                                                                                                                     |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The Dashboard displays five balance cards showing the organization's current financial position: Total Balance, Cash On-Bank, Cash On-Hand, Collectibles, and Fines.                                                                                                                                                           |
| **Preconditions**  | User is authenticated. An active semester exists and initial balance has been set.                                                                                                                                                                                                                                               |
| **Postconditions** | The user can see the current values of all balance categories.                                                                                                                                                                                                                                                                  |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to the Dashboard.<br>2. View the Total Balance card showing the combined Cash On-Bank and Cash On-Hand amount.<br>3. View the Cash On-Bank card (editable via deposit/withdrawal buttons) and Cash On-Hand card (read-only display).<br>4. View the Collectibles card (amount expected to be collected) and Fines card (fine amount per student and paid/total student count).<br>5. Toggle balance visibility using the eye icon on the Total Balance card to show or mask all amounts. |
| **Exceptions**     | 1. If no initial balance has been set for the current semester, the Initial Balance Setup form is displayed instead of the balance cards.                                                                                                                                                                                        |

---

### Scenario 2: Setting the Initial Balance

| Use Case Name      | Setting the Initial Balance                                                                                                                                                                                                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | At the start of a new semester, the system requires authorized users to enter the opening Cash on Bank, Cash on Hand, and Collectibles amounts before the balance cards are shown.                                                                                                          |
| **Preconditions**  | User is authenticated. An active semester exists. No initial balance has been recorded for the current semester.                                                                                                                                                                             |
| **Postconditions** | Initial balance values are saved. The balance cards are displayed on the Dashboard with the entered opening values. The initial values are preserved for end-of-semester report calculations.                                                                                               |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to the Dashboard.<br>2. The Initial Balance Setup form is displayed (shown when no balance row exists for the semester).<br>3. Enter the opening Cash on Bank amount.<br>4. Enter the opening Cash on Hand amount.<br>5. Enter the opening Collectibles amount.<br>6. Click "Save".<br>7. The balance cards appear with the entered values. |
| **Exceptions**     | 1. If saving fails, an error toast is displayed and the form remains open with the entered values intact.                                                                                                                                                                                   |

---

### Scenario 3: Recording a Bank Deposit

| Use Case Name      | Recording a Bank Deposit                                                                                                                                                                                                                                                                             |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to record a deposit, transferring an amount from Cash on Hand into Cash on Bank. Cash on Bank increases and Cash on Hand decreases by the same amount.                                                                                                           |
| **Preconditions**  | User is authenticated. Initial balance has been set. The semester report has not been published and the semester has not ended.                                                                                                                                                                      |
| **Postconditions** | Cash on Bank increases by the deposited amount. Cash on Hand decreases by the same amount. Total Balance remains unchanged. An activity log entry is recorded. An undo option is available via a toast notification.                                                                               |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Cash On-Bank card, click the deposit (+) button.<br>2. The calculator dialog opens.<br>3. Enter the deposit amount using the numeric keypad. The keyboard (digits, dot, Backspace, Enter, Escape) can also be used.<br>4. Click "Confirm" (or press Enter).<br>5. Cash on Bank increases and Cash on Hand decreases by the entered amount.<br>6. A success toast appears with an "Undo" option. |
| **Exceptions**     | 1. If the entered amount is zero or invalid (not a positive number), the system does not process the deposit and the dialog remains open.<br>2. Deposit and withdrawal buttons are hidden when the semester report is published or the semester has ended.                                            |

---

### Scenario 4: Recording a Bank Withdrawal

| Use Case Name      | Recording a Bank Withdrawal                                                                                                                                                                                                                                                                          |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to record a withdrawal, transferring an amount from Cash on Bank to Cash on Hand. Cash on Bank decreases and Cash on Hand increases by the same amount.                                                                                                          |
| **Preconditions**  | User is authenticated. Initial balance has been set. The semester report has not been published and the semester has not ended.                                                                                                                                                                      |
| **Postconditions** | Cash on Bank decreases by the withdrawn amount. Cash on Hand increases by the same amount. Total Balance remains unchanged. An activity log entry is recorded. An undo option is available via a toast notification.                                                                               |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Cash On-Bank card, click the withdrawal (−) button.<br>2. The calculator dialog opens.<br>3. Enter the withdrawal amount using the numeric keypad or keyboard.<br>4. Click "Confirm" (or press Enter).<br>5. Cash on Bank decreases and Cash on Hand increases by the entered amount.<br>6. A success toast appears with an "Undo" option. |
| **Exceptions**     | 1. If the entered amount is zero or invalid, the system does not process the withdrawal and the dialog remains open.<br>2. Withdrawal button is hidden when the semester report is published or the semester has ended.                                                                               |

---

### Scenario 5: Adding to Collectibles

| Use Case Name      | Adding to Collectibles                                                                                                                                                                                                                                                                  |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to add an amount to the Collectibles balance to record expected incoming funds not yet deposited.                                                                                                                                                   |
| **Preconditions**  | User is authenticated. Initial balance has been set. The semester report has not been published and the semester has not ended.                                                                                                                                                         |
| **Postconditions** | The Collectibles balance increases by the entered amount. An activity log entry is recorded. An undo option is available via a toast notification.                                                                                                                                    |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Collectibles card, click the add (+) button.<br>2. The calculator dialog opens.<br>3. Enter the amount using the numeric keypad or keyboard.<br>4. Click "Confirm" (or press Enter).<br>5. The Collectibles value increases by the entered amount.<br>6. A success toast appears with an "Undo" option. |
| **Exceptions**     | 1. If the entered amount is zero or invalid, the system does not process the addition and the dialog remains open.<br>2. The add button is hidden when the semester report is published or the semester has ended.                                                                       |

---

### Scenario 6: Managing Fines

| Use Case Name      | Managing Fines                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to configure the fine amount per student and total number of students with fines, and to transfer the total uncollected fine amount into the Collectibles balance when all payments have been settled.                                                                                                                                       |
| **Preconditions**  | User is authenticated. Initial balance has been set. The semester report has not been published and the semester has not ended.                                                                                                                                                                                                                                                  |
| **Postconditions** | Fine configuration is updated. When confirmed, the uncollected fine total (remaining students × fine amount) is added to Collectibles. An activity log entry is recorded.                                                                                                                                                                                                      |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Fines card, click the edit (pencil) button to open the Fine Edit dialog.<br>2. Enter the fine amount per student and the total number of students subject to fines.<br>3. Click "Confirm" to save the configuration. The Fines card updates to show the fine amount and a paid/total student count.<br>4. Once all fine payments are settled, click the add (+) button on the Fines card.<br>5. A confirmation prompt shows the amount to be added (remaining students × fine amount).<br>6. Click "Confirm" to transfer the amount to Collectibles. |
| **Exceptions**     | 1. If fines have already been added to Collectibles for the current session, the add button is disabled to prevent duplicate entries.<br>2. If no students remain with unpaid fines (remaining count is zero) or the fine amount is zero, the add button is disabled.<br>3. All fine management buttons are hidden when the semester report is published or the semester has ended. |

---

## Related Use Cases

- [Transaction Ledger](transaction-ledger.md)
- [Transaction Entry](transaction-entry.md)
- [Financial Report Generation](financial-report-generation.md)

---

<div align="center">© 2026 Tera IV</div>
