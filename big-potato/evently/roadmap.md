# Roadmap — Evently

| # | Milestone | Outcome | Status | Depends on | Risk |
| --- | --- | --- | --- | --- | --- |
| 1 | Schema + models + repositories | 6 MySQL tables exist; each repository reads and writes its table | todo | — | Schema churn later |
| 2 | Auth & user management | Admin logs in; users managed; no screen reachable without signing in | todo | 1 | — |
| 3 | Google connection | Profile connects a Gmail account; Google features disabled until connected | todo | 1 | OAuth testing-mode limits |
| 4 | Events & organizer management | Event created/edited with capacity and organizers | todo | 1, 2 | — |
| 5 | Forms, registration sync & CSV import | Event yields a working form link under 2 min; capacity enforced for form and CSV | todo | 3, 4 | Forms API can't close a form |
| 6 | QR tickets & email | Ticket emailed; announcements/reminders sent with counts | todo | 5 | Scheduled mail only while app runs |
| 7 | Webcam check-in & badges | Scan updates live count; same ticket blocked twice; badge previews and prints | todo | 6 | Webcam varies by machine |
| 8 | Live dashboard & reports | All PRD 5.4 sections refresh without freezing; attendance/reviews export CSV | todo | 6 | Query speed at 5,000 tickets |
| 9 | Event reviews | Checked-in attendees submit once; sync reports imported/skipped/failed | todo | 7 | Email-only identity |
| 10 | End-to-end event run | One event goes create → form → register → ticket → check-in → badge → review | todo | 2–9 | Integration bugs |

## Details

### 1. Schema + models + repositories
- Done when: `Schema.sql` creates User, Event, Organizer, Ticket, Announcement, Review with constraints/indexes; models match; repos run raw SQL.
- Tasks: write schema; models; `Database.cs`; User/Event/Ticket/Announcement/Review/Dashboard repos.
- Unknowns: none.

### 2. Auth & user management
- Done when: BCrypt hashing; first-run admin setup; login; user management; no screen reachable unauthenticated.
- Tasks: hashing; first-run flow; login; user CRUD; route guard.
- Unknowns: none.

### 3. Google connection
- Done when: OAuth2 loopback connects Gmail; token stored with DPAPI; Google features gated until connected.
- Tasks: loopback OAuth2; DPAPI token store; profile "Connect Google"; gate features.
- Unknowns: OAuth verification needed for public distribution.

### 4. Events & organizer management
- Done when: create/edit event with capacity; overview lists events; organizers assigned.
- Tasks: create/edit form; overview; organizer assignment.
- Unknowns: none.

### 5. Forms, registration sync & CSV import
- Done when: form generated per event, link ready under 2 min; registrations sync; CSV import up to 500 reports imported/skipped/failed; full event issues no ticket from either source.
- Tasks: Forms API generation; registration sync; CSV import; capacity skip logic.
- Unknowns: form closing enforced in MySQL only.

### 6. QR tickets & email
- Done when: UUID + QR generated; ticket emailed within 5 min of "Send Tickets"; announcements and reminders send with sent/failed counts.
- Tasks: QR generation; MailKit send; ticket email; announcement/reminder scheduler.
- Unknowns: overdue emails send only on next launch.

### 7. Webcam check-in & badges
- Done when: webcam scan updates live count in under 0.5s; same ticket never used twice; badge previews and prints.
- Tasks: OpenCvSharp + ZXing scan; conditional update / row lock; live count; badge template + print.
- Unknowns: detection on Windows 10 and 11.

### 8. Live dashboard & reports
- Done when: all PRD 5.4 sections; queries under 200 ms at 5,000 tickets; UI never frozen; attendance and review CSV export.
- Tasks: async polling queries; ScottPlot charts; role visibility; CSV export.
- Unknowns: none.

### 9. Event reviews
- Done when: review form generated; request email to checked-in attendees; one review per ticket; sync reports imported/skipped/failed.
- Tasks: review form generation; request email; response sync; one-per-ticket check.
- Unknowns: someone could submit for another attendee (accepted for local/school use).

### 10. End-to-end event run
- Done when: one event goes create → form → register → ticket → check-in → badge → review without manual DB work.
- Tasks: run the full flow; fix integration bugs; verify capacity and double-scan; verify dashboard matches DB.
- Unknowns: none.

Next up: 1 — Schema + models + repositories.
