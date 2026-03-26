# 🛡️ Enterprise Safety Incident Reporting System


## 📖 Project Overview
The Safety Incident Reporting System is an end-to-end enterprise solution designed to digitize, track, and resolve workplace safety hazards. Built on the Microsoft Power Platform, this application replaces fragmented paper trails with a centralized database, automated background alerts, and dynamic role-based UI routing. 

This project demonstrates a full-stack low-code architecture, integrating frontend application design, relational database management, and scheduled automation.

## 🛠️ Technology Stack & Architecture
* **Frontend UI:** Microsoft Power Apps (Canvas App)
* **Backend Database:** Microsoft Dataverse (Relational tables: `Incidents` and `Actions`)
* **Automation Engine:** Power Automate (Scheduled Cloud Flows)

## ✨ Key Features & Capabilities

### 1. Dynamic Role-Based Access Control (RBAC)
* The app features intelligent routing at startup based on the logged-in user's credentials (`User().Email`).
* **Standard Workers:** Automatically routed to a streamlined reporting form to capture incident details, photos, and automatic GPS coordinates.
* **HSE Supervisors:** Securely routed to a management dashboard to review open incidents, assess severity, and resolve cases. Navigation to this dashboard is strictly locked to approved administrators.

### 2. Automated "Watchdog" Workflows
* A scheduled Power Automate Cloud Flow acts as a daily system watchdog.
* It queries the Dataverse backend for any logged actions or incidents that have missed their target completion dates.
* Upon finding overdue records, it dynamically fetches the assigned user's profile and dispatches a high-priority "Overdue Action" email reminder to enforce safety compliance.

### 3. Smart Data Capture
* Utilizes native device capabilities to capture live photos or gallery uploads.
* Features a dynamic location toggle, allowing users to either manually type a location or automatically pull their device's exact latitude and longitude GPS coordinates.

## 📁 Repository Contents
* `SafetyReportingApp_Final.zip`: The untouched, exported Power Apps package containing the application and flow logic.
* `Screenshots/`: High-resolution images of the UI, Supervisor Dashboard, and automated email alerts.
* `README.md`: Project documentation.

## 🚀 How to Deploy (For Evaluators)
To test this application in your own Microsoft environment:
1. Download the `SafetyReportingApp_Final.zip` file from this repository. **Do not extract the `.zip` file.**
2. Navigate to [make.powerapps.com](https://make.powerapps.com).
3. Select your desired environment.
4. Click **Apps** on the left-hand navigation menu.
5. Click **Import canvas app** from the top ribbon.
6. Upload the `.zip` package, authenticate the necessary Dataverse and Office 365 connections, and click **Import**.
