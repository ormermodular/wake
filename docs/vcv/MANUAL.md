*Ormer Modular · made in Guernsey*

# WAKE

USER MANUAL · VCV RACK · v2.0.0 · 16 HP

Wake is a stereo delay for long, deep trails. Every echo behaves like the wake behind a ship: it **spreads out, fades, darkens and drifts** as it trails away, and some of them break up. Three knobs do most of the work. **DISTANCE** is how long the trail lasts and how wide it spreads, **CHOP** is how often a repeat drops out, **DRIFT** is how far the pitch wanders. **TIME** picks a musical division of the tempo, **BCLM** (becalm) stops the ship dead, and **CLR** clears the water. Every knob takes CV, and both buttons have a gate or trigger input.

## The panel

Everything below is at its default setting. Wake comes in two panels, silver and black: Rack picks one from its own dark-panel setting, and you can force either from the module's right-click menu.

- **CHOP** (Large knob · 0–100% · default 0): Repeats that break up. Each repeat has a chance of dropping out, rolled afresh every time, with no seed and no pattern. The trail carries on underneath, so a different set of repeats is heard each time round. At 0% every repeat comes back; at 100% about nine in ten are dropped.
- **DISTANCE** (Large knob · 0–100% · default 50): How long the trail lasts and how wide it spreads. Higher means more feedback and a wider stereo spread, and the last 5% holds the trail as a bed, kept clean by a slow leveller in the loop.
- **DRIFT** (Large knob · 0–100% · default 0): How far the pitch wanders. Steady at zero, a gentle sine wobble in the lower half, then random wander with tape wow, flutter and a darker top in the upper half. It acts on the repeats, never the dry signal.
- **GAIN** (Small knob · 0–100% · default 50): Level into the delay. 50% is unity, 100% is double. The dry signal is not touched. Not an audio input: those are IN L and IN R. Has a CV input.
- **TIME** (Small knob · 25 steps · default 1/4): A stepped dial of musical divisions of the tempo, from 1/32 to four bars. It snaps, shows each step by name, and glides like tape when moved while repeats are sounding. Has a CV input: 10 V sweeps all 25 steps.
- **CLCK** (Small knob · 20–300 BPM · default 120): The tempo, used when nothing is patched into the jack below. A patched clock sets the tempo instead. If the clock stops for four seconds the knob is used again.
- **REV** (Small knob · 0–100% · default 0): How many repeats are heard backwards, chosen at random for each one. Heard at the output only, so reversed repeats do not flip back on the next pass. Works while the delay is at most half the maximum delay time. Has a CV input.
- **TONE** (Small knob · 0–100% · default 30): How much each repeat darkens: a low-pass inside the loop, applied again on every pass. 0% leaves the top open, 100% is about 1 kHz. Has a CV input.
- **BCLM** (Button, latching): Becalm. The current repeats hold and loop, and new input is shut out. The held loop is an exact copy, so it neither decays nor gets noisier. Lit while on. A gate into the jack below does the same.
- **MIX** (Small knob · 0–100% · default 50): Equal-power dry/wet. 100% is the classic send-return wash. Has a CV input.
- **CLR** (Button): Clear. Empties the repeats: the wet fades out over a few milliseconds, the delay forgets what it holds, and the wet comes back. The dry signal is never touched. A trigger into the jack below does the same.
- **IN L** (Audio input): Left audio in. Patch a mono source here and IN R follows it. A polyphonic cable is summed to one signal.
- **IN R** (Audio input): Right audio in. Normalled to IN L, so it can stay empty for a mono source.
- **OUT L** (Audio output): Left audio out: the dry and wet signal, mixed by MIX.
- **OUT R** (Audio output): Right audio out: the dry and wet signal, mixed by MIX.
- **DIST CV** (CV input): Sums with the knob. +10 V adds the full range and −10 V takes it away, held between 0 and 100%.
- **CHOP CV** (CV input): Sums with the knob. +10 V adds the full range and −10 V takes it away, held between 0 and 100%.
- **DRFT CV** (CV input): Sums with the knob. +10 V adds the full range and −10 V takes it away, held between 0 and 100%.
- **GAIN CV** (CV input): Sums with the knob. +10 V adds the full range and −10 V takes it away, held between 0 and 100%.
- **TIME CV** (CV input): Adds to the knob: +10 V sweeps all 25 steps. The step is always a whole one, and a change glides like tape.
- **CLCK** (Clock input): Patch a clock here and Wake sets the tempo from the spacing of the pulses (rising edge above about 2 V). The right-click menu sets how many pulses make a beat. Overrides the CLCK knob while it runs.
- **REV CV** (CV input): Sums with the knob. +10 V adds the full range and −10 V takes it away, held between 0 and 100%.
- **TONE CV** (CV input): Sums with the knob. +10 V adds the full range and −10 V takes it away, held between 0 and 100%.
- **BCLM gate** (Gate input): High (about 2 V or more) holds the repeats, exactly as the button does. Drop the gate to release.
- **MIX CV** (CV input): Sums with the knob. +10 V adds the full range and −10 V takes it away, held between 0 and 100%.
- **CLR trigger** (Trigger input): A rising edge (above about 2 V) empties the repeats, exactly as the button does. Any clock, gate or trigger will do.
- **THE SCREEN** (Display): A small boat with its wake opening out behind it. Each ripple is a repeat. TIME spaces the ripples, DISTANCE lengthens and widens the wake, CHOP breaks ripples into fragments (some become dotted ghosts), DRIFT makes the wake wobble and, past halfway, adds tape grain and a slow weave. The ripples glow with the delay’s own level. When becalmed, the boat stops, the wake holds still and the sea goes glassy.

