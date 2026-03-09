# 🛡️ Organized Retail Crime (ORC) Intelligence Engine

![Palantir Foundry](https://img.shields.io/badge/Palantir-Foundry-black?style=for-the-badge&logo=palantir)
![Data Engineering](https://img.shields.io/badge/Data-Engineering-blue?style=for-the-badge)
![Fraud Detection](https://img.shields.io/badge/Domain-Fraud_Detection-red?style=for-the-badge)

## 📖 Project Overview
Retailers lose millions of dollars annually to return fraud and Organized Retail Crime (ORC). Traditional fraud systems often fail because they analyze shoppers as isolated individuals. 

This project is an end-to-end data product built in **Palantir Foundry** that shifts the paradigm to connected network analysis. By utilizing device-fingerprinting and an object-oriented data model, this engine automatically flags coordinated fraud rings, visualizes the network of fake accounts, and empowers Loss Prevention investigators to freeze compromised accounts with a single click.

## 🏗️ Solution Architecture
This product was architected across three distinct layers within the Palantir Foundry ecosystem to transform raw transactional data into operational action.

### 1. The Logic Layer (Pipeline Builder & PySpark)
* **Ingestion & Processing:** Processed raw transactional and customer data using Foundry's data integration layer.
* **Device Fingerprinting:** Engineered logic to group disparate customer accounts by the physical hardware (`Device Id`) used to execute the return.
* **Risk Aggregation:** Applied a dynamic mathematical threshold to sum the total `Margin Exposure` across shared devices.
* **Alerting:** Configured automated logic to instantly flag any `Customer Id` with a "CRITICAL - FREEZE REQUIRED" alert if their shared network crosses the defined financial threshold.

### 2. The Digital Twin Layer (Ontology Manager)
* **Semantic Modeling:** Abstracted raw data into real-world Objects: **Customers**, **Transactions**, and **Stores**.
* **Relational Mapping:** Engineered 1:Many and Many:Many links between objects to create a connected, 3D web of the retail environment.
* **Operational Writebacks:** Developed a secure Action (`freeze_fraudulent_account`) to allow immediate database modifications directly from the frontend interface with full auditability.

### 3. The Operational Application (Workshop)
Designed and deployed the **Fraud Command Center**, a live investigative dashboard tailored for the Loss Prevention team:
* **Intelligent Inbox:** A prioritized queue of active fraud rings, sorted by highest financial exposure.
* **Network Visualization:** An interactive Network Graph and Bar Chart that automatically maps the total dollar amount stolen by every individual fake account sharing the targeted device.
* **Active Execution:** A connected Action button that allows the investigator to immediately update the database and freeze the entire fraud ring in real-time.

## 📸 Application Showcase

> **Fraud Command Center Dashboard**
> *The central investigative hub showing the prioritized inbox (left), the connected fraud ring graph (center), and the single-click operational execution panel (right).*

![Fraud Command Center](images/dashboard_screenshot.png) 

## 📈 Business Impact
* **Reduced Time-to-Action:** Transformed a manual, hours-long investigative spreadsheet process into a three-click workflow.
* **Increased Detection Accuracy:** Shifted analytical focus from individual bad actors to interconnected device networks, exposing hidden ORC rings.
* **Immediate ROI:** Provided Loss Prevention teams with an exact, real-time dollar figure of money at risk and the immediate tooling to stop the exposure.

## 🛠️ Tech Stack
* **Platform:** Palantir Foundry
* **Data Integration:** Pipeline Builder, PySpark, SQL
* **Data Modeling:** Ontology Manager
* **Application Development:** Foundry Workshop, Foundry Actions

---
*Disclaimer: All data shown in screenshots and documentation is synthetic/dummy data created solely for the purpose of this portfolio project. No proprietary company data or personally identifiable information (PII) is included.*
