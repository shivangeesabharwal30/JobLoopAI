# JobLoopAI User Flows

---

# Flow 1: First-Time User

## Goal

Connect Gmail and Calendar and automatically generate a recruiting pipeline.

## Steps

1. User lands on JobLoopAI.
2. User clicks Connect Google.
3. User grants:
   - Gmail Read Only
   - Calendar Read Only
4. User selects scan range:
   - Last 30 Days
   - Last 60 Days
   - Last 90 Days
   - Custom Date
5. JobLoopAI begins scan.
6. JobLoopAI extracts opportunities.
7. JobLoopAI builds recruiting timeline.
8. User sees dashboard.

## Success

User sees:

- Active opportunities
- Current stage
- Upcoming interviews
- Action items

within 5 minutes.

---

# Flow 2: Daily Monitoring

## Goal

Keep recruiting pipeline updated.

## Steps

1. New email arrives.
2. JobLoopAI scans email.
3. JobLoopAI updates opportunity.
4. JobLoopAI updates stage.
5. JobLoopAI creates task if necessary.

Example:

Interview invitation received.

↓

Create opportunity update.

↓

Create Prepare Interview task.

---

# Flow 3: Application Tracking

## Goal

Track progress of every application.

Example:

Applied

↓

Recruiter Screen

↓

Hiring Manager

↓

Panel

↓

Offer

JobLoopAI displays:

Current Stage

Completed Stages

Remaining Stages

---

# Flow 4: Assignment Tracking

## Goal

Prevent missed assignments.

Example:

Assignment received.

↓

Deadline detected.

↓

Task created.

↓

Reminder generated.

↓

Assignment submitted.

↓

Status updated.

---

# Flow 5: Interview Tracking

## Goal

Track interviews automatically.

Example:

Recruiter schedules interview.

↓

Calendar event detected.

↓

Opportunity updated.

↓

Task created.

↓

Interview completed.

↓

Waiting status assigned.

---

# Flow 6: Follow-Up Recommendation

## Goal

Detect opportunities requiring attention.

Example:

Hiring Manager interview completed.

↓

No response after 7 business days.

↓

Follow-up task created.

↓

User notified.

---

# Flow 7: Rejection Handling

## Goal

Close opportunities automatically.

Example:

Rejection email detected.

↓

Status changed to Closed.

↓

Opportunity moved to Archive.

---

# Flow 8: Dashboard

## Goal

Provide recruiting command center.

Sections:

1. Active Opportunities

2. Upcoming Interviews

3. Open Tasks

4. Follow-Ups Needed

5. Dormant Opportunities

6. Closed Opportunities

---

# Flow 9: Export

## Goal

Export recruiting history.

User can export:

- CSV
- Excel

Fields:

- Company
- Role
- Current Stage
- Status
- Dates
