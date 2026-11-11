---
name: sc26-register
description: Plan and register for SC26 (Chicago, Nov 15–20, 2026) receptions, parties, and social events listed in this repo's README. Use when the user wants to pick SC26 events, check time/location conflicts, or fill out RSVP/registration forms — through the Claude in Chrome browser tools when they are connected, otherwise by handing back a click-through checklist.
argument-hint: "[optional: days, companies, or events you're interested in]"
---

# SC26 reception registration helper

The source of truth is `README.md` at the repo root (the day-by-day tables). Read it fresh every time you run — events, links, and sold-out status change during the week.

## 1. Ask once for what you need

Ask only for what the user hasn't already told you, in a single short message:

- **Days in Chicago** and **SC26 badge type** (Technical Program, Exhibits, Exhibitor, Students@SC). Several receptions are badge-only or included with specific badges.
- **What they're after** — specific companies, students / early-career events, big parties, smaller networking, etc.
- **Form details** — full name, email, organization, job title. Use only what the user gives you; never guess or invent values. Do not write these details into any file in the repo.

## 2. Propose a plan, then wait

From the README tables, build a shortlist:

- Drop events that are ❌ sold out / closed, that need a badge the user doesn't have, or fall on days they aren't there.
- Flag overlaps (see the README's "Scheduling collisions" section) and travel time between venues using the 📍 addresses — e.g. River North ↔ McCormick Place / Museum Campus is a cab ride, not a walk.
- Sort each pick into what it needs:
  - **Register online** — the row has a registration link.
  - **Nothing to do** — walk-up, booth, or included with the badge.
  - **Request / invite** — needs host approval.
  - **No public link** — tell the user to check the host's site or their inbox.

Show the plan as a short table (time, event, venue, action) and let the user confirm or edit it **before registering anything**.

## 3. Register

### With browser tools (Claude in Chrome connected, e.g. Claude Code started with `claude --chrome`)

Go through the confirmed **Register online** events one at a time:

1. Open the event's registration link from the README in a new tab.
2. If the page needs a login (Luma, Eventbrite, a company portal), a CAPTCHA, or payment, stop and ask the user to do that step in the browser, then continue once they say so.
3. Fill in the form with the user's details. For any field you don't have an answer for (dietary needs, "how did you hear about us", phone number, etc.), ask instead of guessing. Leave marketing opt-in and newsletter checkboxes **unchecked** unless the user says otherwise.
4. Before clicking the final Register / RSVP / Submit button, show the user exactly what you filled in and get an explicit **yes for this event**. Then submit and report the confirmation message.
5. If the page says sold out, closed, or shows a different time or venue than the README, tell the user and note it for a README fix.

### Without browser tools

Output a checklist the user can click through: time, event, 📍 venue + map link, registration link, and the action needed. Mention that installing the Claude in Chrome extension and restarting with `claude --chrome` lets you fill in the forms for them.

## 4. Wrap up

- Summarize: ✅ registered, ⏳ pending approval, 🚶 walk-up / badge-only, ⏭️ skipped (and why).
- Offer to create an `.ics` calendar file for the confirmed events (time zone `America/Chicago`, venue address in the location field). Save it outside the repo or as a `*.ics` file, which is git-ignored.
- If you found anything new or changed (a new event, a time change, sold out, a public registration link for a row marked "no public link yet"), offer to draft the README edit as a PR.

## Rules

- Never submit a form, accept terms, or create an account without the user's explicit confirmation for that specific event.
- Never type passwords, payment details, or one-time codes. The user does those steps.
- Never commit the user's personal details to the repo.
