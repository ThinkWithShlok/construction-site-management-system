# 🏗️ Construction Site Management System (CSMS)

A responsive, role-based application for managing construction sites, workforce logs, material procurement, geofenced attendance, and invoicing.

The app supports a hybrid data architecture: it operates **offline in Demo Mode** using detailed local mock data out-of-the-box, or connects to a **Supabase backend database** with full authentication and Row-Level Security (RLS).

---

## 🌟 Key Features

*   **👥 Role-Based Portals (RBAC):** Customized user profiles and interfaces for:
    *   **Admin:** User approvals, overall project oversight, material approvals, and invoice generation.
    *   **Site Engineer:** GPS-validated attendance marking, daily progress logs, and petty cash books.
    *   **Contractor:** Materials requisition requests and assigned task management.
    *   **Worker:** Mobile-responsive dashboards for daily check-in and task tracking.
*   **📍 Geofenced Attendance:** Uses Leaflet maps and the **Haversine formula** to enforce that field workers can only check in/out when within a specified radius (e.g. 300m) of their assigned project site.
*   **📦 Material Requests & Inventory:** Real-time stock status monitoring with structured contractor requests, site engineer reviews, and final admin releases.
*   **💰 Financial & Admin Ledgers:** Live petty cash books for engineers, invoice line-item calculations with PDF exports (jsPDF), and automated wage settlements.
*   **📲 PWA & Localization:** Progressive Web App capabilities for offline asset caching (Vite PWA) and multilingual translation framework (i18next).

---

## 🛠️ Technology Stack

*   **Frontend:** React 19, JavaScript (ES6+), Vanilla CSS3 (Custom design system), React Router 7.
*   **Data Vis & Mapping:** Leaflet JS, React Leaflet, Chart.js, React-Chartjs-2.
*   **PDF Engine:** jsPDF, jsPDF-AutoTable.
*   **Backend & Auth:** Supabase (Auth, PostgreSQL DB, RLS policies).
*   **PWA Tooling:** Vite 7, `vite-plugin-pwa`, Workbox.

---

## ⚙️ Quick Start Setup

### 1. Install Dependencies
```bash
npm install
```

### 2. Run in Demo Mode (Local Offline)
If no environment variables are set, the app will automatically launch in **Demo Mode** using high-quality local mock data.
```bash
npm run dev
```

### 3. Connect to Supabase Backend
Create or edit the `.env` file in the root directory:
```env
VITE_SUPABASE_URL=https://your-project-id.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-publishable-key
```

### 4. Build for Production
To generate optimized static assets in the `/dist` directory:
```bash
npm run build
```

---

## 🛢️ Database Seeding (Supabase)
To host the database on your own Supabase instance, execute the following SQL scripts located in the `supabase/` folder in your Supabase SQL Editor:
1.  `schema.sql` (Creates base tables and triggers)
2.  `petty_cash.sql`, `wage_settlements.sql`, `attendance_geolocation.sql` (Enables advanced features)
3.  `dummy_data_seed.sql` (Populates initial test accounts and records)
4.  `add_approval_column.sql`, `fix_approval_rls.sql`, `fix_rls_all_tables.sql` (Applies security policies)

---

## 🔐 Test Accounts (Demo Mode / Seeded DB)
You can log in immediately using the following accounts:

| Role | Email | Password | Primary Actions |
| :--- | :--- | :--- | :--- |
| **Admin** | `alan@g.com` | `123456` | Global dashboard, approvals, invoices, material final reviews |



<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.demo</groupId>
    <artifactId>github-actions-demo</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>jar</packaging>

    <name>github-actions-demo</name>

    <properties>
        <maven.compiler.source>17</maven.compiler.source>
        <maven.compiler.target>17</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>3.8.1</version>
            <scope>test</scope>
        </dependency>
    </dependencies>

</project>
