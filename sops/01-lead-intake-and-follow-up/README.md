# Lead Intake and Follow-Up for a Local Service Business

> **In one sentence:** Every inbound lead is captured, contacted, and moved toward a booked appointment — so no lead ever ends up in an undefined or "lost" state.

| | |
|---|---|
| **Responsible** | Intake owner (supported by the automation system) |
| **Effective from** | 2026-02-06 |
| **Last updated** | 2026-02-06 |
| **Version** | 1.2 |

---

## Why this SOP exists

Most local service businesses do not lose leads because of bad marketing. They lose them in the gap between a lead arriving and someone actually doing something with it. A form gets filled out on a Friday evening, nobody sees it until Monday, and by then the prospect has already booked with a competitor who replied in ten minutes.

This procedure exists to close that gap structurally, so that lead handling does not depend on someone remembering to check an inbox. The guiding principle behind every step below is simple: **a lead is either being actively worked, or it is in a defined state with a recorded reason. There is no third option.** "Lost", "forgotten", and "I think someone followed up" are not states this system allows.

Everything that follows is downstream of that one decision.

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

**Not covered** — walk-in customers and referrals handled in person. These are deliberately excluded: they arrive through a human conversation that already is the first contact, so forcing them through an automated intake sequence would feel wrong to the customer and add nothing. The system covers the channels where speed and consistency are the bottleneck, not the channels where a person is already in the loop.

The procedure begins the moment a new lead record is created in the CRM by any connected intake source. Intake is automated — under normal operation, no one enters leads by hand. This is intentional: manual entry is the single most common point where leads silently disappear, so the design removes the human from capture entirely and places them where judgment is actually needed, which is the conversation.

## Who is involved

- **Automation system** — handles lead capture, deduplication, first contact, and reminders. In other words, everything that is repetitive, time-sensitive, and does not require judgment.
- **Intake owner** — the team member who monitors the pipeline and handles anything the automation escalates. Their attention is deliberately reserved for real conversations and exceptions, not for routine sending.

This split is the core design idea: **the machine handles speed and consistency, the human handles judgment.** Most failures happen when those two are mixed up — when a person is asked to be fast and consistent, or when automation is asked to make a judgment call.

## What you need beforehand

Before this procedure can run, all of the following must be true:

- The CRM pipeline exists with the six stages listed below.
- Every intake source is connected to the CRM via webhook, and each connection has been verified.
- Webhook endpoints are protected with a shared secret or signature check (see Data and security considerations).
- Approved message templates exist for first contact, reminders, and reactivation.
- Opt-out handling is configured and compliant for every channel in use.

If any of these is not in place, the procedure does not "mostly work" — it fails quietly, which is worse than failing loudly. An unverified webhook looks fine until the day leads stop arriving and nobody notices.

## The pipeline stages

A lead moves through six clearly defined stages. The number is deliberate: few enough that anyone can hold the whole pipeline in their head, detailed enough that the state of any lead is unambiguous.

| Stage | Meaning |
|-------|---------|
| **1. New Lead** | Created by intake, not yet contacted. |
| **2. Contacted** | First outreach has been sent. |
| **3. Engaged** | The lead has replied or otherwise responded. |
| **4. Booked** | An appointment is scheduled. |
| **5. Disqualified** | The lead is not a fit; a reason is recorded. |
| **6. Nurture** | No response after the follow-up sequence; moved to long-term contact. |

A note on what is *not* here: there is no "in progress" or "working on it" stage. Those are the stages that feel productive but mean nothing, because they describe an intention rather than a fact. Every stage in this list is a fact about the lead that anyone can verify by looking.

## Step by step

### Step 1 — Capture and deduplicate

When a lead record is created, the system checks for an existing record with the same phone number or email address.

- **If a match is found:** the new information is merged into the existing record — no duplicate is created.
- **If no match is found:** the new record is kept.

Either way, the lead is placed in the **New Lead** stage.

