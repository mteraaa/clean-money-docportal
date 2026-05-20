# Clean Money

CLARO is a web-based transparent financial management system
for the Visayas State University - Student Election Board.

**Target:** CL.010.001 (or CL.020.001 for pre-completed projects)

| Internal Release Code | Date Released |
| :--- | :--- |
| CL.010.001 | 2025-02-13 |
| ... | ... |

---

**Site Map**

- [Project Homepage](README.md)
- [Account Balance Overview](account-balance-overview.md)
- [Transaction Ledger](transaction-ledger.md)
- [Transaction Entry](transaction-entry.md)
- [Activity Monitoring](activity-monitoring.md)
- [Public Financial Report](public-financial-report.md)
- [Financial Report Generation](financial-report-generation.md)

---

## ## CL.010.001 Release Notes

\*\*\* Account Balance Overview

- Add Account Balance Overview use case document covering real-time balance display across total balance, cash on bank, cash on hand, collectibles, and fines cards.
- Document initial balance setup flow for semester-opening configuration of cash on bank, cash on hand, and collectibles.
- Document bank deposit and withdrawal recording via calculator dialog with undo support.
- Document collectibles management including adding amounts and undo functionality.
- Document fines management including fine-per-student configuration and transfer of uncollected fines to collectibles.

\*\*\* Transaction Ledger

- Add Transaction Ledger use case document covering complete display of all recorded financial transactions.
- Document filtering by date range, type, and category, search functionality, and CSV/PDF export.

\*\*\* Transaction Entry

- Add Transaction Entry use case document covering income transaction recording with optional receipt upload.
- Document expense transaction recording with mandatory receipt upload and duplicate detection.
- Document editing of existing transaction entries with change logging.

\*\*\* Activity Monitoring

- Add Activity Monitoring use case document covering administrative viewing of all user activity logs.
- Document automatic activity logging on user login, logout, transaction entry, and transaction modification.
- Document suspicious activity detection and administrator alert flow.

\*\*\* Public Financial Report

- Add Public Financial Report use case document covering no-authentication public access to semester financial summaries.
- Document historical public report browsing and shareable report link generation.
- Specify included and excluded report content to distinguish public summaries from internal transaction data.

\*\*\* Financial Report Generation

- Add Financial Report Generation use case document covering public PDF download and detailed internal report generation.
- Document report publishing workflow that sanitizes internal reports for public release.
- Document scheduled automatic report generation and batch multi-report download.
- Specify public and internal PDF report format standards.

---

### Important Links:

- _Design Specs:_ [https://github.com/...](https://github.com/...)

---

<div align="center">© 2026 Tera IV</div>
