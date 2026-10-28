Covers: 379 reports, merged into #4471, from 11 tenants. Intake tags are unreliable here: 356 are tagged parser, 23 are tagged hint. 5 of them the desk read as a one-day move; they are filed here by tenant, as the desk counts them.

Cause: the shared date parser reads every date month first. Tenants that write the day first (for example da-DK, nl-NL, en-GB, cs-CZ, fr-FR, it-IT, pl-PL) get a flipped month, so bookings land on the wrong day.

Affected channels: app 204, email 150, form 25.

Status: fixed by engineering in `fix(dates): parse dd/mm for eu locales`. #4471 closed 05 Oct.