**Why deduplication comes first, before anything else:** a returning prospect who fills out a second form should never receive a "nice to meet you" first-contact message as if they were a stranger. It signals that the business is not paying attention, and it splits one person's history across two records so that neither tells the full story. Catching duplicates at the very first step keeps the lead's history intact and the messaging coherent. It is cheap to do here and expensive to untangle later.

### Step 2 — First contact

Within a short, defined window after capture (for example, **five minutes**), the system sends the first-contact message on the same channel the lead used. The lead moves to the **Contacted** stage.

**Why the window is minutes, not hours:** lead response rates are extremely time-sensitive. The difference between replying in five minutes and replying in an hour is not incremental — it is often the difference between a conversation and silence. The window is short on purpose, and it is automated precisely because no human can reliably hit a five-minute target across evenings, weekends, and busy days. This is the clearest case in the whole procedure of the machine doing what a person structurally cannot.

**Why the same channel:** a lead who used a form expects a reply where they are, not a cold phone call. Matching the channel respects how the lead chose to make contact and keeps the response rate high.

### Step 3 — Follow-up sequence

If the lead does not respond, the system sends a defined sequence of follow-up messages spaced over several days (for example, on **day 1, day 3, and day 6**). Every message is logged on the lead record. The lead stays in the **Contacted** stage until it either responds or the sequence ends.

**Why a fixed sequence instead of "follow up when you can":** the spacing is a deliberate balance. Too aggressive and the business looks desperate and risks an opt-out; too sparse and the lead goes cold. A fixed, pre-decided rhythm removes the daily judgment call ("is it too soon to message them again?") and makes follow-up something that simply happens rather than something that depends on someone's mood or workload that day.

**Why every message is logged:** when the intake owner finally picks up a conversation, they need to see exactly what the lead has already received. Nothing erodes trust faster than a team member who clearly has no idea what was already said.

### Step 4 — Handle a response

When the lead responds, it moves to the **Engaged** stage and the automated follow-up sequence stops immediately — so the lead never receives an automated message after a real conversation has started. The intake owner takes over the conversation and works toward a booking.

**Why the automation stops the instant a human replies:** this is the most important safeguard in the procedure. An automated "just checking in!" landing in the middle of a real conversation is the single most visible way to show a prospect they are talking to a system, not a person. The hard rule — a human reply ends the automation, with no delay — protects the one thing that actually closes bookings, which is the real conversation.

### Step 5 — Booking

When an appointment is scheduled, the lead moves to the **Booked** stage. The system sends a confirmation and schedules reminders ahead of the appointment.

**Why reminders are scheduled here and not left to chance:** the booking is not the finish line — a no-show is just a lost lead with extra steps. Reminders are set at the moment of booking so that the follow-through is guaranteed by the system rather than depending on anyone remembering.

### Step 6 — Close out

Every lead must end in a defined state:

- **Not a fit** → move to **Disqualified** and record the reason.
- **Full follow-up sequence ended with no response** → move to **Nurture** for long-term, low-frequency contact, rather than being dropped.

**Why "no response" leads go to Nurture instead of being deleted:** silence is not the same as rejection. A lead who did not reply this month may simply have been busy, not uninterested. Moving them to a low-frequency long-term track keeps the door open without burning the contact, and it means the marketing spend that generated that lead is not thrown away after six days.

**Why disqualification always requires a recorded reason:** "Disqualified" with no reason is indistinguishable from "someone gave up". The recorded reason makes the decision auditable, lets patterns surface over time (if many leads are disqualified for the same reason, that is a signal about the marketing, not the leads), and keeps the stage honest.

## Done when …

A run of this procedure is complete when the lead sits in exactly one of these stages:

- **Booked** — appointment scheduled, confirmation and reminders sent; or
- **Disqualified** — with a recorded reason; or
- **Nurture** — in long-term contact after no response.

No lead remains in an undefined or "lost" state.

## Common questions & edge cases

The edge cases below are not afterthoughts. Each one is a place where a naive version of this system would fail silently, so each is handled by explicit design.

