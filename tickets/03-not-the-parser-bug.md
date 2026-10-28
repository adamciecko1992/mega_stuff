Covers: 5 reports, merged into #4471 by the subject-match dedupe rule (decision 0001), from 5 tenants: kettle.books, alder.physio, nine.lanterns, pale.harbour, lantern.row.

These reports read like the parser bug (a date on the wrong day) but their dates do not move the way a month/day swap moves a date. A swap turns 12 May into 5 December, a different date entirely. These move by exactly one day, or only in one month, or differ by the reader's timezone:

- kettle.books: "Invite says Tuesday 12 May. Calendar says Monday 11 May." One day, same month.
- alder.physio: "Every booking in June is one day off. Only June." One month only.
- pale.harbour: "Client in Lisbon got Tuesday. Client in Toronto got Monday. Same meeting." Same instant, different local day.
- lantern.row: "Tuesday 6 October showed as Monday." One day, same date.
- nine.lanterns: "The invite arrived before I made the booking." Not a date swap at all.

Cause: not diagnosed here. The pattern across four of the five (one day, one month, cross-timezone) points to a timezone or DST boundary bug, not the shared parser's month-first read. The fifth (nine.lanterns) may be unrelated noise; worth a second look.

Action: pull these 5 out of #4471 and out of the parser count. They were merged by subject line, not by cause. Track as their own problem.
