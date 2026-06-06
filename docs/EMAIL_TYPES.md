# JobLoopAI Email Types

JobLoopAI classifies job-search emails and calendar events to reconstruct a user's recruiting pipeline.

The scan start date is configurable by the user:
- Last 30 days
- Last 60 days
- Last 90 days
- Custom date

Default: Last 60 days.

---

## Core Questions JobLoopAI Answers

1. Where did I apply?
2. Did I get a response?
3. What stage am I in?
4. What stages are completed?
5. What needs action now?
6. Which opportunities are active, closed, or stalled?

---

# Email/Event Types

## 1. Application Submitted

### Meaning
The user applied to a role.

### Signals
- "Thank you for applying"
- "Application received"
- "We received your application"
- "Thanks for your interest"
- "Your application to..."
- Greenhouse, Lever, Ashby, Workday confirmation emails

### Stage
Applied

### Status
Active

---

## 2. Application Under Review

### Meaning
The company has acknowledged review.

### Signals
- "Your application is under review"
- "Our team is reviewing your profile"
- "Recruiting team is evaluating"
- "We are impressed with your background"

### Stage
Under Review

### Status
Active

---

## 3. Recruiter Outreach

### Meaning
A recruiter contacted the user.

### Signals
- "I came across your profile"
- "Would love to chat"
- "Are you open to opportunities?"
- "Your background looks relevant"
- "Let's schedule a call"

### Stage
Recruiter Outreach

### Status
Active

---

## 4. Recruiter Screen Scheduled

### Meaning
Initial recruiter call is scheduled.

### Signals
- "Recruiter screen"
- "Intro call"
- "Initial conversation"
- "Phone screen"
- "Schedule time with recruiting"
- Calendar event with recruiter

### Stage
Recruiter Screen Scheduled

### Status
Active

### Action
Prepare background, role fit, compensation, work authorization, availability.

---

## 5. Recruiter Screen Completed

### Meaning
Recruiter call happened.

### Signals
- Calendar event is in the past
- "Thanks for chatting"
- "Great speaking with you"
- "Next steps after our call"
- "I will share your profile with the team"

### Stage
Recruiter Screen Completed

### Status
Waiting

---

## 6. Hiring Manager Screen Scheduled

### Meaning
Hiring manager interview is scheduled.

### Signals
- "Hiring manager interview"
- "Meet with the hiring manager"
- "HM screen"
- "Manager conversation"
- "Next round with the team lead"

### Stage
Hiring Manager Screen Scheduled

### Status
Active

---

## 7. Hiring Manager Screen Completed

### Meaning
Hiring manager round happened.

### Signals
- Calendar event is in the past
- "Thanks for meeting with the hiring manager"
- "We will follow up with feedback"
- "Next steps after the manager conversation"

### Stage
Hiring Manager Screen Completed

### Status
Waiting

---

## 8. Technical / Functional Screen Scheduled

### Meaning
A technical, product, design, case, coding, system design, or functional interview is scheduled.

### Signals
- "Technical screen"
- "Product case"
- "System design"
- "Coding interview"
- "Functional interview"
- "Technical discussion"
- "Case interview"

### Stage
Technical Screen Scheduled

### Status
Active

---

## 9. Technical / Functional Screen Completed

### Meaning
Technical or functional screen happened.

### Signals
- Calendar event is in the past
- "Thanks for completing the technical round"
- "We will review feedback"
- "Next steps after your interview"

### Stage
Technical Screen Completed

### Status
Waiting

---

## 10. Take-Home Assignment Received

### Meaning
User received an assignment.

### Signals
- "Take-home assignment"
- "Assignment"
- "Case study"
- "Product exercise"
- "Please submit"
- "Due by"
- "Deadline"

### Stage
Take-Home Assignment

### Status
Action Required

### Action
Complete and submit assignment before deadline.

---

## 11. Take-Home Assignment Submitted

### Meaning
User submitted the assignment.

### Signals
- "Thanks for submitting"
- "We received your assignment"
- "Submission received"
- User sent email containing attachment/link and phrases like "Please find my assignment"

### Stage
Assignment Submitted

### Status
Waiting

---

## 12. Panel / Onsite Loop Scheduled

### Meaning
Final or multi-person interview loop is scheduled.

### Signals
- "Panel interview"
- "Onsite"
- "Virtual onsite"
- "Interview loop"
- "Final round"
- "Meet the team"
- Multiple interview calendar events

