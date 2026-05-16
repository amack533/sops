# Content Publish-and-Send Workflow

> **In one sentence:** A finished piece of content is published to the website and turned into a newsletter in one controlled flow — so publishing and audience contact happen together, reliably, instead of as two disconnected manual jobs.

| | |
|---|---|
| **Responsible** | Content owner (supported by the automation system) |
| **Effective from** | 2026-03-02 |
| **Last updated** | 2026-03-02 |
| **Version** | 1.0 |

---

## Why this SOP exists

In most small teams, publishing an article and emailing the audience about it are two separate jobs done by hand. The article goes live, and then — maybe that day, maybe next week, maybe never — someone copies it into an email tool, reformats it, fixes the images, writes a subject line, and sends it. The two steps drift apart. Content gets published with no announcement, or a newsletter goes out pointing at a page that was quietly changed afterwards.

This procedure exists to make publishing and sending a single, deliberate act. The guiding principle is: **the newsletter is generated from the published content, not rebuilt alongside it.** There is one source of truth — the published piece — and the email is derived from it. If the two ever say different things, that is a bug, not a normal state.

The second principle is just as important: **sending is always a human decision.** The system removes all the repetitive work — formatting, image handling, list management — but it never decides on its own that something is ready to reach the audience.

## What this is about

This procedure defines how a finished piece of content moves from "written" to "published on the site and delivered to the newsletter audience". When it runs correctly, the result is:

- the content live on the website, and
- a newsletter derived from that exact content, either sent or held as a reviewed draft awaiting an explicit send.

There is no state where content is live but the newsletter is an untracked manual to-do.

## When to use this

**Covered** — regular content intended for both the website and the newsletter audience: articles, posts, announcements.

**Not covered** — content meant for only one channel. A website page that is not an announcement (a service page, a legal page) does not trigger a newsletter. A pure broadcast email with no published counterpart (a one-off promotion) is a different process and is out of scope here. This SOP is specifically for content that is meant to exist in both places.

The procedure begins when a piece of content is marked as ready to publish. It does not begin while the content is still being drafted or edited.

## Who is involved

- **Automation system** — handles everything repetitive and deterministic: publishing the content, processing images, generating the newsletter from the published piece, managing the subscriber list, and sending once a send is approved.
- **Content owner** — makes the judgment calls: that the content is ready, that the generated newsletter looks right, and that it should go out. The system does not send without this person's explicit action.

The same split as in the lead procedure applies here: **the machine handles the repetitive and deterministic work, the human makes the judgment calls.** Formatting an email is repetitive. Deciding the audience should receive it is judgment.

## What you need beforehand

Before this procedure can run, all of the following must be true:

- The website target for the content exists and is reachable by the automation.
- The subscriber list is in place, and every subscriber on it has confirmed their subscription (see Data and security considerations).
- A newsletter template exists, matching the brand, and has been tested across common email clients.
- Image processing is configured, so images are resized and optimized for both web and email automatically.
- A sender identity and domain authentication for outgoing email are set up and verified.

If any of these is missing, the procedure fails in a visible way — a broken layout, a missing image — rather than silently sending something wrong to the whole list.

## The content states

A piece of content moves through clearly defined states:

| State | Meaning |
|-------|---------|
| **Draft** | Being written or edited. Not in scope for this procedure. |
| **Ready to publish** | Marked as finished; this is the trigger for the procedure. |
| **Published** | Live on the website. |
| **Newsletter generated** | A newsletter draft has been derived from the published content. |
| **Sent** | The newsletter has been delivered to the audience. |

There is no "published, newsletter pending somewhere" state. Once content is Published, the newsletter is generated immediately and automatically. The only thing left to a human after that is the decision to send.

## Step by step

### Step 1 — Publish the content

When the content is marked Ready to publish, the system publishes it to the website. Its state becomes Published.

**Why publishing is the trigger, not a separate manual step:** the published piece is the single source of truth for everything downstream. Generating the newsletter from anything earlier — a draft, a copy-paste — means the email and the live page can disagree. Making the published piece the trigger guarantees the newsletter is always derived from exactly what the audience will see if they click through.

### Step 2 — Process images

As part of publishing, every image in the content is processed automatically: resized and optimized into appropriate versions for the website and for email.

**Why image processing is automated and not left to the person:** images are the most common reason a newsletter looks broken or loads slowly. A full-resolution photo that is fine on a website can be far too heavy for an email. Handling this in code, every time, removes a tedious and error-prone manual step and means the email is never the place where image problems first show up.

### Step 3 — Generate the newsletter

The system generates a newsletter from the published content, placing it into the newsletter tool. Its state becomes Newsletter generated. The newsletter is created as a **draft**, not sent.

**Why the newsletter is generated from the published piece, and why it stops at a draft:** there were two ways to produce the email. One is to treat the newsletter as its own piece of writing — composed separately, in the email tool, by a person who adapts the content for that format. That gives the most control over the email specifically. The other is to derive the newsletter automatically from the published content. Deriving it was chosen, because a separately written newsletter is a second source of truth: the moment the published piece is edited, the email silently disagrees with it, and nobody is guaranteed to notice. Deriving from the published piece means the two are consistent by construction, and a content change is one regeneration rather than a manual re-do. The cost of that choice is less hand-tuning of the email — which is exactly why generation stops at a draft rather than sending. The system does all the repetitive work, then deliberately hands control back: the draft exists, but a human still sees it before the audience does. Automatic derivation and automatic sending are two different decisions, and only the first one is safe to make without a person.

