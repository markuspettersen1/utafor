# Endurance coach

A training coach for one athlete: half marathon, base lifts, winter double poling. Runs in a browser, stores everything on your phone, has no server and no build step. Open `index.html` and it works.

It plans your week, tracks fitness, takes a debrief after each session, and lets you argue with the plan.

---

## Start here

1. Open `index.html` in a browser.
2. Go to **You** and fix the placeholders: race name, real race date, goal time, max HR, weight, location. The race date is currently a guess.
3. Go to **Log** → **Import** and drop in `data/Activities.csv`.
4. Go to **Metrics** and check whether the VO2max estimate looks like you. If it doesn't, add a recent race or hard time trial under **You → Personal records** — that's the input the whole model hangs on.

Your data lives in browser local storage. It is not synced anywhere. **Use Back up data before you clear your browser history or switch phones.**

---

## Putting it on GitHub so you can use it from your phone

You need a free GitHub account. Everything below is done once.

### 1. Make the repository

On [github.com](https://github.com), click **+** → **New repository**. Name it `endurance-coach`. Leave it public (GitHub Pages is free for public repos) or make it private if you'd rather — Pages works on private repos on the free plan too now, but public is simpler. Don't tick "Add a README", you already have one.

### 2. Get the files up there

The easiest route, no command line: on the new empty repo page, click **uploading an existing file**, then drag in every file and folder from this project. Write "first version" in the commit box and click **Commit changes**.

### 3. Turn on GitHub Pages

Repo → **Settings** → **Pages** → under *Source* choose **Deploy from a branch**, branch `main`, folder `/ (root)`. Save. After a minute your app is live at:

```
https://<your-username>.github.io/endurance-coach/
```

Open that on your phone, then **Share → Add to Home Screen**. It behaves like an app.

### 4. Changing things later

Two ways, pick whichever suits the change.

**Small edits, in the browser.** Open the file on GitHub, click the pencil icon, edit, then **Commit changes** at the bottom. Pages redeploys in about a minute. Good for tweaking a session in the `QUALITY` table.

**Real work, with Claude Code.** Install Claude Code, then in a terminal:

```bash
git clone https://github.com/<your-username>/endurance-coach.git
cd endurance-coach
claude
```

Then just describe what you want: *"the taper is too aggressive, make it 65% of normal volume"* or *"add a swim session type"*. It edits the file, and when you say *"commit and push that"* it handles the Git. You'll pick up the commands by watching them go past, which is a better way to learn Git than reading about it.

The four commands worth knowing, in the order you'll use them:

```bash
git pull                      # get the latest version down
git add -A                    # mark your changes
git commit -m "what I did"    # save them with a note
git push                      # send them to GitHub
```

If you break something, `git log --oneline` lists every past version and `git revert <id>` undoes one. Nothing you do is unrecoverable, which is the actual point of Git.

---

## Files

```
index.html          the whole app: markup, styles, logic
data/Activities.csv your Garmin export, kept for reference
METHODOLOGY.md      why the plan looks the way it does — read before changing it
ROADMAP.md          what isn't built yet
```

## Where to change things

`index.html` is numbered in sections. The ones you'll actually touch:

| I want to | Go to |
|---|---|
| Change what Tuesday looks like | `QUALITY` table, section 7 |
| Change the second quality day | `QUALITY2` |
| Change the long run | `LONG` |
| Change the lifting | `STRENGTH` |
| Change ski sessions | `SKI` |
| Change how much a taper cuts | `PHASE_VOL` |
| Change when phases switch | `phaseFor()` |
| Change readiness scoring | `readinessFrom()` |
| Change weather rules | `weatherAdvice()` |
| Change what the AI knows | `buildContext()` |

## The AI part

Two options, both on the **Ask** tab.

**Copy context** builds a full briefing — profile, fitness, six weeks of load, recent sessions, check-ins, debriefs, this week's plan — and copies it. Paste it into the Claude app and argue there. Costs nothing, works everywhere, and you get the full model.

**In-app chat** needs an Anthropic API key, entered on the **You** tab. Faster, but the key sits in your browser where any script on the page can read it. It's a personal single-user app so the risk is mostly you, but use a key with a low spend cap and never commit it to the repo. It is stored in local storage, not in any file, so it won't end up in Git by accident.

## Weather

Uses [Open-Meteo](https://open-meteo.com), free and no key needed. Set your latitude and longitude on the **You** tab.

## Limits worth knowing

- VO2max here is VDOT, a performance model. It's an estimate from race results, not a measurement, and it flatters you if your only recent hard effort was downhill or wind-assisted.
- Ski fitness has no equivalent model. The app tracks your double-poling sessions and any repeated time trial you log, and leaves the interpretation to you.
- Nothing here knows about illness, travel, or a bad week at work unless you tell it in a check-in.
