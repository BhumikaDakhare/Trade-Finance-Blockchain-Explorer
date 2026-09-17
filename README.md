<div align="center">

# 🔗 Trade Finance Blockchain Explorer

### Transparent Trade Finance • Document Integrity • Ledger Tracking • Risk Insights

![Status](https://img.shields.io/badge/STATUS-Completed-success)
![Project](https://img.shields.io/badge/PROJECT-Trade%20Finance-blue)
![Backend](https://img.shields.io/badge/BACKEND-FastAPI-009688)
![Frontend](https://img.shields.io/badge/FRONTEND-React.js-61DAFB)
![Database](https://img.shields.io/badge/DATABASE-PostgreSQL-336791)
![Auth](https://img.shields.io/badge/AUTH-JWT-orange)
![Hashing](https://img.shields.io/badge/HASHING-SHA--256-purple)

**A secure web-based platform for tracking trade finance documents,  
verifying document integrity, exploring ledger events, and analyzing trade risk.**

</div>

---

# 📖 Overview

Trade Finance Blockchain Explorer is a secure application designed to provide
transparent and tamper-evident tracking of trade finance artifacts such as:

- Letters of Credit (LoCs)
- Invoices
- Bills of Lading
- Purchase Orders
- Certificates of Origin
- Insurance Certificates

The system combines document hashing, ledger-style event tracking,
role-based access control, and risk analytics to improve transparency,
traceability, and document integrity across trade finance workflows.

---

# ✨ Key Features

### 📄 Document Management

- Upload and store trade finance documents
- Generate SHA-256 hash for uploaded documents
- Store document metadata
- Secure object storage using S3-compatible storage
- Verify document integrity using stored hashes

### ⛓️ Ledger Explorer

- Track document lifecycle events
- View chronological trade events
- Record actions such as:
  - ISSUED
  - AMENDED
  - SHIPPED
  - RECEIVED
  - PAID
  - CANCELLED
  - VERIFIED

### 🔐 Secure Authentication

- JWT-based authentication
- Access and refresh tokens
- Role-based access control
- Organization-based access
- Multiple user roles:
  - Bank
  - Corporate
  - Auditor
  - Admin

### 🛡️ Tamper-Evident Audit Trail

- Maintain immutable-style event records
- Store document hashes
- Verify whether a document has been modified
- Maintain audit logs for important system actions

### 📊 Risk Scoring

- Counterparty risk scoring
- Combine internal trade events with external statistics
- Display risk information through analytics dashboards

### 📈 Analytics & Reporting

- Trade flow visualization
- Risk dashboards
- Transaction analytics
- Exportable reports
- CSV/PDF reporting

---

# 🏗️ System Architecture

```text
                    ┌───────────────────────┐
                    │       Frontend        │
                    │   React + Tailwind    │
                    └───────────┬───────────┘
                                │
                                │ REST API
                                ▼
                    ┌───────────────────────┐
                    │       FastAPI         │
                    │       Backend         │
                    └───────────┬───────────┘
                                │
             ┌──────────────────┼──────────────────┐
             │                  │                  │
             ▼                  ▼                  ▼
       ┌───────────┐      ┌────────────┐     ┌─────────────┐
       │   Auth    │      │ Documents  │     │   Ledger    │
       │   + RBAC  │      │ + Hashing  │     │   Explorer  │
       └───────────┘      └──────┬─────┘     └─────────────┘
                                 │
                                 ▼
                         ┌───────────────┐
                         │ S3-Compatible │
                         │    Storage    │
                         └───────────────┘

                                │
                                ▼
                     ┌─────────────────────┐
                     │     PostgreSQL      │
                     │                     │
                     │ Users               │
                     │ Documents           │
                     │ Ledger Entries      │
                     │ Transactions        │
                     │ Risk Scores         │
                     │ Audit Logs          │
                     └─────────────────────┘

