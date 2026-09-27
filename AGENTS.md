# AGENTS.md

Repo: single-file Paris itinerary site (`index.html`) on GitHub Pages.

## Before every commit: privacy and PII check

Do not stage or commit until all of these pass.

1. Scan staged files and the working tree for PII:
   - street addresses (e.g. Rue, Avenue, Bd with a number)
   - email addresses
   - phone numbers
   - home GPS coordinates (the public station pin 48.8035,2.3174 is allowed; anything more precise is not)
   - full names of private individuals, booking references, API keys
2. Scan git history for the same, since a push publishes history too:
   `git log -p --all | grep -i -E "assia|djebar|@|tel:|\+33 ?[16]"`
3. Allowed: public museum, restaurant, and station addresses already on the page.
4. If anything is found, remove it from files AND from history (rewrite before pushing; never force-push without explicit user approval). Re-run the scan. Only commit when clean.
