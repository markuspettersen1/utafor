# Methodology

What the plan generator believes, and why. This exists so that when you disagree with a session you can argue with a position rather than a black box.

## The situation it is built for

One athlete, 6–9 hours a week, three goals that don't fully agree with each other: a half marathon, general strength on the base lifts, and winter double poling. Rest Monday, hard Tuesday, the rest open.

Six to nine hours is the constraint that decides almost everything below. At 15 hours you can afford sessions that only work a little. At seven you cannot.

## Five positions

**1. Most of the week is easy, and easy means easier than you think.**

The consistent finding across endurance sports is that trained athletes spend roughly 75–85% of sessions at low intensity and the rest genuinely hard, with little in the moderate middle — Seiler's polarised work is the usual citation, and Stöggl & Sperlich's 2014 comparison of intensity distributions is the cleaner experiment. The mechanism people argue about; the distribution is fairly stable across sports and levels.

The failure mode this guards against is the moderately hard easy run. It costs real recovery and buys very little. The app's easy pace band comes from VDOT at 68–74% of VO2max, which will feel slow.

**2. One hard day, plus a second lighter one, plus a long run.**

At your hours, two full quality sessions and a long run is three stressors in five training days, and the long run is a stressor. So Tuesday is the real session, Thursday is a lighter one in build and peak only, and Sunday is long. In base, Thursday is just easy.

If you find you recover fine and want more, the honest move is to raise total hours first and add the third hard session second.

**3. Threshold does the heavy lifting for a half marathon; VO2max work is a supplement.**

A half marathon is run at roughly 85–90% of VO2max for someone at your level, which is close to threshold. So threshold sessions get the most slots in `QUALITY`, VO2max intervals appear in build to raise the ceiling, and race-pace work dominates the final four weeks on the principle that you get good at what you practise. That last principle is stated more bluntly than anywhere else in Nils van der Poel's *How to skate a 10k*, which is in this project: whoever does the most laps at competition speed wins the 10k.

**4. Strength is maintained, not built, once the race gets close.**

Concurrent training interference is real but modest, and it runs mostly one way: heavy lifting barely hurts endurance, while high endurance volume blunts strength gains. So the base phase lifts heavy and expects progress; build and peak drop to 2–4 hard sets of low reps, which holds strength at low fatigue cost.

Van der Poel lost about 25% of his squat and explosiveness in a year of this kind of programme and considered it a fair trade for the event he cared about. You have said you want to maintain general strength, so the app protects the lifting slots from the volume scaler — they never get cut to hit an hours target. If you'd rather progress the lifts than run 1:30, tell the plan and change `STRENGTH`.

**5. Rest days are training.**

Van der Poel's 5–2 structure — five days on, two full days off — is the reason the app defaults to a hard Monday-free week and treats the check-in as a real input. His argument isn't that rest is nice, it's that a fixed rhythm gives you a baseline: you learn what a normal Wednesday feels like, so an abnormal one is visible before it becomes an injury. Your version isn't a strict 5–2 because you want six days of activity, but the logic of a fixed shape holds.

## Winter and double poling

Double poling is not cross-training for running and running is not preparation for double poling — the upper-body and trunk demands don't transfer in either direction. What does transfer is the aerobic base.

So in winter the app substitutes a ski session for one easy run rather than adding it on top. You keep the hours, you shift where they land. The trade is real: a winter of serious double poling costs you some running-specific fitness, and a half marathon in March after a poling winter will be slower than one in March after a running winter. If the half is the priority, keep ski days to one. If the winter is the priority, set two and accept the half will be a training race.

## Phases

| Weeks to race | Phase | What changes |
|---|---|---|
| >12 | Base | Volume, threshold, heavy lifting, no race-pace work |
| 12–5 | Build | VO2max intervals appear, long run gets marathon-pace finishes, lifting drops volume |
| 4–2 | Race specific | Everything becomes goal-pace, lifting is low volume high intent |
| ≤1 | Taper | Volume to ~55%, intensity kept, nothing to prove |

The taper cuts volume and keeps intensity, which is the direction the meta-analytic evidence points (Bosquet et al., 2007): a 40–60% volume reduction over 1–3 weeks, frequency and intensity roughly maintained.

## The daily adaptation rules

Readiness is a crude sum of four self-reported numbers: sleep hours, sleep quality, stress, soreness. It is deliberately not HRV. HRV is noisy day to day and easy to over-read, and the four questions capture most of what you'd act on anyway.

- **Green (15–20):** train as planned.
- **Amber (11–14):** keep the intensity, cut the volume. A shortened hard session is still a hard session; a full session done badly is neither.
- **Red (≤10):** downgrade to easy or rest, and move the session rather than abandoning it.

The bias is toward doing less. Missing a session costs almost nothing over a 20-week build. Doing a hard session on top of an unrecovered body is how the build ends.

## What this methodology is not confident about

- Whether a second quality day at 7 hours a week is a net gain or a net cost. It's in build and peak only, which is a hedge.
- The VDOT decay rate (0.35/month). Chosen so a four-month-old marathon doesn't dominate, not derived from anything.
- The readiness thresholds. Made up. They should be recalibrated once you have two months of check-ins alongside how sessions actually went.
- Whether your goal time is right. It is currently a placeholder.

## Sources

- Seiler, S. (2010). What is best practice for training intensity and duration distribution in endurance athletes? *Int J Sports Physiol Perform*.
- Stöggl, T. & Sperlich, B. (2014). Polarized training has greater impact on key endurance variables than threshold, high intensity, or high volume training. *Front Physiol*.
- Daniels, J. *Daniels' Running Formula* — the VDOT tables and the pace percentages used in section 4 of the app.
- Bosquet, L. et al. (2007). Effects of tapering on performance: a meta-analysis. *Med Sci Sports Exerc*.
- Rønnestad, B. & Mujika, I. (2014). Optimizing strength training for running and cycling endurance performance. *Scand J Med Sci Sports*.
- van der Poel, N. (2022). *How to skate a 10k*. In this project. Not a peer-reviewed source; a first-person account of what one athlete did, and the clearest statement of the specificity argument anywhere.

Swap these for your own handpicked papers — that's what the file is for.
