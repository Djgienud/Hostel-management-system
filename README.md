# 🏨 Hostel Management System - Enterprise Oracle Database

A robust, fully normalized (3NF/BCNF) Oracle Relational Database Management System (RDBMS) designed to manage the end-to-end lifecycle of a multi-institute, co-ed hostel facility. 

This project simulates a production-grade backend architecture handling physical infrastructure, admission lifecycles, dynamic billing, and vendor management.

## 🚀 Key Features & Business Logic
- *Advanced CRM for Inquiries:* Tracks student inquiries, conversion rates, and follow-up calls natively within the database.
- *Dynamic Pricing Engine:* Room charges dynamically adapt based on room type (Single, Double, Triple) and amenities (AC/Non-AC).
- *Flexible Mess Allocation:* Accommodates hostel residents, outside private mess opt-outs, and "Mess-Only Outsiders" via structured DDL logic.
- *Zero-Anomaly Design:* Strictly normalized to 3NF/BCNF to prevent update, insertion, and deletion anomalies.
- *Referential Integrity:* Enforced via strict Primary Key (PK) and Foreign Key (FK) constraints across all 15 operational tables.

## 🛠️ Tech Stack
- *Database:* Oracle RDBMS (12c+)
- *Languages:* SQL, PL/SQL
- *Tools:* Oracle VirtualBox, SQL*Plus, SQL Developer
- *Design:* Entity-Relationship Modeling, 3NF Normalization

## 🗄️ Database Schema Domains (15 Tables)

The database is logically partitioned into 5 core domains:

### 1. Physical Infrastructure & Assets
- institutions: Associated universities and coaching centers.
- buildings & hostels: Multi-block, Co-ed hostel tracking.
- rooms: Capacity and dynamic occupancy tracking.
- infrastructure: Asset tracking mapped to specific rooms.

### 2. Pre-Admission & Resident Lifecycle
- inquiries: Lead generation and follow-up CRM.
- candidates: Core resident demographics and KYC (Aadhaar).
- admissions: Room mapping and mess preference logs.

### 3. Dining, Exceptions & Vendors
- mess: Mess schedules and dietary types.
- mess_exceptions: Fee rebates for vacations (e.g., Diwali).
- vendors: Groceries and daily supply management.

### 4. Financials & Billing
- payments: Automated invoice generation combining base rent, penalties, and dynamic mess charges.

### 5. Logs, Grievances & Exits
- attendance: Timestamp-based In/Out tracking.
- issues: Maintenance and grievance ticket tracking.
- exit_records: Final settlement and clearance logs.

## ⚙️ How to Execute (Local Setup)
To deploy this schema in your local Oracle environment:

1. Clone this repository to your local machine or VirtualBox VM.
2. Open your terminal and log into SQL*Plus: sqlplus username/password
3. Execute the SQL scripts in numerical order to maintain Foreign Key integrity:
   ```sql
   SQL> @01_institutions.sql
   SQL> @02_buildings.sql
   -- Continue sequentially up to 15_exit_records.sql
