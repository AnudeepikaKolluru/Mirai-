Here is your **complete updated README content** including the SpaceExploration workflow section, formatted consistently and without emojis:

---

# n8n Automation Workflows

This repository contains multiple **n8n workflows** developed as part of assignments and practical projects. These workflows demonstrate automation using webhooks, Telegram bots, Google Sheets, Google Calendar, email services, AI agents, and LLMs, along with frontend integrations using Lovable Dev.

---

Each `.json` file is an exported n8n workflow and can be imported directly into n8n.

---

## Workflows Overview

### 1. Weather Web Page (Lovable Dev)

**Description**
A simple weather application built using Lovable Dev where users enter a city name and receive:

* Temperature
* Humidity
* Air Quality Index (AQI)

**Technologies**

* Lovable Dev frontend
* Weather API integration
* Frontend callback handling

---

### 2. Book Seller Request Form

**Workflow File**
`book seller form.json`

**Description**
Automates book request submissions from users.

**Flow**

* Triggered on form submission
* Stores user details and book request in Google Sheets
* Sends a confirmation email to the user

---

### 3. Developer Portfolio – Contact Us Workflow

**Workflow File**
`protfolio contact me.json`

**Form Fields**

* Name
* Email
* Mobile Number
* Query

**Workflow Steps**

1. Frontend sends data to an n8n webhook
2. Data is logged into Google Sheets
3. Query is processed using an LLM
4. LLM-generated response is emailed back to the user
5. Status or response is returned to the frontend

---

### 4. Calendar AI Agent

**Workflow File**
`Calender.json`

**Description**
A calendar assistant that understands natural language commands and manages Google Calendar events.

**Capabilities**

* Receives chat-based user input
* Extracts date, time, and event details
* Blocks time slots in Google Calendar
* Confirms booking via chat

**Example Input**

```
Block my calendar for a meeting at 2 PM tomorrow
```

---

### 5. Dr. Strange Physiotherapy Appointment System

**Workflow Files**

* `Dr strange appointments.json`
* `Dr strange appointmentsTelegram.json`
* `Dr strange appointments UI.json`

**Description**
An automated appointment scheduling system for a physiotherapy clinic.

**Features**

* Appointment booking via Telegram bot and Lovable UI
* Google Calendar availability checks
* 30-minute appointment slots with buffer time
* Working hours: 9 AM to 5 PM (Monday to Friday)
* Lunch break enforced between 1 PM and 2 PM
* Patient data stored in Google Sheets
* Email confirmation sent after successful booking
* Privacy ensured by not exposing other patient data

---

### 6. LLM RAG Workflow

**Workflow File**
`llm_rag.json`

**Description**
Implements a Retrieval-Augmented Generation (RAG) pipeline using an LLM.

**Capabilities**

* Accepts user queries
* Retrieves relevant context
* Generates accurate responses using LLM reasoning

---

### 7. SpaceExploration – Automated Space Photo Workflow

**Workflow File**
`space_exploration.json`

**Description**
An automated workflow that sends a space-related image to all subscribers at a fixed scheduled time every day without manual intervention.

**Workflow Steps**

1. Triggered automatically using a Cron node at a fixed time daily
2. Fetches a space image from NASA APOD API
3. Extracts image URL, title, and description
4. Retrieves all subscriber emails from Google Sheets or database
5. Sends formatted email with image and details to all subscribers
6. Logs execution status

**Capabilities**

* Fully automated daily execution
* Valid and trusted image source (NASA APOD API)
* Bulk email delivery to subscribers
* No manual triggering required
* Can be extended to Telegram or other messaging platforms

**Scheduling Example**

```
0 9 * * *
```

Runs every day at 9:00 AM.

---

## How to Use

1. Clone or download this repository
2. Open n8n
3. Import the required `.json` workflow file
4. Configure credentials (Google Sheets, Google Calendar, Email, Telegram, LLM, NASA API)
5. Activate or publish the workflow as required

---

## Notes

* Telegram Trigger workflows must be unpublished to test manually in n8n
* Production URLs are used for webhook-based workflows
* Cron-based workflows run automatically once activated
* All workflows are tested with multiple scenarios and edge cases

---
