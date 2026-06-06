# JobLoopAI Data Model

JobLoopAI stores structured recruiting pipeline data extracted from Gmail and Google Calendar.

By default, it does not store full email bodies.

---

# User Settings

## user_settings

Stores scan preferences.

| Field | Type | Description |
|---|---|---|
| user_id | string | Unique user identifier |
| scan_start_date | date | Date from which Gmail/Calendar scan starts |
| scan_window_days | integer | 30, 60, 90, or custom |
| last_scan_timestamp | datetime | Last successful scan |
| gmail_connected | boolean | Gmail connection status |
| calendar_connected | boolean | Calendar connection status |

---

# Opportunity

## opportunities

Represents one job opportunity at one company.

| Field | Type | Description |
|---|---|---|
| opportunity_id | string | Unique opportunity ID |
| user_id | string | Owner |
| company_name | string | Company |
| role_title | string | Role |
| source | string | Gmail, Calendar, or both |
| current_stage | string | Current recruiting stage |
| status | string | Active, Waiting, Action Required, Dormant, Closed |
| recruiter_name | string | Recruiter name if detected |
| recruiter_email | string | Recruiter email if detected |
| first_detected_at | datetime | First time opportunity was detected |
| last_activity_at | datetime | Most recent email/calendar activity |
| confidence_score | float | 0.0 to 1.0 |
| recommended_action | string | Next recommended action |
| action_due_date | date | Due date if applicable |

---

# Pipeline Event

## pipeline_events

Represents each detected recruiting event.

| Field | Type | Description |
|---|---|---|
| event_id | string | Unique event ID |
| opportunity_id | string | Linked opportunity |
| user_id | string | Owner |
| event_type | string | Application Submitted, Interview Scheduled, Rejection, etc. |
| stage | string | Recruiting stage associated with event |
| status_after_event | string | Opportunity status after event |
| event_date | datetime | When the event happened |
| source_type | string | Gmail or Calendar |
| source_id | string | Gmail message ID or Calendar event ID |
| source_sender | string | Email sender or calendar organizer |
| summary | string | Short sanitized summary |
| confidence_score | float | 0.0 to 1.0 |

---

# Task / Action

## tasks

Represents something the user needs to do.

| Field | Type | Description |
|---|---|---|
| task_id | string | Unique task ID |
| opportunity_id | string | Linked opportunity |
| user_id | string | Owner |
| task_type | string | Follow Up, Prepare, Complete Assignment, Respond |
| task_title | string | Human-readable task |
| due_date | datetime | Optional due date |
| priority | string | High, Medium, Low |
| status | string | Open, Done, Dismissed |
| created_at | datetime | Task creation time |

---

# Calendar Event

## calendar_events

Stores interview-related calendar events.

| Field | Type | Description |
|---|---|---|
| calendar_event_id | string | Google Calendar event ID |
| opportunity_id | string | Linked opportunity if detected |
| user_id | string | Owner |
| title | string | Calendar title |
| start_time | datetime | Start time |
| end_time | datetime | End time |
| organizer | string | Organizer email |
| attendees | list | Attendee emails |
| detected_stage | string | Recruiter Screen, HM Screen, Panel, etc. |
| status | string | Upcoming, Completed, Cancelled |

---

# Closed Opportunity Rules

An opportunity is Closed if:

- Rejection email is detected
- Candidate withdrawal is detected
- Role closed email is detected

Closed opportunities can be reopened if a newer active-stage email is detected after the closure.

---

# Dormant Opportunity Rules

An opportunity is Dormant if:

- Applied only and no response for 21+ days
- Interview completed and no response for 10+ business days
- Recruiter outreach had no reply/activity for 14+ days

---

# Privacy Rules

Do not store full email body by default.

Allowed stored fields:

- sender
- subject summary
- extracted company
- extracted role
- extracted stage
- extracted dates
- extracted recruiter
- source message ID

User controls:

- Delete all data
- Disconnect Gmail
- Disconnect Calendar
- Export CSV
