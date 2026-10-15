*Ormer Modular · made in Guernsey*

# WAKE

USER MANUAL · DISTING NT · v1.0.0

Wake is a stereo delay for long, deep trails, for the Expert Sleepers disting NT. Every echo behaves like the wake behind a ship: it **spreads out, fades, darkens and drifts** as it trails away, and some of them stutter. Three controls do most of the work. **Distance** is how long the trail lasts and how wide it spreads, **Chop** is how much the repeats stutter, **Drift** is how far the pitch wanders. **Time** picks a musical division of the tempo, **Becalm** stops the ship dead, and **Clear** clears the water. Wake is free.

## Installing

1. Download **wake-plugin.zip** from the Wake releases page and unzip it onto the root of the disting NT's SD card. It puts `wake.o` in `programs/plug-ins/ormermodular/`.
2. Put the card back in the NT and restart it.
3. Add an algorithm and choose **Wake** (it is under Effect and Delay).

Wake needs a disting NT with firmware that lets a plug-in re-seed the pots after a bank change (**v1.19** or later). On earlier firmware the pots in banks two and three can jump.

When you add Wake it asks for one thing, the **Max time**: how many seconds of delay to reserve in memory, from 5 to 30 (default 10). It cannot be changed afterwards without re-adding the algorithm, and longer takes more memory: about 192 KB per second at 48 kHz, so 30 seconds is about 5.8 MB. The NT has 16 MB in all, shared with everything else in the preset, and it will not add an algorithm if there isn't enough memory left. If that happens, choose a shorter Max time.

## The screen and the pots

A boat sits at the top and its wake opens out beneath it. The wake is the delay, drawn live: it is brighter when the repeats are louder, wider with **Distance**, broken into pieces with **Chop**, flipped with **Reverse**, wobbling with **Drift** and frozen still while **Becalm** holds. Along the bottom, three names show what the three pots are doing now, each with a level bar. Three dots in the corner show which of the three banks you are on.

The three pots work in three **banks**. Push the centre pot to move to the next bank:

| Bank | Left pot | Centre pot | Right pot |
|---|---|---|---|
| 1 | Distance | Chop | Drift |
| 2 | Time | Reverse | Tone |
| 3 | Mix | Input | Tempo |

That is all Wake takes over: the three pot turns and the centre-pot push. Everything else on the NT keeps its usual job: the four buttons under the screen (Menu, Params, Help, Shift), the left pot push (back to the overview), the right pot push (jump to the knob) and the encoders.

**Becalm** and **Clear** are ordinary parameters on the Wake page. Set them from the parameter list, or map a gate, button or sequencer output to them in Mappings. The word BECALM shows at the top left of the screen while it is on, and CLEAR flashes at the top right when the repeats are emptied.

> **Pots after a bank change:** the firmware holds each pot until you turn it past the value it already has, so a bank change never makes a parameter jump.

## The three macros

Under the controls is one stereo delay line with feedback. You never meet its parameters raw. Each macro is **one control that moves several things along a single curve**.

IN → INPUT → DELAY (TIME) → TONE → LOOP (DISTANCE · CHOP · DRIFT) → REVERSE → MIX → OUT

### Distance: how long the trail lasts, how wide it spreads

Low, you get a few repeats close together. Turn it up and each pass keeps more of the last, so the trail runs longer. At 50% each repeat keeps about 60% of the one before; at 95% it keeps about 98%.

**The last few degrees hold.** In the final 5% the feedback reaches 100%, so the trail no longer dies: it holds as a bed. A slow leveller sits inside the loop: when sustained sound piles up in a long trail it eases the feedback back smoothly, so the bed stays clean instead of distorting, it never runs away, and a trail can run for minutes. Clear empties it.

The same control opens the stereo image. The right side runs a little longer than the left, by up to 1.5% at full, so each repeat lands further from its left twin than the last did, and a mono sound comes apart into stereo as it trails.

### Chop: repeats that stutter

