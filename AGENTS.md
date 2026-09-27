# AGENTS.md

Repo: single-file Paris itinerary site (`index.html`) on GitHub Pages.

## Before every commit: privacy, PII, and whereabouts check

Do not stage or commit until all of these pass.

1. Scan staged files and the working tree for PII:
   - street addresses (e.g. Rue, Avenue, Bd with a number)
   - email addresses
   - phone numbers
   - home GPS coordinates (the public station pin 48.8035,2.3174 is allowed; anything more precise is not)
   - full names of private individuals, booking references, API keys
2. Scan for anything revealing whereabouts on a specific date:
   - calendar dates or date ranges for the trip (weekday names alone are allowed; exact dates are not)
   - flight numbers, times, terminals, confirmation codes
   - dated bookings or reservations (restaurant, museum, boat) with a day attached
   - statements like "we will be at X on <date>" or countdowns tied to departure
   - EXIF or metadata in added images that contains dates or locations
   The rule: a stranger reading the page must never learn where the family is on any given calendar day.
3. Scan git history for the same, since a push publishes history too:
   `git log -p --all | grep -i -E "assia|djebar|@|tel:|\+33 ?[16]|november [0-9]|20[0-9]{2}-[0-9]{2}|flight|booking|confirmation"`
4. Allowed: public museum, restaurant, and station addresses already on the page; weekday labels without dates.
5. If anything is found, remove it from files AND from history (rewrite before pushing; never force-push without explicit user approval). Re-run the scan. Only commit when clean.
