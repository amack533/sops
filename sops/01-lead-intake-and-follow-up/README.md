# Lead Intake and Follow-Up for a Local Service Business

> **In one sentence:** Every inbound lead is captured, contacted, and moved toward a booked appointment — so no lead ever ends up in an undefined or "lost" state.

| | |
|---|---|
| **Responsible** | Intake owner (supported by the automation system) |
| **Effective from** | 2026-05-17 |
| **Last updated** | 2026-05-17 |
| **Version** | 1.0 |

---

## What this is about

This procedure defines how an inbound lead is captured, qualified, contacted, and moved toward a booked appointment. When it runs correctly, every lead ends up in one of three clear states:

- **Booked** — an appointment is scheduled.
- **Disqualified** — the lead is not a fit, and the reason is recorded.
- **In a follow-up sequence** — the lead is being contacted on a defined schedule.

No lead should ever be in an undefined or "lost" state.

## When to use this

**Covered** — all inbound leads from paid and organic channels:

- paid social lead forms,
- website contact and booking forms,
- missed inbound calls.

**Not covered** — walk-in customers and referrals handled in person.

The procedure begins the moment a new lead record is created in the CRM by any connected intake source. Intake is automated — under normal operation, no one enters leads by hand.

## Who is involved

- **Automation system** — handles lead capture, deduplication, first contact, and reminders.
- **Intake owner** — the team member who monitors the pipeline and handles anything the automation escalates.

## What you need beforehand

Before this procedure can run, all of the following must be true:

- The CRM pipeline exists with the six stages listed below.
- Every intake source is connected to the CRM via webhook, and each connection has been verified.
- Approved message templates exist for first contact, reminders, and reactivation.
- Opt-out handling is configured and compliant for every channel in use.

## The pipeline stages

A lead moves through six clearly defined stages:

| Stage | Meaning |
|-------|---------|
| **1. New Lead** | Created by intake, not yet contacted. |
| **2. Contacted** | First outreach has been sent. |
| **3. Engaged** | The lead has replied or otherwise responded. |
| **4. Booked** | An appointment is scheduled. |
| **5. Disqualified** | The lead is not a fit; a reason is recorded. |
| **6. Nurture** | No response after the follow-up sequence; moved to long-term contact. |

## Step by step

### Step 1 — Capture and deduplicate

When a lead record is created, the system checks for an existing record with the same phone number or email address.

- **If a match is found:** the new information is merged into the existing record — no duplicate is created.
- **If no match is found:** the new record is kept.

Either way, the lead is placed in the **New Lead** stage.

### Step 2 — First contact

Within a short, defined window after capture (for example, **five minutes**), the system sends the first-contact message on the same channel the lead used. The lead moves to the **Contacted** stage.

Speed matters here: response rates drop sharply the longer first contact is delayed.

### Step 3 — Follow-up sequence

If the lead does not respond, the system sends a defined sequence of follow-up messages spaced over several days (for example, on **day 1, day 3, and day 6**). Every message is logged on the lead record. The lead stays in the **Contacted** stage until it either responds or the sequence ends.

### Step 4 — Handle a response

When the lead responds, it moves to the **Engaged** stage and the automated follow-up sequence stops immediately — so the lead never receives an automated message after a real conversation has started. The intake owner takes over the conversation and works toward a booking.

### Step 5 — Booking

When an appointment is scheduled, the lead moves to the **Booked** stage. The system sends a confirmation and schedules reminders ahead of the appointment.

### Step 6 — Close out

Every lead must end in a defined state:

- **Not a fit** → move to **Disqualified** and record the reason.
- **Full follow-up sequence ended with no response** → move to **Nurture** for long-term, low-frequency contact, rather than being dropped.

## Done when …

A run of this procedure is complete when the lead sits in exactly one of these stages:

- **Booked** — appointment scheduled, confirmation and reminders sent; or
- **Disqualified** — with a recorded reason; or
- **Nurture** — in long-term contact after no response.

No lead remains in an undefined or "lost" state.

## Common questions & edge cases

- **Duplicate lead** — handled in Step 1 by merging into the existing record, never by creating a second one.
- **Lead opts out** — the system stops all messaging immediately and marks the record as opted out. No further automated contact is sent.
- **Intake webhook fails** — if no leads have entered the pipeline for an unusually long period, the intake owner is alerted to check the connection. Silence can mean a broken integration, not just low demand.
- **Lead responds outside business hours** — the lead still moves to Engaged and the automated sequence stops; the intake owner picks it up at the next working time.
- **Wrong or invalid contact details** — the lead moves to Disqualified, with the reason recorded as "invalid contact information".

## Keeping this SOP up to date

This document and the live system must stay in sync. Whenever the pipeline stages, timing, or message templates change, **this SOP is updated in the same step** — not afterwards. Message templates should also be reviewed periodically against current response rates.
