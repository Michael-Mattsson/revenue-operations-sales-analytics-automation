# Revenue Operations & Sales Analytics Automation Pipeline

## Overview

This project simulates a modern Revenue Operations (RevOps) workflow for a fictional B2B SaaS company.

The system automates the full inbound lead lifecycle:
- lead capture
- lead scoring
- qualification logic
- geographic enrichment
- opportunity tracking
- sales notifications
- KPI reporting
- funnel analytics

The goal was to replicate how revenue teams combine operational automation with analytics to improve lead management and sales visibility.

---

# Business Problem

The company receives inbound leads from multiple acquisition channels but lacks:
- centralized lead tracking
- qualification consistency
- visibility into funnel performance
- automated sales notifications
- real-time reporting

Reporting was previously manual and delayed, making it difficult for stakeholders to evaluate:
- lead quality
- channel effectiveness
- conversion rates
- pipeline value

---

# Solution

Built an automated RevOps pipeline using:
- Google Forms
- Make
- Google Sheets
- REST APIs
- Slack
- Looker Studio

The workflow:
1. captures inbound leads
2. cleans and standardizes data
3. scores leads using business rules
4. enriches geographic information via API
5. stores structured operational data
6. alerts sales teams on high-value leads
7. tracks opportunity stage progression
8. visualizes KPIs and funnel performance

---

# Tech Stack

| Tool | Purpose |
|---|---|
| Google Forms | Lead intake simulation |
| Make | Workflow automation |
| Google Sheets | Operational database |
| REST Countries API | Geographic enrichment |
| Slack | Real-time lead alerts |
| Looker Studio | KPI dashboards & reporting |

---

# Key Features

## Lead Intake Automation
- Automated ingestion from Google Forms
- Standardized lead records
- Email/domain parsing
- Country normalization

## Lead Scoring Engine
Scoring model evaluates:
- work vs personal email
- company size
- referral source
- geographic target market
- demo intent signals

## API Enrichment
Integrated REST Countries API to append:
- region
- subregion

## Funnel & Opportunity Tracking
Tracks:
- Qualified leads
- Demo Booked
- Proposal Sent
- Closed Won
- Closed Lost

## Real-Time Notifications
Slack alerts triggered for high-scoring leads.

## Executive Dashboard
Looker Studio dashboard includes:
- funnel conversion
- lead source performance
- geographic distribution
- qualification rates
- pipeline value
- revenue won

---

# Project Structure

```text
Assets/
├── automation/
├── dashboard/
├── diagram/

Automation/
├── lead_pipeline_scenario.json
├── sales_update_scenario.json

data/
├── sample_data.csv
├── schema.md

docs/
├── automation-flow.md
├── business-context.md
├── data-model.md
├── insights-summary.md

README.md
```

---

# Workflow Architecture

```text
Google Forms
   ↓
Make Automation
   ├── Data Cleaning
   ├── Lead Scoring
   ├── API Enrichment
   ├── Slack Alerts
   ↓
Google Sheets Database
   ├── leads
   ├── opportunities
   └── activity_log
   ↓
Looker Studio Dashboard
```

---

# Dashboard KPIs

- Total Leads
- Qualified Leads
- Qualification Rate %
- Demo Booked %
- Win Rate %
- Pipeline Value €
- Revenue Won €

---

# Dashboard Preview

## Funnel Overview
![Funnel Dashboard](assets/dashboard/funnel.png)

## Executive Overview
![Overview Dashboard](assets/dashboard/overview.png)

## Source Performance
![Source Performance](assets/dashboard/source_performance.png)

---

# Automation Flow

## Lead Pipeline
![Lead Pipeline](assets/automation/lead_pipeline_overview.png)

## Lead Scoring Logic
![Lead Scoring](assets/automation/lead_scoring.png)

## Opportunity Flow
![Opportunity Flow](assets/automation/opportunity_flow.png)

---

# System Architecture

![Architecture Diagram](assets/diagram/architecture.png)

---

# Sample Business Insights

Examples generated from simulated data:
- Referral leads showed the highest conversion rate
- Germany and UK produced the highest average lead scores
- Larger companies progressed further through the funnel
- Personal email domains correlated with lower qualification rates

---

# Skills Demonstrated

## Analytics
- Funnel analysis
- KPI reporting
- Operational metrics
- Business intelligence
- Data modeling

## Automation
- Workflow automation
- API integration
- Event-driven pipelines
- CRM process simulation

## Tools
- Make
- Looker Studio
- Google Sheets
- Slack
- REST APIs

---

# Future Improvements

- Replace Google Sheets with PostgreSQL or BigQuery
- Add dbt transformation layer
- Integrate HubSpot CRM API
- Add predictive lead scoring model
- Build automated cohort retention reporting
- Deploy dashboard with scheduled stakeholder reporting

