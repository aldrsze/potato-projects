# Evently

## What

Windows Forms desktop event management and check-in system: auto-generated Google Forms for registration, QR tickets, email, webcam check-in, badge printing, live dashboard, and post-event reviews, backed by MySQL.

## Why

Paper attendance sheets and generic sign-up forms cause long entrance lines, check-in mistakes, no capacity tracking, fake tickets, and repeated manual form and email work for every event.

## Done when

- [ ] Admin logs in (username/password), manages users, and connects a Gmail account; Google features disabled until connected.
- [ ] Creating an event yields a working event-specific Google Form link in under 2 minutes, no manual form building.
- [ ] Registrations sync from the form and import from CSV; no ticket issued once an event is full, from either source.
- [ ] Attendee registers and receives a QR ticket by email within 5 minutes of "Send Tickets."
- [ ] Webcam QR check-in updates live attendance in under half a second; same ticket never used twice.
- [ ] Live dashboard shows all sections in PRD 5.4, refreshes without freezing the UI; new check-in within 1s locally, 5s on other stations.
- [ ] Scheduled reminder emails send while app runs, with sent/failed counts recorded.
- [ ] CSV import of up to 500 attendees reports imported/skipped/failed in one step.
- [ ] Review form collects ratings/comments from checked-in attendees only (one per ticket); dashboard shows average and count.
- [ ] Badges preview and print in under 10 seconds.
- [ ] Passwords hashed, never logged; no screen reachable without signing in.