Each repeat has a chance of being broken into a fragment that repeats: the first half, third, quarter, sixth or eighth of the repeat is looped for the length of that repeat, each grain faded in and out over a few milliseconds. At 0% every repeat plays straight. As you turn it up, more repeats stutter, and the divisions get finer.

It changes what you hear, not the trail: the repeats keep circulating underneath, and the pitch never moves. It is purely random, rolled afresh for every repeat. It needs the delay to be at most half the Max time, like Reverse, and it rests while Becalm holds the loop.

### Drift: how far the pitch wanders

Steady at zero. The lower half brings in a slow sine wobble of the delay time, different on each side, deepest around 45%. From 40% genuine random wander takes over, and from 45% **the tape comes in**: wow and flutter, a little saturation in the loop and a darker top. At full, pitch moves by up to about 4%, which is under a semitone. It acts on the repeats only, never on the dry signal.

> **Feel:** Drift moves settle over a fraction of a second, so the weather changes rather than switches. With Distance high, Drift and Tone together make a trail that wanders and darkens as it goes. That is the idea.

## Time and tempo

### Time: a division of the tempo

**Time** is a stepped parameter of **25 musical divisions**, from a 1/32 up to four bars, including septuplets, quintuplets, 5/16, 7/16, 5/8, 7/8, one and a half bars and three bars. The default is 1/4. The delay time is the step multiplied by the length of a beat.

### Where the tempo comes from

Choose a bus for **Clock input** (on the Clock page) and Wake sets the tempo from the spacing of the pulses, a clock or a gate going up through about 2 V. **Clock PPQN** says how many pulses make a beat (1, 2, 4 or 24, default 4). With **Clock input** set to None, the **Tempo** parameter sets it, from 20 to 300 BPM (default 120). If a clock stops for four seconds, Wake falls back to Tempo. A clock with jitter in it makes the delay time wobble a little: that is the clock.

### Long steps fold down

A step longer than the Max time **halves until it fits**, so it stays on the beat grid. At the default 10 seconds, four bars at 60 BPM would be 16 seconds, so it plays as 8.

### Moving Time: tape glide or crossfade

By default, change **Time** while repeats are sounding and they glide to the new delay like tape, rather than cutting. A small step is a quick swoop. A big jump takes a few seconds and bends further: shortening can lift the pitch by up to a fifth, and lengthening can drop it by up to an octave while the delay travels. Drift works on the same glide.

If you would rather the pitch never moved, set **Time change** to **Crossfade**. A change then jumps to the new delay and the old repeats fade into the new ones over a tenth of a second: no bend, no click.

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
| Reverse | 0–100% | How many repeats are heard backwards. Each repeat is chosen at random, so 50% is a mix of forward and backward. It is heard at the output only: the feedback loop always runs forward. A reversed repeat is the slice just recorded, played backwards, so it arrives one delay time late. It only works while the delay is at most half the Max time; beyond that, repeats stay forward. |
| Tone | 0–100% | How bright each repeat stays: left for dark, right for open. A low-pass inside the loop, applied again on every pass, so the tail gets duller as it trails. 100% leaves the top open (about 16 kHz), the default 70% is about 7 kHz, and 0% is about 1 kHz. |
| Input | 0–100% | Level into the delay. 50% (the default) is unity and 100% is double. The dry signal is never touched, so Input only changes how loud the repeats are. |
| Mix | 0–100% | Equal-power dry/wet. 100% is the classic send-return wash. |
| Becalm | Off / On | A becalmed ship stops dead. The current repeats hold and loop, and new input is shut out. It eases in over about a tenth of a second without a click, and the held loop is an exact copy of itself, so it neither decays nor gets noisier, however long you hold it. While held, Drift still moves the frozen loop and turning it back down returns the loop exactly as it was. Time stays where it was, and Mix and Wet level still work. Set it from the parameter list, or map a gate to it. |
| Clear | trigger | Empties the repeats. The wet signal fades out over a few milliseconds, the delay forgets what it holds, and the wet comes back. The dry signal is never touched, and nothing is left to return later, even if you lengthen Time. It also empties a becalmed loop. Set it to Clear from the parameter list, or map a gate to it: a rising edge clears. |
| Wet level | 0 to +12 dB | Make-up gain on the wet path, after the delay and before the mix. Pull Input back for headroom, then push the repeats back up here. At 0 dB (the default) the repeats are exactly as they are without it. Parameter only: it has no pot. |

