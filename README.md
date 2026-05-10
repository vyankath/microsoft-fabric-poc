# Microsoft Fabric — End-to-End Analytics POC

* A complete proof of concept built on Microsoft Fabric covering
* data ingestion, transformation, warehousing, semantic modeling,
* and Power BI dashboard development using 3 different approaches.

## 📌 Overview

* This POC demonstrates how to build a full analytics pipeline entirely
* within Microsoft Fabric — from raw CSV files to live Power BI dashboards —
* without leaving the platform.

**Pipeline Flow:**

CSV Files → Lakehouse → Data Pipeline → Warehouse → Data Preparation
→ Semantic Model → Power BI Dashboard (3 approaches) >>  Fabric Web, DirectQuery, Import Mode

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
