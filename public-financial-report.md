# Internal Code Name
**Target:** CL.010.001 (or CL.020.001 for pre-completed projects)

| Revision Date | Document Version | Description | Tracking Notes | Approved By |
|---------------|------------------|-------------|----------------|-------------|
| 2025-02-13 | v1.0 | First document version | CL.010.001 | Tan, Ron Nicolas<br>*Project Manager* |
| ... | ... | ... | ... | ... |

## Site Map
- [Project Homepage](README.md)
- [Transaction Ledger](transaction-ledger.md)
- [Transaction Entry](transaction-entry.md)
- [Activity Monitoring](activity-monitoring.md)
- [Public Financial Report](public-financial-report.md)
- [Financial Report Generation](financial-report-generation.md)

---

# Public Financial Report

## Use Case Scenarios

### Scenario 1: Public Access to Financial Summary

| Use Case Name | Public Access to Financial Summary |
|---------------|------------------------------------|
| **Summary** | The system provides public access to semester financial reports showing summarized income, expenses, and budget allocation without detailed transaction information. |
| **Preconditions** | Financial report for the previous semester has been generated. Report has been published by authorized users. |
| **Postconditions** | Public user has access to high-level financial information. Transparency is maintained while protecting detailed transaction data. |
| **Basic Flow** | **Actor Action**<br><br>1. Visit the CLARO public page (no login required).<br>2. Navigate to "Financial Reports" or "Transparency" section.<br>3. View list of available public financial reports by semester.<br>4. Select the report to view.<br>5. View the public financial report showing semester/period covered, total income, total expenses, budget allocation by category, current balance, and key highlights.<br>6. View the report in web format or download as PDF. |
| **Exceptions** | 1. If no public reports have been published, the system displays a message indicating reports will be available soon. |

---

### Scenario 2: Viewing Historical Public Reports

| Use Case Name | Viewing Historical Public Reports |
|---------------|-----------------------------------|
| **Summary** | The system allows users to browse and view financial reports from previous semesters for historical transparency. |
| **Preconditions** | Multiple semester reports are available. |
| **Postconditions** | User has access to historical financial transparency data. Organization demonstrates ongoing commitment to transparency. |
| **Basic Flow** | **Actor Action**<br><br>1. Access public financial reports section.<br>2. View chronological list of available reports showing semester/year, date published, and preview of key figures.<br>3. Browse through historical reports.<br>4. Select a specific semester to view.<br>5. Compare data across different semesters if needed. |
| **Exceptions** | None. |

---

### Scenario 3: Sharing Public Financial Report

| Use Case Name | Sharing Public Financial Report |
|---------------|----------------------------------|
| **Summary** | The system provides shareable links to financial reports for easy distribution without authentication requirements. |
| **Preconditions** | User is viewing a public financial report. |
| **Postconditions** | Report link is shared with others. Public accessibility is maintained. |
| **Basic Flow** | **Actor Action**<br><br>1. View a public financial report.<br>2. Click "Share" button.<br>3. Copy the shareable link provided by the system.<br>4. Share link via social media or messaging.<br>5. Recipients access the report without authentication. |
| **Exceptions** | None. |

---

## Report Content Specifications

### Included in Public Report:
- **Summary Period:** Semester/year covered
- **Total Income:** Aggregate amount by broad categories
- **Total Expenses:** Aggregate amount by broad categories
- **Budget Breakdown:** Percentage or total allocation per category (Events, Operations, Projects, etc.)
- **Opening Balance:** Balance at start of period
- **Closing Balance:** Balance at end of period
- **Key Highlights:** Major projects funded, significant events, or financial milestones

### Excluded from Public Report:
- Individual transaction details
- Specific payee/payer names
- Exact transaction dates and times
- Receipt images
- User information who entered transactions
- Detailed line-item descriptions

---

## Related Use Cases
- [Financial Report Generation](financial-report-generation.md)

---

*© 2026 Tera IV*