- **Duplicate lead** — handled in Step 1 by merging into the existing record, never by creating a second one. The reasoning is covered in Step 1: one person, one history.
- **Lead opts out** — the system stops all messaging immediately and marks the record as opted out. No further automated contact is sent. This overrides every other rule in the procedure: an opt-out is not a step in the flow, it is a hard stop that applies everywhere, both because it is the legal requirement and because contacting someone who asked you not to destroys trust permanently.
- **Intake webhook fails** — if no leads have entered the pipeline for an unusually long period, the intake owner is alerted to check the connection. This matters because the dangerous failure here is the *quiet* one: a broken webhook looks exactly like a slow week. Treating an unusual silence as a possible fault, rather than assuming low demand, is what turns a silent failure into a loud one.
- **Lead responds outside business hours** — the lead still moves to Engaged and the automated sequence stops; the intake owner picks it up at the next working time. The automation must not keep messaging into an open conversation just because the office is closed.
- **Wrong or invalid contact details** — the lead moves to Disqualified, with the reason recorded as "invalid contact information". This keeps the distinction clean between a lead the business chose not to pursue and a lead it simply could not reach.

## Data and security considerations

A lead record is personal data — a name, a phone number, an email address, and a history of contact. The procedure treats it that way, not as anonymous pipeline material. The points below are deliberate design choices, not optional extras.

- **Webhook endpoints are protected.** An intake webhook is an open door into the CRM: anything that can reach it can write a record. Each endpoint is secured with a shared secret or a signature check, so the CRM only accepts leads from sources it actually trusts. Without this, anyone who learns the URL can inject fake or malicious leads, and the pipeline would have no way to tell them apart from real ones.
- **CRM access is limited to the people who need it.** Access to the pipeline is granted by role, not by default. The fewer people who can read and edit lead records, the smaller the surface for both accidental and deliberate misuse. Access is reviewed when someone joins or leaves.
- **Lead data has a defined lifespan.** Personal data is not kept indefinitely "just in case". A retention period is set, and once a lead has been in a closed state (Disqualified, or Nurture with no engagement) beyond that period, its personal data is deleted or anonymized. Keeping data with no active purpose is a liability, not an asset.
- **Consent and opt-out status live on the record.** Whether a lead has consented to contact, and whether they have opted out, is stored explicitly on the lead record — not inferred, not held in someone's memory. Every automated action checks this status first. This is what makes opt-out a reliable hard stop rather than a hopeful intention.
- **The principle of least surprise applies to the lead.** A lead is contacted only on the channel they used, only about what they enquired about, and only until they ask the business to stop. Nothing in the system contacts a person in a way they would not reasonably expect.

None of this slows the procedure down. It is built in so that doing the fast thing and doing the safe thing are the same thing.

## Design principles behind this SOP

If this document had to be reconstructed from scratch, these five principles would be enough to rebuild it:

1. **Every lead is always in exactly one defined state.** No "lost", no "in progress", no ambiguity. The stage list is the complete set of places a lead can be.
2. **The machine handles speed and consistency; the human handles judgment.** Failures cluster wherever those two are mixed.
3. **Automation yields to a real conversation instantly.** The moment a human is talking to the lead, the system steps back.
4. **Silent failure is the worst failure.** Wherever something can break quietly — an unverified webhook, an unusual stretch with no leads — the system is designed to make the silence visible.
5. **Lead data is personal data and is treated as such.** Access is limited, endpoints are secured, data has a defined lifespan, and consent status is explicit and always checked.

The specific timings, channels, and templates can all change. These five principles should not.

## Keeping this SOP up to date

This document and the live system must stay in sync. Whenever the pipeline stages, timing, or message templates change, **this SOP is updated in the same step** — not afterwards. Message templates should also be reviewed periodically against current response rates.

A practical test for whether this SOP is still healthy: a new team member should be able to read it and not just follow the steps, but understand *why* each step is the way it is. The moment the reasoning and the live system disagree, one of them is wrong — and that is the signal to fix it.
