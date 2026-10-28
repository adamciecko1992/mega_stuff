Covers: 33 reports, merged into #4471, from 3 tenants (copper.studio, alder.physio, pale.harbour). All 33 came through the booking-v3 form. Intake tags are unreliable here: 18 are tagged hint, 15 are tagged parser.

Cause: the booking-v3 form shows MM/DD/YYYY under the date field. Its tenants write the day first (de-DE, pt-PT, es-ES). People type what the hint says, month first, and the form reads it in the tenant's day-first order, so the date is flipped. This is a different bug from the shared parser issue, and it has no ticket of its own.

Action: filed as its own ticket, separate from #4471. The fix shipped; closing this ticket.