### Step 4 — Review

The content owner reviews the generated newsletter: subject line, layout, images, links, and that the link to the published content is correct.

**Why the review step is mandatory and cannot be skipped:** there is a real efficiency argument against it. The system already formatted the email, handled the images, and built it from the content — so why not let a trusted, routine post go straight out and save the step? The answer is the shape of the risk. Skipping review is fine ninety-nine times and catastrophic on the hundredth, because a newsletter reaches the entire audience at once and cannot be recalled. A wrong subject line, a broken link, a generation glitch — unreviewed, it hits every subscriber simultaneously and damages trust across the whole list in one action. The review step costs a minute or two; a bad send costs far more and cannot be undone. When the downside is that asymmetric, the consistent small cost is the right trade. This is the one place in the procedure that deliberately refuses to optimize for speed.

### Step 5 — Send

When the content owner approves it, they trigger the send. The system delivers the newsletter to the current confirmed subscriber list. The state becomes Sent.

**Why the send is an explicit human action:** everything before this point is reversible or invisible to the audience. The send is neither. Making it a distinct, deliberate action — rather than the automatic end of the flow — keeps the decision to contact the audience firmly with a person.

## Done when …

A run of this procedure is complete when:

- the content is **Published** on the website, and
- the derived newsletter is either **Sent** to the confirmed subscriber list, or held as a reviewed draft with an explicit decision to send later.

There is no leftover manual task. The content is not live with an untracked "should email about this" floating in someone's head.

## Common questions & edge cases

- **Content is edited after publishing** — the published piece stays the source of truth, so the newsletter is regenerated from the updated content. If the newsletter has not been sent yet, it is simply replaced — no decision needed. If it has already been sent, the procedure deliberately does *not* try to "correct" it. A follow-up correction email could be sent automatically, but that would mean the system decides, on its own, to contact the whole audience a second time — exactly the irreversible, audience-facing action that the design keeps in human hands. So a post-send change is surfaced to the content owner as a judgment call: minor fixes usually need nothing, a significant change may warrant a correction. The system regenerates and informs; the person decides whether the audience hears about it.
- **Image fails to process** — publishing does not proceed silently with a broken image. The failure is surfaced to the content owner so it can be fixed before anything reaches the audience.
- **Newsletter is generated but never sent** — this is an allowed end state, as long as it was a decision. The content stays Published; the newsletter stays a reviewed draft. The procedure does not force a send.
- **A subscriber unsubscribes** — handled by the subscriber system at send time: an unsubscribed address is not included in the send. Unsubscribe status is always honored on the next send, with no exceptions.
- **Send fails partway through** — the system tracks which subscribers were delivered to, so a retry resumes rather than sending the newsletter twice to the same people.

## Data and security considerations

A subscriber list is personal data — names and email addresses of people who agreed to be contacted. The procedure treats it accordingly.

- **Every subscriber is a confirmed subscriber.** A subscriber joins the list only after explicitly confirming their subscription. An address that is submitted but never confirmed never receives a newsletter. This protects both the recipient, who is only contacted if they actually asked to be, and the sender, whose domain reputation depends on not mailing unconfirmed addresses.
- **Unsubscribing is immediate and permanent.** Every newsletter contains a working unsubscribe option, and an unsubscribe is honored from that point on without exception. Unsubscribe status lives on the subscriber record and is checked on every send.
- **The subscriber list is access-controlled.** Only the people who need it can view or export the list. A subscriber list is a common target precisely because it is a clean set of valid personal contacts; it is treated as sensitive, not as a casual asset.
- **Sender identity is authenticated.** The sending domain is properly authenticated, so the newsletter is verifiably from the business. This protects the audience from spoofing and keeps legitimate mail out of spam folders.
- **The audience is contacted only as they expect.** Subscribers receive the content they signed up for, at a reasonable frequency, with a clear way out. The system is not used to contact the list in ways a subscriber would not have anticipated when they confirmed.

As in the lead procedure, none of this is friction added on top. Confirmed-only lists and honored unsubscribes are also what keep deliverability high — the safe path and the effective path are the same path.

## Design principles behind this SOP

If this document had to be reconstructed from scratch, these five principles would be enough to rebuild it:

1. **The published content is the single source of truth.** The newsletter is derived from it, never maintained in parallel.
2. **Generation and sending are separate.** The system does all the repetitive work automatically, but never sends on its own.
3. **The send is always a deliberate human decision.** It is the one irreversible, audience-facing action, so it stays with a person.
4. **Failures surface before the audience sees them.** A broken image or a failed step stops the flow loudly, rather than reaching the whole list.
5. **The subscriber list is personal data and is treated as such.** Confirmed subscribers only, unsubscribes always honored, access controlled.

The specific template, channels, and timing can change. These five principles should not.

## Keeping this SOP up to date

This document and the live system must stay in sync. Whenever the content states, the template, or the sending setup change, **this SOP is updated in the same step** — not afterwards.

The same health test applies as for any SOP in this collection: a new team member should be able to read it and understand not just what each step does, but why it is built that way. If the reasoning here and the live system disagree, one of them is wrong, and that is the signal to fix it.
