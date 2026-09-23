# Ticket SD-4471

**Opened:** Friday 28 Aug, 09:12
**Reported by:** Priya Raghunathan, Infrastructure
**Assigned to:** *(vacant)*
**Priority:** 2, elevated from 3 on 28 Aug

## What was reported

Monitoring flagged a burst of failed SSH authentication against `web01` in the early hours
of 28 Aug. The alert cleared itself before anyone looked at it, which is why this is a
ticket and not an incident.

Priya's note, verbatim:

> Alert fired at 03:14 and closed at 03:20. I pulled twenty lines around the burst before the
> retention window rolled. Not my area, handing it over. The thing I actually want to know is
> whether anybody got in, because if they did this becomes a different conversation and I need
> to know today.

## What is being asked for

One question, in writing, to someone who is not going to read the log:

**Was the host compromised?**

## What was provided

`auth.log`, twenty lines, pulled by Priya at 09:04 on 28 Aug.

## What was not provided

Nothing else was requested and nothing else was preserved. If the answer needs more than
these twenty lines, say what it needs and why.
