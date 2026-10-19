# Plan — Evently

## Steps

1. MySQL schema (`Schema.sql`): User, Event, Organizer, Ticket, Announcement, Review + constraints and indexes.
2. Models: reflect the 6 tables.
3. Data layer: `Database.cs` and repositories (User, Event, Ticket, Announcement, Review, Dashboard) with raw SQL.
4. Auth: BCrypt hashing, first-run admin setup, login, user management.
5. Google connection: OAuth2 loopback, DPAPI token store, profile "Connect Google".
6. Events: create/edit form with capacity, overview, organizers.
7. Forms API: generate registration form per event; registration sync; CSV import.
8. Tickets: UUID + QR generation; email send via MailKit; announcements and reminder scheduler.
9. Check-in: webcam QR scanning (OpenCvSharp + ZXing), double-scan and capacity safety via conditional update / row lock.
10. Badges: fixed template preview + print.
11. Dashboard: async polling queries, ScottPlot charts, role visibility.
12. Reports: attendance and review CSV export.
13. Reviews: review form generation, request email to checked-in attendees, response sync.

## Notes

- Single WinForms app; Presenter layer keeps logic out of UI code-behind.
- Capacity/double-scan enforced in MySQL, not the UI.
- Smallest working piece first; build bottom-up (schema → models → repos → services → forms).
- Linux or macOS not supported.
