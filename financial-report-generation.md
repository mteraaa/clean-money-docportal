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

[Project Homepage](README.md) > Financial Report Generation

---

# Financial Report Generation

The Financial Report Generation module allows authorized users to preview, prepare, and publish financial reports from the Dashboard. The Publish dialog provides four tabs — Certification, Attachment A & B, Attachment C, and Public — each generating a separate PDF. On publish, all generated PDFs are uploaded to the organization's storage bucket. An existing published report can also be unpublished, which removes all associated files and archives.

## Use Case Scenarios

### Scenario 1: Previewing the Financial Report

| Use Case Name      | Previewing the Financial Report                                                                                                                                                                                                                                                                                                              |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to preview the auto-generated financial report PDF before publishing.                                                                                                                                                                                                                                     |
| **Preconditions**  | User is authenticated. An active semester with balance and entries data exists. No report has been published yet for the semester.                                                                                                                                                                                                           |
| **Postconditions** | The user views the current financial report PDF inline.                                                                                                                                                                                                                                                                                      |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Dashboard, click the "Preview" button in the header area.<br>2. The system generates and opens a PDF viewer card showing the financial report.<br>3. The report is generated from current semester data (balance, income entries, and expense entries).<br>4. Close the viewer to return to the Dashboard. |
| **Exceptions**     | None.                                                                                                                                                                                                                                                                                                                                        |

---

### Scenario 2: Publishing a Financial Report

| Use Case Name      | Publishing a Financial Report                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system generates and publishes up to four PDF documents — the main financial report with certification, Attachment A & B (income), Attachment C (expenses), and a public financial summary — uploading them to the organization's storage bucket.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Preconditions**  | User is authenticated. An active semester with balance and entries data exists. No report has been published yet for the semester.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Postconditions** | All generated PDF files are uploaded to the storage bucket. The Dashboard transitions to a locked (read-only) state. Income and expense entry tables and balance cards can no longer be edited.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Dashboard, click the "Publish" button.<br>2. The Publish dialog opens with four tabs:<br>&nbsp;&nbsp;- **Certification:** Fill in certification fields (receiver name, designation, date deposited, amount, treasurer name, audit date, auditor name). A live PDF preview updates as fields are filled.<br>&nbsp;&nbsp;- **Attachment A & B:** Select income entries to include in the Attachment A/B PDF. Preview is generated on selection.<br>&nbsp;&nbsp;- **Attachment C:** Select expense entries to include in the Attachment C PDF. Preview is generated on selection.<br>&nbsp;&nbsp;- **Public:** Auto-generated financial summary PDF; no inputs required.<br>3. Click "Publish".<br>4. The system uploads all generated PDFs to the organization's storage bucket and saves records to the reports table.<br>5. The Dashboard locks all entry and balance editing. |
| **Exceptions**     | 1. If publishing fails, an error message is displayed below the Publish button and the dialog remains open.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

---

### Scenario 3: Unpublishing a Report

| Use Case Name      | Unpublishing a Report                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Summary**        | The system allows authorized users to unpublish a report, deleting all associated PDF files from storage and related archives, and returning the Dashboard to an editable state.                                                                                                                                                                                                                       |
| **Preconditions**  | User is authenticated. A report has already been published for the current semester.                                                                                                                                                                                                                                                                                                                   |
| **Postconditions** | All report files and related archives are removed from storage and the database. The Dashboard returns to editable state, allowing new entries and balance updates.                                                                                                                                                                                                                                    |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Dashboard, click the "Unpublish" button (visible when a report is published).<br>2. The Unpublish confirmation dialog appears.<br>3. Confirm the action.<br>4. The system deletes all report-related archive files from storage, removes their archive records, deletes the main report file and its database record.<br>5. The Dashboard returns to editable state. |
| **Exceptions**     | None.                                                                                                                                                                                                                                                                                                                                                                                                  |

---

## Related Use Cases

- [Transaction Ledger](transaction-ledger.md)
- [Public Financial Report](public-financial-report.md)

---

<div align="center">© 2026 Tera IV</div>
