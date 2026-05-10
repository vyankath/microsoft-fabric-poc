# Microsoft Fabric — End-to-End Analytics POC

* A complete proof of concept built on Microsoft Fabric covering data ingestion, transformation, warehousing, semantic modeling, and Power BI dashboard development using 3 different approaches.

## 📌 Overview

* This POC demonstrates how to build a full analytics pipeline entirely within Microsoft Fabric — from raw CSV files to live Power BI dashboards without leaving the platform.

**Pipeline Flow:**
-------------------------------------------------------------------------------------------
CSV Files → Lakehouse → Data Pipeline → Warehouse → Data Preparation
→ Semantic Model → Power BI Dashboard (3 approaches) >>  Fabric Web, DirectQuery, Import Mode
---------------------------------------------------------------------------------------------
## Step by Step Walkthrough

### Step 1 — Workspace Setup
* Created a dedicated Fabric workspace with Fabric Capacity license mode.
* All items — Lakehouse, Warehouse, Pipeline, Semantic Model, and Reports — live here under one roof sharing a single OneLake storage layer.

### Step 2 — Lakehouse & CSV Upload
* Created a Lakehouse and uploaded an entire folder of CSV files into the
* Files section of OneLake. The Lakehouse provides two layers:
  * **Files** — raw file storage
  * **Tables** — managed Delta tables (auto-converted from CSV)

### Step 3 — Data Pipeline
* Built a Data Pipeline using the Copy Data activity to move data from the
* Lakehouse into the Fabric Warehouse.
  * Source: Lakehouse Files / Delta Tables
  * Destination: Fabric Warehouse
  * Configured column mappings, data types, and write mode (Overwrite)

### Step 4 — Data Preparation
Performed data transformation inside the Warehouse using:
  * **SQL Queries** — cleaned nulls, fixed types, renamed columns

### Step 5 — Semantic Model
* Created a reusable Semantic Model from the Warehouse:
 * Defined table relationships (Star Schema)
 * Wrote DAX measures (Total Sales, YTD Revenue, % Growth)
 * Built hierarchies (Year → Quarter → Month)
 * Configured column formats and hid technical fields

### Step 6 — Dashboard (3 Approaches)
Built the same dashboard three different ways.
See [Dashboard Approaches](#dashboard-approaches) below.

## Dashboard Approaches

### Approach 1 — Fabric Web (Semantic Model)
## How it was built
1. Opened the Semantic Model in the Fabric workspace
2. Clicked "Create Report" — launched browser-based Power BI editor
3. Built visuals using drag and drop from the field list
4. Added slicers, cards, bar charts, and line charts
5. Saved the report → File → Download this file (.pbix)

**Pros:**
* No Power BI Desktop install required
* Instantly connected to Semantic Model
* Easy browser-based collaboration

**Cons:**
* Limited advanced modeling features
* No offline editing
* Less flexible than Desktop
---

### Approach 2 — Power BI Desktop (DirectQuery via Semantic Model)
## How it was built
1. Opened Power BI Desktop
2. Get Data → Power BI Semantic Models
3. Selected the published Semantic Model from Fabric workspace
4. Chose "DirectQuery" mode when prompted
5. Built all visuals — every interaction fires a live query to Warehouse
6. Saved the .pbix file

**Pros:**
* Always shows current/live data
* No data duplication in .pbix
* Inherits model-level row-level security

**Cons:**
* Slower interactive performance
* Requires constant internet connection
* Higher query load on the Warehouse

---

### Approach 3 — Power BI Desktop (Import Mode from Warehouse)
## How it was built
1. Opened Power BI Desktop
2. Get Data → Microsoft Fabric → Warehouse
3. Entered the Warehouse SQL endpoint URL
4. Selected required tables → chose Import mode
5. Built relationships, DAX measures, and hierarchies inside Desktop
6. Designed all visuals and formatted the dashboard
7. Saved the .pbix file
8. Published to Power BI Service for scheduled refresh

**Pros:**
* Fastest report performance
* Works offline after import
* Full DAX and modeling capability

**Cons:**
* Data goes stale without scheduled refresh
* Larger .pbix file size
* Risk of data duplication
---

## 📊 Dashboard Approaches — Comparison
---------------------------------------------------------
FABRIC DATA ACCESS APPROACHES
---------------------------------------------------------

1. Approach 1 – Fabric Web
* Data Mode       : Live via model
* Desktop Required: No
* Performance     : Moderate
* Data Freshness  : Always current
* Best For        : Quick browser-based reports
--------------------------------------------------------
2. Approach 2 – DirectQuery
* Data Mode       : Live via Warehouse
* Desktop Required: Yes
* Performance     : Moderate
* Data Freshness  : Always current
* Best For        : Live data accuracy and real-time reporting
--------------------------------------------------------
3. Approach 3 – Import
* Data Mode       : Cached in .pbix
* Desktop Required: Yes
* Performance     : Fast
* Data Freshness  : Requires scheduled/manual refresh
* Best For        : Maximum performance and faster dashboards
------------------------------------------------------------
FABRIC LICENSE TIERS As on Apr 2026
------------------------------------------------------------

1. Free Trial
* Fabric Workloads: Full access available
* Best For        : Evaluation, learning, and proof of concept (POC)
* Limitation      : Expires after 60 days
--------------------------------------------------------
2. Power BI Pro
* Fabric Workloads: Not included
* Best For        : Standard BI reporting
* Limitation      : No Microsoft Fabric features
--------------------------------------------------------
3. Premium Per User (PPU)
* Fabric Workloads: Enabled
* Best For        : Small teams and advanced users
* Limitation      : Can become costly at larger scale
--------------------------------------------------------
4. F-SKUs (Fabric Capacity)
* Fabric Workloads: Enterprise-grade access
* Best For        : Organization-wide deployment
* Limitation      : Capacity sizing and management can be complex

---

## 🛠️ Prerequisites

* Microsoft Fabric Trial or licensed workspace
*  Power BI Desktop (for Approach 2 & 3)
* CSV source files (place under `/data/raw/`)

---

## 📎 Resources

* [Microsoft Fabric Documentation](https://learn.microsoft.com/en-us/fabric/)
* [Power BI Desktop Download](https://powerbi.microsoft.com/desktop/)
* [DAX Reference](https://learn.microsoft.com/en-us/dax/)

---

## 📬 Questions or Feedback

Feel free to open an issue or connect on LinkedIn.