### Stage
Panel / Onsite Scheduled

### Status
Active

---

## 13. Panel / Onsite Loop Completed

### Meaning
Panel or onsite loop happened.

### Signals
- Calendar events are in the past
- "Thanks for meeting the team"
- "We are collecting feedback"
- "We will be in touch soon"

### Stage
Panel / Onsite Completed

### Status
Waiting

---

## 14. References Requested

### Meaning
Company requested references.

### Signals
- "Please provide references"
- "Reference check"
- "Professional references"
- "Names and contact information"

### Stage
Reference Check

### Status
Action Required

---

## 15. Offer / Verbal Offer

### Meaning
Company indicates offer intent.

### Signals
- "Offer"
- "Verbal offer"
- "We would like to move forward with an offer"
- "Compensation discussion"
- "Offer details"

### Stage
Offer

### Status
Active

---

## 16. Rejection

### Meaning
Company declined to move forward.

### Signals
- "Unfortunately"
- "We will not be moving forward"
- "We have decided to pursue other candidates"
- "Not selected"
- "At this time"

### Stage
Rejected

### Status
Closed

---

## 17. Candidate Withdrew

### Meaning
User declined or withdrew.

### Signals
- "I would like to withdraw"
- "I am no longer interested"
- "I have accepted another offer"
- "Please withdraw my application"

### Stage
Withdrawn

### Status
Closed

---

## 18. Follow-Up Needed

### Meaning
User should follow up because no response has been detected after a meaningful event.

### Signals
- Interview completed 5+ business days ago
- Assignment submitted 5+ business days ago
- Recruiter said "next week" and no update arrived
- No response after user sent availability

### Stage
Follow-Up Needed

### Status
Action Required

---

## 19. Stalled / Dormant

### Meaning
No activity for a long time.

### Signals
- No recruiter response for 14+ days
- No stage movement for 21+ days
- Application confirmation only, no follow-up

### Stage
Stalled

### Status
Dormant

---

## 20. Scheduling In Progress

### Meaning
Company is trying to schedule but no final time is confirmed.

### Signals
- "Please share availability"
- "Here is my Calendly"
- "Can you send times?"
- "Let's find time"
- "Please book a slot"

### Stage
Scheduling

### Status
Action Required or Waiting

---

# Stage Priority Rules

When multiple emails exist for the same company and role, use the most advanced confirmed stage.

Priority order:

1. Offer
2. Reference Check
3. Panel / Onsite Completed
4. Panel / Onsite Scheduled
5. Take-Home Assignment Submitted
6. Take-Home Assignment
7. Technical Screen Completed
8. Technical Screen Scheduled
9. Hiring Manager Screen Completed
10. Hiring Manager Screen Scheduled
11. Recruiter Screen Completed
12. Recruiter Screen Scheduled
13. Recruiter Outreach
14. Under Review
15. Applied
16. Rejected
17. Withdrawn

Exception:
Rejected and Withdrawn override all active stages unless there is a newer active email after the rejection/withdrawal.

---

# Status Types

## Active
Opportunity is moving forward or awaiting next step.

## Action Required
User must do something.

## Waiting
User has completed their step and is waiting for company response.

## Dormant
No recent activity.

## Closed
Rejected, withdrawn, or role closed.

---

# Recommended Actions

## Follow Up
Triggered when:
- No response 5+ business days after interview
- No response 5+ business days after assignment submission
- Recruiter asked for availability and user has not replied

## Prepare
Triggered when:
- Interview is scheduled
- Calendar event is within 48 hours

## Complete Assignment
Triggered when:
- Assignment is detected
- Deadline is upcoming

## Respond
Triggered when:
- Recruiter asks for availability
- Recruiter asks for information
- References requested

## No Action
Triggered when:
- Application was submitted
- User is waiting
- Opportunity is closed

---

# Confidence Score

Each classification should include a confidence score:

## High
Strong explicit language found.

Example:
"Your interview with Cisco is scheduled for June 10."

## Medium
Likely recruiting signal but missing role/company/stage details.

Example:
"Great chatting today. We'll follow up soon."

## Low
Possibly related but needs review.

Example:
"Following up on our conversation."

---

# Privacy Rules

JobLoopAI should not store full email bodies by default.

Store only:
- company
- role
- stage
- status
- recruiter name
- recruiter email
- important dates
- source email id
- confidence score
- recommended action

User should be able to:
- delete extracted data
- disconnect Google
- export pipeline