## The three knobs

Under the knobs is one stereo delay line with feedback. You never meet its parameters raw. Each big knob is a **macro**: one control that moves several things along a single curve.

IN → GAIN → DELAY (TIME) → TONE → LOOP (DISTANCE · CHOP · DRIFT) → REV → MIX → OUT

### DISTANCE: how long the trail lasts, how wide it spreads

Low, you get a few repeats close together. Turn it up and each pass keeps more of the last, so the trail runs longer. At noon each repeat keeps about 60% of the one before; at 95% it keeps about 98%.

**The last few degrees hold.** In the final 5% the feedback reaches 100%, so the trail no longer dies: it holds as a bed. A slow leveller sits inside the loop: when sustained sound piles up in a long trail it eases the feedback back smoothly, so the bed stays clean instead of distorting, it never runs away, and a trail can run for minutes. CLR clears it.

The same knob opens the stereo image. The right side runs a little longer than the left, by up to 1.5% at full, so each repeat lands further from its left twin than the last did, and a mono sound comes apart into stereo as it trails. The two sides stay separate, so a stereo input stays stereo.

### CHOP: repeats that break up

Each repeat has a chance of dropping out. What you hear is gated one delay time at a time, with a few milliseconds of fade, so a dropped repeat leaves a gap. The trail itself keeps circulating underneath, so the repeats that follow are still there: a different set comes through each time round and the echoes break into a rhythm. At 0% every repeat comes back; at 100% about nine in ten are dropped.

It is purely random. The dice are rolled afresh for every repeat, with no seed and no pattern to learn. With a long DISTANCE, a little CHOP breaks the trail into scattered fragments.

### DRIFT: how far the pitch wanders

Steady at zero. The lower half brings in a slow sine wobble of the delay time (about a third of a hertz), different on each side, deepest around 45%. From 40% genuine random wander takes over, and from 45% **the tape comes in**: wow and flutter, a little saturation in the loop and a darker top. The sine recedes past 60% but never leaves. At full, pitch moves by up to about 4%, which is under a semitone.

The curve is applied to the delay time, so it acts on the repeats only, never on the dry signal.

> **Feel:** DRIFT moves settle over a fraction of a second, so the weather changes rather than switches. With DISTANCE high, DRIFT and TONE together make a trail that wanders and darkens as it goes. That is the idea.

## Time and tempo

### TIME: a division of the tempo

TIME is a stepped dial of **25 musical divisions**, from a 1/32 up to four bars, including septuplets, quintuplets, 5/16, 7/16, 5/8, 7/8, one and a half bars and three bars. It snaps, shows each step's name, and you can click it and type one ("1/8", "dotted 1/4", "2 bars"). The default is 1/4. The delay time is the step multiplied by the length of a beat.

TIME takes CV: +10 V sweeps all 25 steps, so a sequence or a stepped source plays the delay time.

### CLCK: where the tempo comes from

Patch a clock into the jack under CLCK and Wake sets the tempo from the spacing of the pulses. With nothing patched, the CLCK knob sets it, from 20 to 300 BPM (default 120). If a patched clock stops for four seconds, Wake falls back to the knob. The right-click menu says how many pulses make a beat (1, 2, 4 or 24, default 4). A clock with jitter in it makes the delay time wobble a little: that is the clock, not a fault.

### Long steps fold down

A step longer than the maximum delay time **halves until it fits**, so it stays on the beat grid. At the default 10 seconds, four bars at 60 BPM would be 16 seconds, so it plays as 8. The maximum is a right-click choice: 5, 10, 15, 20 or 30 seconds. Changing it rebuilds the buffer, which clears the repeats.

### Moving TIME bends the pitch

Change TIME while repeats are sounding and they glide to the new delay like tape, rather than cutting. A small step is a quick swoop. A big jump takes a few seconds and bends further: shortening can lift the pitch by up to a fifth, and lengthening can drop it by up to an octave while the delay travels. Park the knob before a take if you don't want it. DRIFT works on the same glide, which is why they suit each other.

