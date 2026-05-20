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

[Project Homepage](README.md) > Public Financial Report

---

# Public Financial Report

The Public Financial Report page lists all published financial reports for the user's organization. Reports are stored in the organization's storage bucket (Faculties or Campus SEB) and are accessed via time-limited signed URLs. Authorized users can view, open, and delete published reports from this page.

## Use Case Scenarios

### Scenario 1: Viewing Published Reports

| Use Case Name      | Viewing Published Reports                                                                                                                                                                                                                                              |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The Reports page displays a list of all published financial report files for the user's organization, ordered by publication date from most recent to oldest.                                                                                                         |
| **Preconditions**  | User is authenticated. At least one report has been published for the organization.                                                                                                                                                                                    |
| **Postconditions** | User can see all published reports with their titles and publication dates.                                                                                                                                                                                            |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to the Reports page from the sidebar.<br>2. View the list of published reports showing each report's title and publication date.<br>3. Reports are ordered by publication date, most recent first.<br>4. Each report is accessible via a signed URL valid for one hour. |
| **Exceptions**     | 1. If no reports have been published yet, the table is empty.                                                                                                                                                                                                         |

---

### Scenario 2: Opening a Published Report

| Use Case Name      | Opening a Published Report                                                                                                                                                                                                           |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Summary**        | The system allows authorized users to open and view a published report file directly from the Reports page.                                                                                                                         |
| **Preconditions**  | User is authenticated. A published report is available in the list.                                                                                                                                                                  |
| **Postconditions** | The report file is opened via its signed URL for viewing or downloading.                                                                                                                                                             |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Reports page, click on a report entry.<br>2. The system opens the report file using its signed URL. PDF files are displayed inline; image files are previewed in a viewer dialog.<br>3. The user can download the file directly from the viewer or browser. |
| **Exceptions**     | 1. If the signed URL has expired (after one hour), access to the file will fail. The user must reload the Reports page to generate a fresh signed URL.                                                                               |

---

### Scenario 3: Deleting a Published Report

| Use Case Name      | Deleting a Published Report                                                                                                                                                                                                                                    |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows authorized users to delete one or more published reports, removing both the file from storage and the record from the database.                                                                                                              |
| **Preconditions**  | User is authenticated. At least one report is listed on the Reports page.                                                                                                                                                                                      |
| **Postconditions** | The selected report files are removed from the storage bucket. The corresponding records are deleted from the reports table. The Reports page list is updated.                                                                                                 |
| **Basic Flow**     | **Actor Action**<br><br>1. On the Reports page, enter select mode.<br>2. Select one or more reports to delete.<br>3. Click the delete action.<br>4. The system removes the selected files from the storage bucket and deletes their database records.<br>5. The reports list refreshes to reflect the deletion. |
| **Exceptions**     | None.                                                                                                                                                                                                                                                          |

---

## Related Use Cases

- [Financial Report Generation](financial-report-generation.md)

---

<div align="center">© 2026 Tera IV</div>
