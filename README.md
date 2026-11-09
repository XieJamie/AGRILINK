# AGRILINK
A Web-App designed to manage exports and logistics of Agricultural good to and out of the country
[readme_md.md](https://github.com/user-attachments/files/34596186/readme_md.md)
# AgriLink Logistics Management and Export Tracking System

**AgriLink** is a specialized logistics management and export tracking system designed for small to mid-sized logistics firms handling perishable agricultural exports (cut flowers, tea, coffee, avocados, French beans, and herbs) from Kenya to international markets in Europe and the Middle East.

---

## 📋 System Overview & Scope

Many agricultural logistics firms rely on fragmented tools such as spreadsheets, phone calls, and manual paperwork. This results in data loss, delayed updates, and billing disputes. AgriLink solves these challenges by providing a relational database structure and a modern, responsive user dashboard.

### Key Operational Modules
1. **Customer & Exporter Management**: Register and manage exporters, cooperatives, and international buyers (consignees).
2. **Agricultural Product Catalog**: Manage perishables with temperature and handling requirements.
3. **Shipment Booking & Management**: Book export orders with specified origin/destination terminals and transport methods (Air vs. Sea freight).
4. **Warehouse Storage Tracking**: Oversee temporary storage (cold room vs. ambient) before departure.
5. **Fleet & Driver Dispatch**: Assign vehicles and drivers to pick up produce from farms.
6. **Live Progress Tracking**: Log stage progression from farm collection to international destination delivery.
7. **Billing & Financial Ledger**: Generate invoices and record client payments against shipments.

---

## 🎨 Color Palette & UI Design Standard

The web application follows a distinct primary color palette:
* **Forest Green** (`#1B4332`, `#2D6A4F`): Primary branding, header, navigation, and accents.
* **Warm Beige** (`#F5F2EB`, `#EAE3D2`): Backgrounds, subtle borders, and panel cards.
* **Pure White** (`#FFFFFF`): Workspace containers, tables, and modal backgrounds.

---

## 🗄️ Relational Database Design (MS SQL Server)

The system relies on a **17-entity relational schema** structured to enforce referential integrity and prevent data anomalies.

### Core Database Entities
* `Role` — Defines user system roles (System Admin, Warehouse Staff, Driver, Exporter, etc.).
* `AppUser` — Login authentication credentials and account profiles.
* `Exporter` — Local Kenyan farms, cooperatives, and agricultural exporters.
* `Client` — Overseas consignees/buyers receiving shipped produce.
* `Terminal` — Airports and seaports acting as origin and destination hubs.
* `ProductCategory` & `Product` — Agricultural produce categorization and handling requirements.
* `Driver` & `Vehicle` — Fleet management and local transport assets.
* `Warehouse` — Cold hub facilities and storage capacities.
* `Shipment` — Core export tracking record.
* `ShipmentItem` — Many-to-Many bridge linking products and quantities inside a shipment.
* `Pickup` — Farm collection schedules assigned to drivers and vehicles.
* `ShipmentTracking` — Historical progression logs from origin to delivery.
* `Delivery` — Final delivery sign-off and receipt tracking.
* `Invoice` & `Payment` — Billing records, currency, and payment tracking against shipments.

---

## 🚀 Database Setup Instructions

To deploy the database in **Microsoft SQL Server (MS SQL Server)**:

1. Open **SQL Server Management Studio (SSMS)**.
2. Connect to your SQL Server instance (e.g., `localhost` or `SQLEXPRESS`).
3. Open a **New Query** window and execute the schema creation:
   ```sql
   CREATE DATABASE AgriLinkDB;
   GO
   USE AgriLinkDB;
   GO
   ```
4. Run your combined setup script (`AgriLink_Complete_Database_Setup.sql`) or execute the scripts in order:
   * `01_AgriLink_Schema_DDL.sql` (Creates all 17 tables & foreign keys)
   * `02_AgriLink_Sample_Data.sql` (Seeds initial lookup data)
   * `03_AgriLink_Procedures_and_Views.sql` (Creates `sp_SearchShipments` and `vw_ShipmentTrackingSummary`)

---

## 💻 Web Application Setup

The included `index.html` file is a standalone single-file web application:

1. Download or locate `index.html`.
2. Double-click to open it directly in any modern browser (Chrome, Firefox, Edge, Safari).
3. No external web server setup or npm installations are required.

---

## 🔧 Technology Stack

* **Database Engine**: Microsoft SQL Server (DDL, Stored Procedures, Views, Constraints).
* **Frontend Framework**: HTML5, Tailwind CSS, FontAwesome 6, Google Fonts (Outfit & Inter).
* **Scripting**: Vanilla JavaScript (ES6+).

---

## 👥 Project Authors
* **Roy James Karoki** — BSCLMR117826
* **Emmanuel Gitau** — BSCLMR123726
* **Sifa Wawira** — BSCLMR137926
* **Denzel Otunga** — BSCLMR111626
