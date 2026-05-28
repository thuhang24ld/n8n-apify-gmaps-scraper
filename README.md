# n8n-apify-gmaps-scraper
Automated daily Google Maps data crawling using n8n workflows and Apify integration.

## Overview

This project automates the process of collecting Google Maps reviews daily for multiple restaurant and café branches.
The workflow uses Apify to scrape review data, then processes and monitors the results through n8n automation.

The system is designed to:

* collect customer reviews automatically
* detect low-rating reviews
* store structured data
* send real-time notifications for operational monitoring

## Tech Stack
* n8n
* Apify
* Google Sheets
* Discord Webhook

## Features
* Daily automated Google Maps review scraping
* Multi-branch review monitoring
* Low-rating review detection (≤ 3 stars)
* Automated Google Sheets storage
* Discord alert notifications
* Structured JSON and CSV outputs
* Workflow orchestration with n8n

## Workflow Architecture
Google Maps
      ↓
Apify Review Scraper
      ↓
n8n Automation Workflow
      ↓
Filter Low Ratings (≤ 3★)
      ↓
Google Sheets Database
      ↓
Discord Notifications

## Project Structure
<img width="433" height="385" alt="image" src="https://github.com/user-attachments/assets/67d557b8-105e-469a-8b5c-81375f64f031" />

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
