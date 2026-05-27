# Automation Flow

## Overview

This project uses Make to automate the lead lifecycle from inbound form submission through opportunity tracking and reporting.

The workflow simulates a lightweight CRM and Revenue Operations system using cloud-based automation tools.

---

# Lead Intake Pipeline

## Step 1 — Trigger

A new Google Forms submission initiates the workflow.

Captured fields include:
- Name
- Email
- Company
- Country
- Company Size
- Source
- Message

---

## Step 2 — Data Cleaning

The automation standardizes incoming data to improve reporting quality and consistency.

Transformations include:
- lowercasing email addresses
- trimming whitespace
- extracting email domains
- standardizing country values

### Example Variables

| Variable | Logic |
|---|---|
| clean_email | lowercase + trim |
| email_domain | extracted from email |
| clean_country | trimmed country value |
| clean_source | normalized acquisition source |

---

# Lead Scoring Logic

The workflow applies business rules to simulate lead qualification logic commonly used in B2B SaaS sales operations.

## Scoring Rules

| Rule | Points |
|---|---|
| Work email | +3 |
| Company provided | +2 |
| Company size 51+ | +3 |
| Message contains "demo" | +3 |
| Referral source | +2 |
| Target country | +2 |

---

## Score Bands

| Score | Band |
|---|---|
| 0–4 | Low |
| 5–8 | Medium |
| 9+ | High |

---

# Qualification Logic

Leads are categorized into lifecycle statuses based on scoring and validation rules.

## Status Categories

| Status | Logic |
|---|---|
| Qualified | Score >= 7 |
| New | Score < 7 |
| Disqualified | Test/fake email detected |

---

# API Enrichment

The workflow integrates the REST Countries API to enrich lead records with geographic metadata.

## Added Fields
- region
- subregion

This simulates real-world enrichment pipelines used in CRM and RevOps systems.

---

# Database Storage

Processed leads are written into the `leads` Google Sheets table.

Additional workflows update:
- opportunities
- activity_log

This creates a lightweight relational operational database.

---

# Slack Notifications

High-scoring leads trigger automated Slack alerts.

## Alert Conditions
- lead score >= 9

## Example Notification

```text
🔥 High-value lead detected

Name: John Doe
Company: Example Inc
Country: Germany
Region: Europe
Score: 10 (High)
Source: Referral
```

---

# Opportunity Pipeline

A second Google Form simulates sales pipeline progression.

## Pipeline Stages
- Demo Booked
- Proposal Sent
- Closed Won
- Closed Lost

---

# Opportunity Automation

When a sales update is submitted:

1. a new opportunity event is created
2. the lead status is updated
3. activity history is logged

---

# Activity Logging

The `activity_log` table tracks:
- lifecycle changes
- stage updates
- operational actions

This creates historical traceability for reporting and auditing.

---

# Error Handling

The workflow includes routing logic for:
- unsupported countries
- missing API enrichment
- invalid leads

Fallback values such as `"Unknown"` were used to prevent automation failures and maintain workflow continuity.
- funnel reporting
- operational consistency
