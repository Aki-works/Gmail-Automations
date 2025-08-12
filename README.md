# 📬 Gmail Automations – n8n Workflow

![n8n](https://img.shields.io/badge/Automation-n8n-blueviolet?style=flat-square)
![Google Sheets](https://img.shields.io/badge/Integration-Google%20Sheets-green?style=flat-square)
![Gmail](https://img.shields.io/badge/Email-Gmail-red?style=flat-square)
![Google Gemini](https://img.shields.io/badge/AI-Google%20Gemini-orange?style=flat-square)

## 📌 Overview

This repository contains a **scrubbed** version of an **n8n workflow** designed to automate the classification and tracking of Gmail messages related to **job applications, interviews, LinkedIn activity, promotions, and more**.

The workflow:

* **Monitors incoming Gmail messages** every minute.
* **Classifies emails** into predefined categories.
* **Uses Google Gemini AI** to extract structured job application details.
* **Saves extracted data** to Google Sheets for tracking and analysis.

---

## ⚙️ Core Features

### 🔔 **Automated Email Trigger**

* Checks Gmail inbox every **minute** for new emails.
* Works continuously once the workflow is activated in n8n.

### 🏷 **Smart Email Categorization**

Automatically classifies emails into:

* **Applied** – Job applications sent.
* **Callbacks – Interviews** – Interview confirmations or scheduling.
* **Callbacks – Test Scheduled** – Online assessments or tests.
* **LinkedIn – Job Alert** – New job recommendations from LinkedIn.
* **LinkedIn – Messaged Me** – Recruiter messages on LinkedIn.
* **LinkedIn – Others/Ignore** – Non-relevant LinkedIn activity.
* **Promotions** – Marketing and promotional offers.
* **Rejected** – Application rejections.
* **Services** – Subscription/service-related updates.
* **Other** – Anything that doesn't fit above.

### 🤖 **AI-Powered Information Extraction**

* Sends **relevant job-related emails** to Google Gemini.
* Extracts:

  * `Date Applied`
  * `Company Name`
  * `Job Title`
  * `Location`
  * `Recruiter Name`
  * `Recruiter Contact`
  * `Job Posting Link`
  * `Salary / Compensation`
  * `Job Type`
  * `Notes`

### 📊 **Google Sheets Integration**

* Appends structured results into a Google Sheets job tracker.
* Creates a **centralized application history** for easy access and filtering.

---

## 🗂 Workflow 
<img width="1114" height="680" alt="image" src="https://github.com/user-attachments/assets/853db8ff-6cd1-4dc9-8dc3-1a708623059d" />

---

## 🔒 Privacy & Security

This repository’s workflow file has been **sanitized**:

* All **OAuth credentials** replaced with `"[REDACTED]"`.
* All **Google Sheets links and document IDs** replaced with `"[REDACTED_URL]"`.
* All **Workflow, Instance, and Version IDs** replaced with `"[REDACTED_*]"`.
* No personal email addresses, tokens, or sensitive identifiers remain.

> **Note:** To run this workflow, you will need to **restore your own credentials** in n8n.

---

## 🛠 Setup Instructions

### 1️⃣ **Prerequisites**

* **n8n** installed locally or on a server ([installation guide](https://docs.n8n.io/)).
* **Gmail account** with API access enabled.
* **Google Cloud Project** for Gmail & Google Sheets APIs.
* **Google Gemini (PaLM API)** credentials.

### 2️⃣ **Import the Workflow**

1. Download the scrubbed JSON workflow from this repository.
2. In n8n, go to **Import Workflow** and upload the file.
3. Replace `"[REDACTED]"` credentials with your actual credential names in n8n.

### 3️⃣ **Set Up Gmail Labels**

* Create labels matching the ones in the workflow.
* Update `labelIds` in Gmail nodes to match your account’s IDs.

### 4️⃣ **Connect Google Sheets**

* Replace placeholder document IDs with your own Google Sheet’s ID.
* Ensure your Google Sheets API credentials have **edit** access.

### 5️⃣ **Activate the Workflow**

* Enable the workflow in n8n.
* Incoming emails will be categorized and processed automatically.

---

## 📊 Example Google Sheets Output

| Date Applied | Company Name | Job Title    | Location | Recruiter Name | Recruiter Contact                     | Job Posting Link    | Salary / Compensation | Job Type  | Notes                 |
| ------------ | ------------ | ------------ | -------- | -------------- | ------------------------------------- | ------------------- | --------------------- | --------- | --------------------- |
| 2025-08-12   | ACME Corp    | Data Analyst | Remote   | John Doe       | [john@acme.com](mailto:john@acme.com) | acme.com/jobs/123   | ₹12 LPA               | Full-time | Remote role, flexible |
| 2025-08-15   | Beta Systems | ML Engineer  | New York | Not Provided   | Not Provided                          | betasys.com/careers | Not Provided          | Contract  | AI-based project work |

---

## 🚀 Possible Improvements

* **Slack Notifications**: Alert when a new interview email arrives.
* **Priority Tagging**: Score opportunities by keywords (e.g., "Remote", "High Salary").
* **Analytics Dashboard**: Use Data Studio to visualize job application progress.

---

## 📜 License

Released under the **MIT License** – you may use, modify, and distribute with attribution.


