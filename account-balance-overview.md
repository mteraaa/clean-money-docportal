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

[Project Homepage](README.md) > Account Balance Overview

---

# Account Balance Overview

The Account Balance Overview displays the organization's current financial position in real time. It presents the total balance alongside a breakdown of cash on bank, cash on hand, collectibles, and outstanding fines. Authorized users can record bank deposits, withdrawals, and collectible additions directly from this view, while the initial balance setup is required at the start of each semester.

## Use Case Scenarios

### Scenario 1: Viewing Account Balance

| Use Case Name      | Viewing Account Balance                                                                                                                                                                                                                                                                                           |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system displays the organization's current financial position, including total balance, cash on bank, cash on hand, collectibles, and fines.                                                                                                                                                                  |
| **Preconditions**  | User is authenticated and logged into the system. Initial balance has been set for the current semester.                                                                                                                                                                                                          |
| **Postconditions** | User has a clear view of the current financial position across all balance categories.                                                                                                                                                                                                                            |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to the Dashboard.<br>2. View the Total Balance card showing the combined cash on bank and cash on hand.<br>3. View the Cash On-Bank, Cash On-Hand, Collectibles, and Fines breakdown cards.<br>4. Toggle balance visibility using the show/hide button on the Total Balance card. |
| **Exceptions**     | 1. If no initial balance has been set for the current semester, the system displays the Initial Balance Setup form instead of the balance cards.                                                                                                                                                                   |

---

### Scenario 2: Setting Initial Balance

| Use Case Name      | Setting Initial Balance                                                                                                                                                                                                                                                                                       |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to set the opening cash on bank, cash on hand, and collectibles at the start of a new semester.                                                                                                                                                                            |
| **Preconditions**  | User is authenticated with financial management permissions. No initial balance has been recorded for the current semester.                                                                                                                                                                                    |
| **Postconditions** | Initial balance is saved to the system. Balance cards are now visible with the entered opening values. Initial values are preserved for end-of-semester reporting.                                                                                                                                            |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to the Dashboard.<br>2. View the Initial Balance Setup form (displayed when no balance exists for the semester).<br>3. Enter the opening Cash on Bank amount.<br>4. Enter the opening Cash on Hand amount.<br>5. Enter the opening Collectibles amount.<br>6. Click "Save". |
| **Exceptions**     | 1. If the save operation fails, the system displays an error message and retains the entered values for correction.                                                                                                                                                                                            |

---

### Scenario 3: Recording a Bank Deposit

| Use Case Name      | Recording a Bank Deposit                                                                                                                                                                                                                                                                       |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to record a deposit into the bank account, increasing cash on bank and decreasing cash on hand by the same amount.                                                                                                                                         |
| **Preconditions**  | User is authenticated. Initial balance has been set. Semester is not yet published/closed.                                                                                                                                                                                                    |
| **Postconditions** | Cash on bank is increased by the deposited amount. Cash on hand is decreased by the same amount. Activity log is updated. An undo option is temporarily available.                                                                                                                            |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Cash On-Bank card, click the deposit (+) button.<br>2. Enter the deposit amount using the calculator dialog.<br>3. Click "Confirm".<br>4. View updated Cash On-Bank and Cash On-Hand values.<br>5. Optionally undo the action using the undo button. |
| **Exceptions**     | 1. If the entered amount is zero or invalid, the system does not process the deposit and keeps the dialog open.                                                                                                                                                                                |

---

### Scenario 4: Recording a Bank Withdrawal

| Use Case Name      | Recording a Bank Withdrawal                                                                                                                                                                                                                                                                         |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to record a withdrawal from the bank account, decreasing cash on bank and increasing cash on hand by the same amount.                                                                                                                                           |
| **Preconditions**  | User is authenticated. Initial balance has been set. Semester is not yet published/closed.                                                                                                                                                                                                         |
| **Postconditions** | Cash on bank is decreased by the withdrawn amount. Cash on hand is increased by the same amount. Activity log is updated. An undo option is temporarily available.                                                                                                                                 |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Cash On-Bank card, click the withdrawal (−) button.<br>2. Enter the withdrawal amount using the calculator dialog.<br>3. Click "Confirm".<br>4. View updated Cash On-Bank and Cash On-Hand values.<br>5. Optionally undo the action using the undo button. |
| **Exceptions**     | 1. If the entered amount is zero or invalid, the system does not process the withdrawal and keeps the dialog open.                                                                                                                                                                                 |

---

### Scenario 5: Adding to Collectibles

| Use Case Name      | Adding to Collectibles                                                                                                                                                                                                                                                         |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Summary**        | The system allows authorized users to add an amount to the collectibles balance to record expected incoming funds not yet received.                                                                                                                                            |
| **Preconditions**  | User is authenticated. Initial balance has been set. Semester is not yet published/closed.                                                                                                                                                                                    |
| **Postconditions** | Collectibles balance is increased by the entered amount. Activity log is updated. An undo option is temporarily available.                                                                                                                                                    |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Collectibles card, click the add (+) button.<br>2. Enter the amount using the calculator dialog.<br>3. Click "Confirm".<br>4. View updated Collectibles value.<br>5. Optionally undo the action using the undo button.               |
| **Exceptions**     | 1. If the entered amount is zero or invalid, the system does not process the addition and keeps the dialog open.                                                                                                                                                               |

---

### Scenario 6: Managing Fines

| Use Case Name      | Managing Fines                                                                                                                                                                                                                                                                                                                                                        |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to configure the fine amount per student and the total number of students subject to fines, and to transfer uncollected fine amounts into the collectibles balance.                                                                                                                                                                |
| **Preconditions**  | User is authenticated. Initial balance has been set. Semester is not yet published/closed.                                                                                                                                                                                                                                                                           |
| **Postconditions** | Fine configuration is updated. Uncollected fine total is added to collectibles when confirmed. Activity log is updated.                                                                                                                                                                                                                                              |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Fines card, click the edit (pencil) button.<br>2. Enter the fine amount per student and the total number of students with fines.<br>3. Click "Confirm" to save the fine configuration.<br>4. Once all payments are settled, click the add (+) button on the Fines card.<br>5. Confirm adding uncollected fines to Collectibles. |
| **Exceptions**     | 1. If fines have already been added to collectibles for the current semester, the add button is disabled to prevent duplicate entries.<br>2. If no students remain with unpaid fines, the add button is disabled.                                                                                                                                                     |

---

## Related Use Cases

- [Transaction Ledger](transaction-ledger.md)
- [Transaction Entry](transaction-entry.md)
- [Financial Report Generation](financial-report-generation.md)

---

<div align="center">© 2026 Tera IV</div>
