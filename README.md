# Operations SOPs

A small collection of standard operating procedures for the kind of
operations and automation work I do: lead handling, content workflows,
and the systems that connect them.

## About this collection

These are **example SOPs**, written to a generic standard.

SOPs from live client projects contain confidential details — client
names, internal tooling, account structures, and process specifics that
belong to the client, not to me. I do not share those. Treating client
work as confidential is part of doing this job properly, especially when
the work involves a client's leads and customer data.

So instead, these documents describe the same processes at a generic,
reusable level. They contain no client names, no domains, no internal
identifiers. What they do show is exactly how I structure a process and,
just as importantly, the reasoning behind each decision: why a step is
built the way it is, what was deliberately left out, and which failure
modes the design is guarding against.

If you want to see how I think about an operational process, these are a
faithful representation of it. They are just deliberately stripped of
anything that would belong to a specific client.

## What's in here

| No. | SOP | What it covers |
|-----|-----|----------------|
| 01 | [Lead Intake and Follow-Up](sops/01-lead-intake-and-follow-up/) | How an inbound lead is captured, contacted, and moved toward a booked appointment — so no lead ends up in an undefined or "lost" state. |
| 02 | [Content Publish-and-Send Workflow](sops/02-content-publish-and-send-workflow/) | How a finished piece of content is published and turned into a newsletter in one controlled flow, with sending kept as a deliberate human decision. |

## How these are written

Every SOP in this collection follows the same shape:

- **Why this SOP exists** — the core problem and the guiding principle.
- **Step by step** — what happens, each step paired with *why* it is built that way.
- **Common questions & edge cases** — the places a naive version would fail silently.
- **Data and security considerations** — how personal data is protected by design.
- **Design principles** — the handful of principles the whole document rests on.

The test for a healthy SOP: a new team member should be able to read it
and understand not just *what* each step does, but *why*. If the
reasoning and the live system ever disagree, one of them is wrong.

## How the repository is organized

- **Each SOP has its own folder** under `sops/`, numbered and descriptively
  named, e.g. `sops/01-lead-intake-and-follow-up/`. The number gives a
  recognizable order; the name says immediately what it covers.
- Inside each SOP folder:
  - `README.md` — the SOP itself (shown automatically when you open the folder).
  - `assets/` — optional folder for screenshots, templates, or attachments.
- New SOPs are created from the template `templates/sop-template.md`.
