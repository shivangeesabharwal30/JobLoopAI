# JobLoopAI Opportunity Detection

## Goal

Convert thousands of Gmail and Calendar events into a clean recruiting pipeline.

JobLoopAI should determine:

- Is this a new opportunity?
- Is this an update to an existing opportunity?
- Is this a duplicate?
- Has the opportunity closed?

---

# Example

These emails:

1. Application submitted
2. Recruiter screen scheduled
3. Recruiter screen completed
4. Hiring manager interview scheduled

Should become:

Company: Cisco

Role: Senior Product Manager

Current Stage:
Hiring Manager Interview Scheduled

Completed Stages:
- Applied
- Recruiter Screen

Status:
Active

NOT four separate opportunities.

---

# Opportunity Identity

An opportunity is uniquely identified by:

Primary Keys:

- Company Name
- Role Title

Examples:

Cisco + Product Manager

Meta + Technical Program Manager

Adobe + Senior Product Manager

---

# Matching Rules

## High Confidence Match

Match to existing opportunity if:

Company matches exactly

AND

Role title matches exactly

Example:

Cisco
Senior Product Manager

Cisco
Senior Product Manager

Result:

Same opportunity

---

## Medium Confidence Match

Match if:

Company matches

AND

Role similarity > 80%

Examples:

Product Manager

Senior Product Manager

Principal Product Manager

Result:

Potential match

Needs confidence score.

---

## Low Confidence Match

Do NOT merge automatically.

Examples:

Cisco Product Manager

Cisco Technical Program Manager

Result:

Separate opportunities

---

# Company Detection

Sources:

- Email domain
- Email signature
- ATS metadata
- Calendar organizer

Examples:

careers@cisco.com

→ Cisco

recruiting@adobe.com

→ Adobe

---

# Role Detection

Sources:

- Email subject
- Email body
- Calendar title

Examples:

Application for Senior Product Manager

Hiring Manager Interview - TPM

Interview Loop - Product Operations Manager

---

# Opportunity Lifecycle

Applied

↓

Under Review

↓

Recruiter Screen

↓

Hiring Manager

↓

Technical

↓

Take Home

↓

Panel

↓

References

↓

Offer

OR

Rejected

OR

Withdrawn

---

# Stage Advancement

Always keep highest valid stage.

Example:

Applied

↓

Recruiter Screen

↓

Hiring Manager

Current Stage:

Hiring Manager

Do not revert to Applied.

---

# Rejection Rules

If rejection detected:

Status = Closed

Current Stage = Rejected

---

# Offer Rules

If offer detected:

Status = Offer

Current Stage = Offer

Highest priority.

---

# Duplicate Prevention

Never create a second opportunity if:

Company matches

Role matches

Opportunity already exists

Instead:

Append event to timeline.

---

# Timeline Example

Cisco

Senior Product Manager

Timeline:

06/01 Applied

06/05 Recruiter Screen Scheduled

06/08 Recruiter Screen Completed

06/12 Hiring Manager Scheduled

Current Stage:

Hiring Manager Scheduled

Status:

Active
