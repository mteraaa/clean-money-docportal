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

[Project Homepage](README.md) > Financial Report Generation

---

# Financial Report Generation

The Financial Report Generation module enables authorized users to produce, preview, and publish financial reports in PDF format. It supports on-demand generation of detailed internal reports for review and sanitized public summaries for transparency, as well as scheduled automatic report generation for consistent semester-end reporting.

## Use Case Scenarios

### Scenario 1: Downloading Public Financial Report PDF

| Use Case Name      | Downloading Public Financial Report PDF                                                                                                                                                                                                                   |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows public users to download PDF copies of published financial reports for offline access.                                                                                                                                                  |
| **Preconditions**  | Financial report has been published. User is on the public financial report page.                                                                                                                                                                         |
| **Postconditions** | PDF copy of financial report is downloaded to user's device. User can view, save, or share the offline version.                                                                                                                                           |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to the public financial reports section.<br>2. View available reports.<br>3. Select desired semester/period report.<br>4. Click "Download PDF" button.<br>5. Receive PDF file containing the public financial report. |
| **Exceptions**     | 1. If PDF generation fails, the system displays an error message and suggests trying again or viewing the web version.<br>2. If PDF is large, the system may display a file size warning before download.                                                 |

---

### Scenario 2: Generating Detailed Internal Financial Report

| Use Case Name      | Generating Detailed Internal Financial Report                                                                                                                                                                                                                                                                                                                                                                                |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system generates comprehensive internal reports with full transaction details for authorized users.                                                                                                                                                                                                                                                                                                                      |
| **Preconditions**  | User is authenticated with report generation permissions. Sufficient transaction data exists for the report period.                                                                                                                                                                                                                                                                                                          |
| **Postconditions** | Comprehensive internal financial report is generated. Report includes all transaction details for internal review.                                                                                                                                                                                                                                                                                                           |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to Report Generation section (internal).<br>2. Select report parameters: report type, date range/semester, categories to include, and level of detail.<br>3. Click "Generate Report".<br>4. Preview the comprehensive report including all transaction details, receipt references, user audit trail, category breakdowns, and trends/analytics.<br>5. Download the detailed PDF report. |
| **Exceptions**     | None.                                                                                                                                                                                                                                                                                                                                                                                                                        |

---

### Scenario 3: Publishing Financial Report

| Use Case Name      | Publishing Financial Report                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system creates a sanitized public version of internal reports by removing sensitive details and publishing for public access.                                                                                                                                                                                                                                                                                                                                                         |
| **Preconditions**  | User is authenticated with publishing permissions. Report has been generated and reviewed internally.                                                                                                                                                                                                                                                                                                                                                                                     |
| **Postconditions** | Sanitized financial report is available to public. Public can access and download the report. Detailed information remains protected.                                                                                                                                                                                                                                                                                                                                                     |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to Report Management section.<br>2. Select the report to publish.<br>3. Click "Prepare for Public Release".<br>4. Review the sanitized public version created by the system (with individual transaction details removed, data aggregated by categories, sensitive information removed, and summary statistics generated).<br>5. Add any public notes or highlights.<br>6. Click "Publish Report".<br>7. View confirmation that report is now public. |
| **Exceptions**     | None.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

---

### Scenario 4: Scheduling Automatic Report Generation

| Use Case Name      | Scheduling Automatic Report Generation                                                                                                                                                                                                                                                                                                                                          |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows administrators to configure automatic report generation on a scheduled basis.                                                                                                                                                                                                                                                                                 |
| **Preconditions**  | User is authenticated with admin privileges.                                                                                                                                                                                                                                                                                                                                    |
| **Postconditions** | Automated report generation is configured. Reports are generated on schedule without manual intervention.                                                                                                                                                                                                                                                                       |
| **Basic Flow**     | **Actor Action**<br><br>1. Navigate to Report Settings.<br>2. Configure automatic report generation: schedule (e.g., end of each semester), report type, and auto-publish option.<br>3. Save configuration.<br>4. System creates scheduled task that automatically generates reports, creates public versions, publishes if enabled, and sends notifications to relevant users. |
| **Exceptions**     | None.                                                                                                                                                                                                                                                                                                                                                                           |

---

### Scenario 5: Batch Downloading Multiple Reports

| Use Case Name      | Batch Downloading Multiple Reports                                                                                                                                                                              |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**        | The system allows users to download multiple financial reports in a single ZIP file.                                                                                                                            |
| **Preconditions**  | Multiple reports are available.                                                                                                                                                                                 |
| **Postconditions** | Multiple reports are downloaded in a single operation. User can access historical data offline.                                                                                                                 |
| **Basic Flow**     | **Actor Action**<br><br>1. Access financial reports section.<br>2. Select multiple reports using checkboxes.<br>3. Click "Download Selected Reports".<br>4. Download the ZIP file containing all selected PDFs. |
| **Exceptions**     | None.                                                                                                                                                                                                           |

---

## Report Format Specifications

### Public PDF Report Format:

- **Header:** Organization name, logo, report period
- **Summary Page:** Key financial figures and highlights
- **Income Summary:** Total and breakdown by broad categories
- **Expense Summary:** Total and breakdown by broad categories
- **Charts/Graphs:** Visual representation of data
- **Footer:** Publication date, contact information for inquiries

### Internal PDF Report Format:

- All elements of public report PLUS:
- **Detailed Transaction List:** All transactions with dates, amounts, descriptions
- **Receipt References:** Links or references to uploaded receipts
- **Audit Trail:** User information for each transaction
- **Detailed Analytics:** Trends, comparisons, projections
- **Notes Section:** Internal comments and observations

---

## Related Use Cases

- [Transaction Ledger](transaction-ledger.md)
- [Public Financial Report](public-financial-report.md)

---

<div align="center">© 2026 Tera IV</div>
