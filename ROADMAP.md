# Roadmap

Ordered by what would improve the coaching most, not by what's easiest.

## Next

- **Recalibrate readiness against outcomes.** Once there are ~30 check-ins paired with debriefs, check whether an amber morning actually predicted a bad session. If it didn't, the thresholds are wrong. This is the single biggest quality-of-coaching improvement available and it needs data, not code.
- **Plan overrides that persist.** Right now the week is regenerated from rules every time. Moving Thursday to Friday should stick.
- **Ski benchmark loop.** A named double-poling route you repeat, so the Ski section becomes a trend instead of a list.
- **Session history on the plan.** Show what you actually did next to what was planned, so the gap is visible.

## Later

- **Garmin sync instead of CSV export.** Garmin's API requires developer approval and OAuth, which needs a server. A middle path: Garmin can auto-export to Dropbox or Google Drive, and the app could read from a shared link.
- **Sleep and HRV import.** Garmin Connect gives Body Battery and sleep score, but not through the CSV activity export. Same blocker as above.
- **Long-run fuelling tracker.** Carbs per hour against how the last 5 km felt.
- **Injury log.** Niggles with dates, so a pattern is visible before it's an injury.
- **Multi-race planning.** Currently one goal race. A December ski race plus a March half needs two overlapping phase timelines.

## Deliberately not doing

- **Automatic plan changes from the AI chat.** The coach argues, you decide. If it could rewrite the plan, you'd stop reading it.
- **HRV-driven daily readiness.** Too noisy to act on day to day at this training volume, and it invites over-reading.
- **A training stress score.** Garmin already computes one and it isn't in your export. Hours and sessions are cruder and harder to fool yourself with.
- **Accounts, sync, a backend.** The moment there's a server there's a thing to maintain. Back up the JSON instead.

## Known rough edges

- The Limit line on the week strip is a visual reference, not a constraint. Nothing stops you exceeding it.
- The acute:chronic ratio is calculated from hours, which treats an easy hour and a threshold hour as equal. It is a blunt warning light, not a load model.
- If you import the same Garmin CSV twice, duplicates are skipped by date + type + duration. Two genuinely different sessions with identical values on one day would collide.
- Pool swims are converted from metres to kilometres on import by assuming any distance over 100 is metres. A 150 km ride would be fine; a 150 m swim would not.
