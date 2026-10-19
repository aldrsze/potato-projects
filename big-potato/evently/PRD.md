# Evently

Status: planning · Started: 2026-10-19

## What

Windows Forms desktop event management and check-in system: auto-generated Google Forms for registration, QR tickets, email, webcam check-in, badge printing, live dashboard, and post-event reviews, backed by MySQL.

## Why

Paper attendance sheets and generic sign-up forms cause long entrance lines, check-in mistakes, no capacity tracking, fake tickets, and repeated manual form and email work for every event.

## Done when

- [ ] Admin logs in (username/password), manages users, and connects a Gmail account; Google features disabled until connected.
- [ ] Creating an event yields a working event-specific Google Form link in under 2 minutes, no manual form building.
- [ ] Registrations sync from the form and import from CSV; no ticket issued once an event is full, from either source.
- [ ] Attendee receives a QR ticket by email; reminders and announcements send with sent/failed counts recorded.
- [ ] Webcam QR check-in updates live attendance; same ticket never used twice.
- [ ] Live dashboard shows all PRD 5.4 sections and refreshes without freezing the UI.
- [ ] Badges preview and print; attendance and reviews export as CSV.
- [ ] Review form collects ratings/comments from checked-in attendees only (one per ticket).
- [ ] Passwords hashed, never logged; no screen reachable without signing in.

## Success

- Event-specific form link in under 2 minutes, no manual building.
- QR ticket emailed within 5 minutes of "Send Tickets."
- Scanner updates live count in under half a second.
- Same ticket used twice, and over-capacity issuance, are always blocked (form and CSV).
- New check-in seen within 1s locally, 5s on another station.
- Dashboard queries under 200 ms at 5,000 tickets, UI never frozen.
- CSV import of up to 500 attendees reports imported/skipped/failed in one step.
- Review sync reports imported/skipped/failed; dashboard matches direct DB queries.

## Out of scope

- Custom-coded registration website (registration uses auto-generated Google Forms).
- Paid tickets or payment services.
- SMS, push notifications, chat-app messages (email only).
- Native iOS or Android apps.
- Linux or macOS support.
- Google sign-in as the app login, two-factor auth, self-service password reset.
- Public review pages, replying to or moderating reviews, reviews from non-attendees.
- Automated unit or integration tests.