| # | Step | Beats | At 120 BPM |
|---|---|---|---|
| 1 | 1/32 | 1/8 | 62.5 ms |
| 2 | 1/16 septuplet | 1/7 | 71.4 ms |
| 3 | 1/16 triplet | 1/6 | 83.3 ms |
| 4 | 1/16 quintuplet | 1/5 | 100.0 ms |
| 5 | 1/16 | 1/4 | 125.0 ms |
| 6 | 1/8 triplet | 1/3 | 166.7 ms |
| 7 | dotted 1/16 | 3/8 | 187.5 ms |
| 8 | 1/8 quintuplet | 2/5 | 200.0 ms |
| 9 | 1/8 | 1/2 | 250.0 ms |
| 10 | 1/4 triplet | 2/3 | 333.3 ms |
| 11 | dotted 1/8 | 3/4 | 375.0 ms |
| 12 | 1/4 (default) | 1 | 500.0 ms |
| 13 | 5/16 | 5/4 | 625.0 ms |

| # | Step | Beats | At 120 BPM |
|---|---|---|---|
| 14 | 1/2 triplet | 4/3 | 666.7 ms |
| 15 | dotted 1/4 | 3/2 | 750.0 ms |
| 16 | 7/16 | 7/4 | 875.0 ms |
| 17 | 1/2 | 2 | 1.00 s |
| 18 | 5/8 | 5/2 | 1.25 s |
| 19 | dotted 1/2 | 3 | 1.50 s |
| 20 | 7/8 | 7/2 | 1.75 s |
| 21 | 1 bar | 4 | 2.00 s |
| 22 | 1.5 bars | 6 | 3.00 s |
| 23 | 2 bars | 8 | 4.00 s |
| 24 | 3 bars | 12 | 6.00 s |
| 25 | 4 bars | 16 | 8.00 s |

Times shown are at 120 BPM, before any fold-down.

## The other controls

| Control | Range | What it does |
|---|---|---|
| REV | 0–100% | How many repeats are heard backwards. Each repeat is chosen at random, so 50% is a mix of forward and backward. It is heard at the output only: the feedback loop always runs forward, so a reversed repeat does not flip back on the next pass. A reversed repeat is the slice just recorded, played backwards, so it arrives one delay time late. **It only works while the delay is at most half the maximum delay time** (up to 5 s at the default 10 s); beyond that, repeats stay forward. |
| TONE | 0–100% | How much each repeat darkens. A low-pass inside the loop, applied again on every pass, so the tail gets duller as it trails. 0% leaves the top open (about 16 kHz), the default 30% is about 7 kHz, and 100% is about 1 kHz. The tape half of DRIFT darkens it further. |
| GAIN | 0–100% | Level into the delay. 50% (the default) is unity and 100% is double. The dry signal is never touched, so GAIN only changes how loud the repeats are. Not an audio input: the audio jacks are IN L and IN R. |
| MIX | 0–100% | Equal-power dry/wet. 100% is the classic send-return wash. |
| BCLM | button + gate | Becalm: a becalmed ship stops dead. The current repeats hold and loop, and new input is shut out. It eases in over about a tenth of a second without a click, and the held loop is an exact copy of itself, so it neither decays nor gets noisier, however long you hold it. While held, DISTANCE, CHOP, DRIFT and TONE have nothing to act on, TIME stays where it was, and MIX and the wet level still work. A gate of about 2 V or more into the jack below does the same as the button. The light shows it is on. Press again, or drop the gate, to release. |
| CLR | button + trigger | Clear: empties the repeats. The wet signal fades out over a few milliseconds, the delay forgets what it holds, and the wet comes back. The dry signal is never touched, and nothing is left to return later, even if you lengthen TIME. A rising edge (above about 2 V) into the jack below does the same, which makes it a performance control. It also empties a becalmed loop. |

## Patching and CV

Wake is stereo and not polyphonic. It expects ordinary Eurorack audio, about ±5 V at the peaks, and puts out the same level. The **right input is normalled to the left**, so a mono source into IN L feeds both sides. Bypass passes left to left and right to right.

| Jack | Type | Notes |
|---|---|---|
| IN L / IN R | audio in | IN R is normalled to IN L. A polyphonic cable into either input is summed to one signal. CV inputs read the first channel only. |
| OUT L / OUT R | audio out | Stereo dry and wet, mixed by MIX. |
| DIST · CHOP · DRFT | CV in | Sums with the knob. +10 V adds the full range, −10 V takes it away, and the result is held between 0 and 100%. |
| GAIN · REV · TONE · MIX | CV in | The same scaling as the macros. |
| TIME | CV in | +10 V sweeps all 25 steps, added to the knob and held to the range. The step is always a whole one. |
| CLCK | clock in | Sets the tempo from the spacing of the pulses (rising edge above about 2 V), using the pulses-per-beat setting in the menu. Overrides the CLCK knob while it runs. |
| BCLM | gate in | High (about 2 V or more) holds the repeats, as the button does. |
| CLR | trigger in | A rising edge (above about 2 V) empties the repeats, exactly like the button. |

