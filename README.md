# n8n-apify-gmaps-scraper
Automated daily Google Maps data crawling using n8n workflows and Apify integration.

## 📊 Overview

This project automates the process of collecting Google Maps reviews daily for multiple restaurant and café branches.
The workflow uses Apify to scrape review data, then processes and monitors the results through n8n automation.

This system empowers customer success and brand management teams to detect operational bottlenecks, mitigate PR risks, and maintain a high service standard through immediate data visibility.

## 🛠️ Tech Stack & Integration

* **Data Extraction:** [Apify Store](https://apify.com/) (`apify/google-maps-scraper`)
* **Orchestration & Workflow Automation:** [n8n](https://n8n.io/) (Self-hosted / Cloud)
* **Data Warehouse / Storage:** Google Sheets API
* **Incident Alerting:** Discord Webhooks API

## 🚀 Key Features & Operational Capabilities

* **Daily Automated Google Maps Review Scraping:** Triggered daily via n8n's native scheduler to automate continuous data collection without manual intervention.
* **Multi-Branch Review Monitoring:** Configured to dynamically track, extract, and consolidate customer feedback across multiple business locations and branches.
* **Low-Rating Review Detection (≤ 3 Stars):** Utilizes conditional n8n logic to instantly isolate negative feedback, bypassing positive reviews for immediate crisis management.
* **Automated Google Sheets Storage:** Synchronizes and logs cleaned review metadata systematically to a centralized spreadsheet for permanent data archiving.
* **Discord Alert Notifications:** Dispatches real-time, actionable Rich Embed alerts directly to operational channels, lowering incident response time.

## 🏗️ Workflow Architecture
The architecture follows a scheduled, event-driven pipeline ensuring seamless data transformation without manual intervention:
```
[Scheduled Trigger] 
       │ (Every Daily via Cron)
       ▼
 ┌───────────┐      API Request      ┌─────────────┐
 │    n8n    |──────────────────────►│ Apify Tasks │
 │  Engine   |◄──────────────────────|   Scraper   │
 └─────┬─────┘     JSON Dataset      └─────────────┘
       │
       ▼
 ┌───────────────┐
 │ n8n Node      │  Filter Condition: [stars <= 3]
 │ (IF/Filter)───│
 └───────────────┘
       │
       ├───► [True: Negative Review]   ──► [Google Sheets Node]  ──► Append to Database
       │                               ──► [Discord Alert Node] ──► Push Rich Embed Notification
       │
       └───► [False: Rating > 3★]      ──► [Google Sheets Node]  ──► Append to Database
```

## 📂 Repository Structure
```
├── apify/
│   ├── Input.json                         # Production-ready configuration for Apify Actor
│   ├── actor_config.md                    # Environment setup and API documentation
│   ├── dataset_Google-Maps-Reviews_...csv # Raw sample dataset for testing/schema mapping
│   ├── output_sample.json                 # Expected JSON payload from the scraper
│   └── sample_response_schema.json        # Data schema definitions for target validation
├── image/
│   ├── Data_flow.png                      # High-level architecture blueprint
│   ├── apify_actor.png                    # Apify UI configuration guide
│   └── output_discord_sample.png          # Production preview of Discord notification embed
├── workflow/
│   └── n8n_workflow.json                  # Production-ready n8n workflow deployment file
└── README.md                              # System documentation
```
## Automation Logic

The n8n workflow automatically:

1. Executes scheduled scraping tasks
2. Retrieves Google Maps reviews from Apify
3. Filters reviews with ratings ≤ 3 stars
4. Stores data into Google Sheets
5. Sends Discord alerts for operational follow-up

## Use Cases
* Restaurant review monitoring
* Customer experience tracking
* Operational issue detection
* Multi-branch reputation management
* Automated review data collection