## All parameters

On the Params screen, Wake has three pages. Every parameter can be mapped to CV, MIDI or I2C in the usual way.

| Page | Parameter | Range | Default |
|---|---|---|---|
| Wake | Time | 25 steps | 1/4 |
| Wake | Distance | 0–100.0% | 50.0% |
| Wake | Chop | 0–100.0% | 0% |
| Wake | Drift | 0–100.0% | 0% |
| Wake | Reverse | 0–100.0% | 0% |
| Wake | Tone | 0–100.0% | 70.0% |
| Wake | Mix | 0–100% | 50% |
| Wake | Input | 0–100% | 50% |
| Wake | Becalm | Off / On | Off |
| Wake | Clear | - / Clear | - |
| Wake | Wet level | 0–12.0 dB | 0 dB |
| Wake | Time change | Tape glide / Crossfade | Tape glide |
| Clock | Tempo | 20–300 BPM | 120 |
| Clock | Clock input | None, or a bus | None |
| Clock | Clock PPQN | 1 / 2 / 4 / 24 | 4 |
| Routing | Left input, Right input | bus | 1, None |
| Routing | Left output, Right output (and modes) | bus, Add / Replace | 13, 14, Replace |

## Routing

Wake is stereo. It expects ordinary Eurorack audio, about ±5 V at the peaks, and puts out the same level. Set **Right input** to None and the left input feeds both sides, so a mono source gives a stereo trail. Each output has an **Add** or **Replace** mode, as on any NT algorithm: Replace (the default) writes the mix to the bus, Add sums it onto what is already there.

## Troubleshooting

**I hear nothing.**

Check the Routing page: the input bus has to carry your audio and the outputs have to go where you are listening. With Mix at zero you hear only the dry signal.

**I hear the dry signal but no repeats.**

Check Mix is above zero, Input isn't at zero, and Becalm isn't on with nothing in the loop (becalm shuts new input out). A very low Distance gives just a few short repeats.

**Reverse does nothing.**

Reverse only works while the delay is at most half the Max time. Choose a shorter Time step, a faster tempo, or re-add Wake with a longer Max time.

**The pitch swoops when I change Time.**

That is the tape glide. Change it slowly, or set **Time change** to Crossfade for no pitch change at all.

**The Tempo pot does nothing.**

A clock is set on Clock input and it takes over. Set Clock input to None, or stop the clock for four seconds. If the tempo is a multiple or fraction of what you expect, check Clock PPQN.

**Where are Becalm and Clear on the pots?**

They are parameters, not pot controls. Wake only takes the three pot turns and the centre push, so the buttons and the left and right pot pushes keep their normal jobs. Find Becalm and Clear on the Wake page of the parameter list, or map a gate to them.

**The trail at full Distance won't die.**

By design: in the last 5% the feedback holds. Lower Distance, or set Clear.

## Specifications

| Format | disting NT plug-in | Stereo in, stereo out. Free. |
|---|---|---|
| Engine | stereo delay with feedback | Interpolated delay line; leveller and low-pass in the loop; per-repeat stutter; reversed output tap; Drift on the delay time (sine, then random wander and tape) |
| Time | 25 steps | 1/32 to 4 bars, from a clock or 20–300 BPM; steps longer than the Max time halve until they fit |
| Max time | 5 – 30 s | chosen when the algorithm is added, default 10 s; stored as 16-bit stereo, about 192 KB per second at 48 kHz |
| Audio | about ±5 V | in and out; right input optional (None: left feeds both) |
| Firmware | v1.19 or later | for pot takeover after a bank change |

Wake's engine is original. It uses no third-party DSP. Wake is closed-source and proprietary.

Wake for disting NT · Ormer Modular · made in Guernsey

fair winds