> **Nothing steps.** Every level and filter glides inside the engine, so stepped CV, fast envelopes and sample-and-hold sources stay clean. The one thing that moves in steps is TIME, and it glides between them.

## Right-click menu

| Item | Choices | What it does |
|---|---|---|
| Wet level | 0 to +12 dB | Make-up gain on the wet path, after the delay and before the mix. Pull GAIN back for headroom, then push the repeats back up here. At 0 dB (the default) the repeats are exactly as they are without it. The dry signal is not touched. |
| Max delay time | 5 · 10 · 15 · 20 · 30 s | How much audio Wake keeps. Default 10 s. Longer steps fold down to fit (see Time and tempo). Changing it rebuilds the buffer and clears the repeats. The choice is saved with the patch. |
| Clock pulses per beat | 1 · 2 · 4 · 24 | How many pulses of a patched clock make one beat. Default 4. Saved with the patch. |
| Panel | Follow Rack setting · Silver · Black | Forces the silver or the black panel for this module. The jacks and screws change with it. The choice is saved with the patch. By default the panel follows Rack's **View > Use dark panels if available**. |

## Installing

Wake is sold through the VCV Library, for Mac (Apple Silicon or Intel), Windows and Linux.

1. Add Wake to your account on its VCV Library page.
2. In Rack, log in from the **Library** menu and choose **Library > Update all**. Rack downloads Wake and any other plugins you own.
3. Restart Rack if it asks you to, then add **Wake** from the module browser, under Ormer Modular.

Wake needs Rack 2.

## Troubleshooting

**I hear nothing.**

Patch audio into IN L (IN R follows it) and make sure the module isn't bypassed. With MIX at zero you hear only the dry signal.

**I hear the dry signal but no repeats.**

Check MIX is above zero, GAIN isn't at zero, and BCLM isn't lit with nothing in the loop (becalm shuts new input out). A very low DISTANCE gives just a few short repeats.

**REV does nothing.**

REV only works while the delay is at most half the maximum delay time. Choose a shorter TIME step, a faster tempo, or a longer maximum in the right-click menu.

**The pitch swoops when I change TIME.**

That is the tape glide: the delay slides to its new length instead of cutting. A big jump bends further and takes a few seconds. Change it slowly, or before a take.

**TIME won't move while BCLM is lit.**

Becalm holds the loop at the length it had. TIME takes effect when you release it.

**The tempo knob does nothing.**

A clock is patched into CLCK, and it takes over. Unpatch it, or stop it for four seconds, and the knob is used again. If the tempo is a multiple or fraction of what you expect, check **Clock pulses per beat** in the right-click menu.

**The trail stops when I change the maximum delay time (or Rack's sample rate).**

Wake rebuilds its buffer, which clears the repeats. They start again as audio arrives.

**The trail at full DISTANCE won't die.**

By design: in the last 5% the feedback holds. Lower DISTANCE, or press CLR.

**The panel won't change colour.**

Use the module's right-click **Panel** menu. If it is set to Follow Rack setting, Rack's **View > Use dark panels if available** decides.

## Specifications

| Format | Rack 2 · 16 HP | Stereo, not polyphonic. Silver and black panels. |
|---|---|---|
| Engine | stereo delay with feedback | Interpolated delay line; soft limiter and low-pass in the loop; per-repeat dropout; reversed output tap; DRIFT on the delay time (sine, random wander, tape wow and flutter); exact-copy hold |
| Time | 25 steps | 1/32 to 4 bars, from a clock or 20–300 BPM; steps longer than the maximum halve until they fit |
| Max delay time | 5 – 30 s | default 10 s; stored as 16-bit stereo, about 192 KB per second at 48 kHz (10 s is 1.9 MB) |
| Audio | about ±5 V | in and out; IN R normalled to IN L |
| CV | 10 V = full range | DIST, CHOP, DRFT, GAIN, REV, TONE, MIX; TIME 10 V = all 25 steps; CLCK is a clock, BCLM a gate, CLR a trigger |
| Sample rate | 8 kHz and up | the buffer is rebuilt, and clears, when Rack changes it |
| Platforms | Mac · Windows · Linux | Apple Silicon and Intel Macs |

Wake's engine is original. It uses no third-party DSP. Wake is closed-source and proprietary.

Wake for VCV Rack · Ormer Modular · made in Guernsey

fair winds
