Title: Day-first dates come out flipped: shared parser reads month first (379 reports, 11 tenants)

Covers: 379 reports, merged into #4471, from 11 tenants. Intake tags are unreliable here: 356 are tagged parser, 23 are tagged hint.

Cause: the shared date parser reads every date month first. Tenants that write the day first (for example da-DK, nl-NL, en-GB, cs-CZ, fr-FR, it-IT, pl-PL) get a flipped month, so bookings land on the wrong day.

Affected channels: app 204, email 150, form 25.

Action: keep this on #4471. The fix is already queued.
