README.md

# AI-Powered Event Planning Automation Workflow

## Overview

This project automates the event planning process using AI agents and n8n.

The workflow collects event requirements, generates cost estimates from specialized agents, verifies budget constraints, handles managerial approvals, and stores finalized event records automatically.

---

## Problem Statement

Traditional event planning involves:

- Manual vendor coordination
- Cost calculations
- Budget approval emails
- Spreadsheet updates
- Repetitive communication

This workflow automates the entire process using AI agents and workflow automation.

---

## Features

### Event Requirement Collection
Captures:

- Event Type
- Guest Count
- Budget
- Location
- Special Requirements

### AI-Based Cost Estimation

The main AI Agent delegates tasks to:

#### Venue Agent
Calculates venue-related costs.

#### Catering Agent
Calculates catering expenses based on:

- Guest count
- Food preferences
- Event type

#### Logistics Agent
Calculates:

- Transportation
- Staffing
- Setup costs

---

### Budget Validation

The workflow calculates:

Total Cost =
Venue Cost +
Catering Cost +
Logistics Cost

The result is compared with the allocated budget.

---

### Approval System

If:

Total Cost ≤ Budget

The workflow proceeds automatically.

If:

Total Cost > Budget

An approval request email is sent to management.

---

### Webhook-Based Approval

Managers can approve or reject directly from email.

The approval action triggers a webhook.

The workflow processes the response automatically.

---

### Data Storage

Approved event data is stored in Google Sheets for:

- Reporting
- Auditing
- Historical records

---

## Workflow Architecture

Form Submission
↓
Preprocessing
↓
AI Agent
↓
├── Venue Agent
├── Catering Agent
└── Logistics Agent
↓
Wait For All
↓
Budget Checker
↓
IF Budget Valid?
↓
├── YES → Email Confirmation → Google Sheets
│
└── NO → Approval Email
↓
Webhook
↓
Switch
↓
├── Approve → Google Sheets
└── Reject → Rejection Email

---

## Technologies Used

- n8n
- Groq LLM
- JavaScript
- Python
- Google Sheets API
- Webhooks
- Gmail API

---

## Future Improvements

- Multi-level approvals
- Vendor recommendation system
- Dynamic pricing integration
- Event dashboard
- Cost optimization suggestions

---

## Team Contributions

Member 1:
Introduction and Workflow Architecture

Live Demonstration


Member 2:

Approval System and Technical Logic

Benefits, Conclusion, and Q&A