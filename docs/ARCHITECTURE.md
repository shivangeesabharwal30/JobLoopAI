# JobLoopAI Architecture

## Goal

Automatically convert Gmail and Calendar activity into a structured recruiting pipeline.

---

# Components

1. Gmail Connector
2. Calendar Connector
3. Event Extraction Engine
4. Opportunity Matching Engine
5. Pipeline Database
6. Dashboard

---

# Gmail Connector

Purpose:

Read recruiting-related emails.

Input:

Gmail API

Output:

Raw email events

Examples:

Application Submitted

Interview Scheduled

Rejection

Offer

Assignment

---

# Calendar Connector

Purpose:

Read recruiting-related calendar events.

Input:

Google Calendar API

Output:

Interview events

Examples:

Recruiter Screen

Hiring Manager Interview

Panel Interview

Final Round

---

# Event Extraction Engine

Purpose:

Convert raw emails into structured recruiting events.

Input:

Email

Output:

Company

Role

Stage

Status

Dates

Confidence

---

# Opportunity Matching Engine

Purpose:

Determine whether an event belongs to an existing opportunity.

Rules:

Match Company

Match Role

Update Timeline

Prevent Duplicates

---

# Pipeline Database

Stores:

Users

Opportunities

Events

Calendar Events

Settings

---

# Dashboard

Displays:

Recruiting Feed

Opportunities

Interviews

Assignments

Archive

---

# Processing Flow

Gmail Email

↓

Extract Event

↓

Match Opportunity

↓

Update Timeline

↓

Update Dashboard

---

Calendar Event

↓

Extract Event

↓

Match Opportunity

↓

Update Timeline

↓

Update Dashboard
