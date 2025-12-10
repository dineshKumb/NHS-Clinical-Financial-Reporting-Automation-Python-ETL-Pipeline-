# Automated Healthcare Reporting Pipeline (NHS Data – Python)

## 📌 Overview
This project automates the end-to-end reporting workflow for NHS clinical and financial datasets used by Primary Eyecare Services.  
It processes **200+ geographical areas**, assigned to **36 reporting officers**, and generates service-level KPI reports in PDF format.  
The solution replaces manual reporting with a fully automated, scalable Python pipeline.

---

## 🚀 Features

### **🔹 Automated File Routing**
- Reads financial Excel files for 200+ NHS areas  
- Identifies which areas belong to which reporting officer  
- Moves each area’s file into that officer’s working folder  

### **🔹 Multi-Layer Data Architecture (Bronze → Silver → Gold)**
**Bronze – Raw Files**  
- Stores unprocessed financial files  
- Handles multi-tab Excel formats (1–14 services per file)  

**Silver – ID-Level Consolidated Files**  
- Splits each multi-tab Excel into individual service files  
- Combines service files across areas into unified datasets  

**Gold – Final Merged Reports**  
- Merges consolidated financial files with clinical backend data  
- Applies all KPIs and clinical transformations  
- Produces analytics-ready final outputs  

### **🔹 Clinical + Financial Data Integration**
- Joins backend clinical raw data with cleaned financial datasets  
- Applies business rules for NHS service reporting  
- Generates CCG/ICB-level KPI metrics  

### **🔹 Automated PDF Report Generation**
- Converts each Gold-level dataset into a clean PDF report  
- Includes:
  - Clinical KPIs  
  - Operational KPIs  
  - Service performance summaries  
- Generates one PDF per service per officer  

### **🔹 Sensitivity & Compliance**
- Designed to work with NHS patient-sensitive data  
- Runs locally within internal environment  
- Enforces folder-level data isolation per officer  

---

## 🏗️ Pipeline Workflow

1. **Ingest financial Excel files** (1 per area, up to 14 service tabs).  
2. **Identify the reporting officer** assigned to each area.  
3. **Route files** into that officer’s workspace.  
4. **Split multi-tab Excel files** into individual service datasets.  
5. **Combine service files across areas** into unified Silver datasets.  
6. **Merge with backend clinical raw data.**  
7. **Apply clinical + KPI transformations.**  
8. **Store final outputs in Gold layer.**  
9. **Generate PDF reports automatically.**

---

## ⚙️ Tech Stack
- **Python**
  - Pandas  
  - OpenPyXL  
  - PyPDF / ReportLab  
  - NumPy  
- **Excel / CSV clinical datasets**
- **Local secure environment (NHS / PES)**

---

## 📊 KPIs Generated
- Service utilization  
- Attendance & follow-up rates  
- Referral patterns  
- Clinical outcomes  
- Activity counts by service type  
- CCG/ICB performance comparisons  

---

## 🗂️ Folder Structure (Officer-Level Workspace)
Officer_Name/
│
├── Bronze/ # Raw financial files
├── Silver/ # Split & combined service datasets
└── Gold/ # Merged clinical-financial outputs + final PDFs