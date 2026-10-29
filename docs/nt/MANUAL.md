# Wake for disting NT: User Manual

*Ormer Modular, made in Guernsey.*

Wake is a stereo delay for long, deep trails, for the Expert Sleepers disting NT. Every echo behaves like the wake behind a ship: it **spreads out, fades, darkens and drifts** as it trails away, and some of them stutter. Three controls do most of the work. **Distance** is how long the trail lasts and how wide it spreads, **Chop** is how much the repeats stutter, **Drift** is how far the pitch wanders. **Time** picks a musical division of the tempo, **Becalm** stops the ship dead, and **Clear** clears the water. Wake is free.

This is the manual for the Expert Sleepers disting NT plug-in. Version 1.0.0.

## Contents

1. [The screen](#the-screen)
2. [The three macros](#the-three-macros)
3. [Other controls](#other-controls)
4. [Time and tempo](#time-and-tempo)
5. [On the disting NT](#on-the-disting-nt)
6. [Troubleshooting](#troubleshooting)
7. [Specifications](#specifications)

## The screen

This is the live display, running the same drawing code as the plug-in: a boat on the sea, with its wake opening out behind it. Each chevron is a repeat. They get brighter and last longer as you raise Distance, and the wake opens wider. Chop breaks the chevrons into pieces, some of them looping. Drift rocks the boat, wobbles the wake and speeds the sea. The lantern and the spray follow the actual level of the repeats. Becalm freezes the whole picture, and Clear flashes its label. The three names along the bottom sit above the three pots, each with a level bar, and the three squares at the bottom left show the page. (The labels use plain letters here instead of the NT's own font.)

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

## Other controls

| Control | Range | What it does |
|---|---|---|
| Reverse | 0–100% | How many repeats are heard backwards. Each repeat is chosen at random, so 50% is a mix of forward and backward. It is heard at the output only: the feedback loop always runs forward. A reversed repeat is the slice just recorded, played backwards, so it arrives one delay time late. It only works while the delay is at most half the Max time; beyond that, repeats stay forward. |
| Tone | 0–100% | How bright each repeat stays: left for dark, right for open. A low-pass inside the loop, applied again on every pass, so the tail gets duller as it trails. 100% leaves the top open (about 16 kHz), the default 70% is about 7 kHz, and 0% is about 1 kHz. |
| Input | 0–100% | Level into the delay. 50% (the default) is unity and 100% is double. The dry signal is never touched, so Input only changes how loud the repeats are. |
| Mix | 0–100% | Equal-power dry/wet. 100% is the classic send-return wash. |
| Becalm | Off / On | A becalmed ship stops dead. The current repeats hold and loop, and new input is shut out. It eases in over about a tenth of a second without a click, and the held loop is an exact copy of itself, so it neither decays nor gets noisier, however long you hold it. While held, Drift still moves the frozen loop and turning it back down returns the loop exactly as it was. Time stays where it was, and Mix and Wet level still work. **Push the left pot**, set it from the parameter list, or map a gate to it. |
| Clear | trigger | Empties the repeats. The wet signal fades out over a few milliseconds, the delay forgets what it holds, and the wet comes back. The dry signal is never touched, and nothing is left to return later, even if you lengthen Time. It also empties a becalmed loop. **Push the right pot**, set it to Clear from the parameter list, or map a gate to it: a rising edge clears. |
| Wet level | 0.0 to +12.0 dB | Make-up gain on the wet path, after the delay and before the mix. Pull Input back for headroom, then push the repeats back up here. At 0 dB (the default) the repeats are exactly as they are without it. Parameter only: it has no pot. |

## Time and tempo

### Time: a division of the tempo

**Time** is a stepped parameter of **25 musical divisions**, from a 1/32 up to four bars, including septuplets, quintuplets, 5/16, 7/16, 5/8, 7/8, one and a half bars and three bars. The default is 1/4. The delay time is the step multiplied by the length of a beat.

### Where the tempo comes from

The tempo comes from the first of these that is available:

1. **MIDI clock**, when the **MIDI clock** parameter (Clock page) is On and the NT is sending clock. Wake follows the standard 24 ticks per beat, whether it comes from an external source or from an algorithm on the NT that sends MIDI clock. MIDI stop hands the tempo back, and so does four seconds without a tick.
2. The **Clock input** bus: choose a bus and Wake sets the tempo from the spacing of the pulses, a clock or a gate going up through about 2 V. **Clock PPQN** says how many pulses make a beat (1, 2, 4 or 24, default 4). If the pulses stop for four seconds, Wake falls back.
3. The **Tempo** parameter, from 20 to 300 BPM (default 120).

A clock with jitter in it makes the delay time wobble a little: that is the clock.

### Long steps fold down

A step longer than the Max time **halves until it fits**, so it stays on the beat grid. At the default 10 seconds, four bars at 60 BPM would be 16 seconds, so it plays as 8.

### Moving Time: tape glide or crossfade

By default, change **Time** while repeats are sounding and they glide to the new delay like tape, rather than cutting. A small step is a quick swoop. A big jump takes a few seconds and bends further: shortening can lift the pitch by up to a fifth, and lengthening can drop it by up to an octave while the delay travels. Drift works on the same glide.

If you would rather the pitch never moved, set **Time change** to **Crossfade**. A change then jumps to the new delay and the old repeats fade into the new ones over a tenth of a second: no bend, no click.

| # | Step | Beats |
|---|---|---|
| 1 | 1/32 | 0.125 |
| 2 | 1/16 septuplet | 0.142857 |
| 3 | 1/16 triplet | 0.166667 |
| 4 | 1/16 quintuplet | 0.2 |
| 5 | 1/16 | 0.25 |
| 6 | 1/8 triplet | 0.333333 |
| 7 | dotted 1/16 | 0.375 |
| 8 | 1/8 quintuplet | 0.4 |
| 9 | 1/8 | 0.5 |
| 10 | 1/4 triplet | 0.666667 |
| 11 | dotted 1/8 | 0.75 |
| 12 | 1/4 (default) | 1 |
| 13 | 5/16 | 1.25 |
| 14 | 1/2 triplet | 1.33333 |
| 15 | dotted 1/4 | 1.5 |
| 16 | 7/16 | 1.75 |
| 17 | 1/2 | 2 |
| 18 | 5/8 | 2.5 |
| 19 | dotted 1/2 | 3 |
| 20 | 7/8 | 3.5 |
| 21 | 1 bar | 4 |
| 22 | 1.5 bars | 6 |
| 23 | 2 bars | 8 |
| 24 | 3 bars | 12 |
| 25 | 4 bars | 16 |

Times shown are at 120 BPM, before any fold-down.

## On the disting NT

### Installing

Wake needs [disting NT firmware 1.19 or newer](https://www.expert-sleepers.co.uk/distingNTfirmwareupdates.html).

1. Download `wake-plugin.zip` and unzip it onto the root of the MicroSD card. It puts `wake.o` in `programs/plug-ins/ormermodular/`.
2. Restart the module.
3. Add an algorithm and choose **Wake** (tagged Effect / Delay).

When you add Wake it asks for one thing, the **Max time**: how many seconds of delay to reserve in memory, from 5 to 30 (default 10). It cannot be changed afterwards without re-adding the algorithm, and longer takes more memory: about 192 KB per second at 48 kHz, so 30 seconds is about 5.8 MB. The NT has 16 MB in all, shared with everything else in the preset, and it will not add an algorithm if there isn't enough memory left. If that happens, choose a shorter Max time.

### The pots: three pages

The three pots always do exactly three things, and which three depends on the page. **Pushing the centre pot steps to the next page**; the label strip along the bottom of the screen always names what the pots do right now, with a level bar for each, and the three squares at the bottom left show which page you are on.

**PAGE 1: The macros** (where Wake lives: the trail in three moves). DISTANCE: how long it lasts, how wide it spreads; CHOP: repeats that stutter; DRIFT: how far the pitch wanders

**PAGE 2: Time, reverse and tone** (shaping each repeat). TIME: 25 divisions of the tempo; REVERSE: repeats played backwards; TONE: dark to open

**PAGE 3: The levels and tempo** (set when patching, then leave). MIX: equal-power dry/wet; INPUT: level into the delay; TEMPO: BPM when no clock is patched

> **Nothing ever jumps:** after a page change, each pot stays silent until you turn it to the value it now owns (the NT's soft takeover). Flip pages freely mid-performance. **Wet level** and the clock, time-change and routing settings have no pot: set them from the parameter list.

### Becalm and Clear on the pot pushes

Two quick performance tools sit on the pot pushes, named along the top of the screen:

- **Push the left pot: Becalm**, on and off. The label at the top left reads BECALM when it is off, and bright BECALM ON while it holds.
- **Push the right pot: Clear.** It is momentary: the repeats empty, and the CLEAR label at the top right lights for a moment.

Both are also ordinary parameters on the Wake page, so you can set them from the parameter list or map a gate, button or sequencer output to them in Mappings.

> **Encoders and the parameter list:** while Wake's screen is showing, both encoders (turning them) and the right encoder push do nothing, so you can never change a hidden parameter by accident. Press **button 2** to switch to the NT's parameter list, where they work as usual. The ways out are always the NT's own: buttons 1 to 4 and the left encoder push (back to the overview).

### Automation and CV

Every parameter, the three macros included, is a normal NT parameter, so all of it can be mapped to CV, MIDI or i2c and automated through the module's own **Mappings** system, exactly like a built-in algorithm. The macros run at 0.1% resolution and every audible target glides inside the engine, so mapped steps and fast automation stay clean. Time moves like tape (or crossfades) when it changes, and Chop and Reverse change how many repeats stutter or play backwards, so you hear more or fewer of them.

### All parameters

Wake has three pages in the NT's parameter list: Wake, Clock and Routing.

| Parameter | Range | Default | Page | What it does |
|---|---|---|---|---|
| Time | 25 steps | 1/4 | Wake | The delay time, as a division of the tempo. |
| Distance | 0 to 100.0% | 50.0% | Wake | How long the trail lasts, and how wide it spreads. |
| Chop | 0 to 100.0% | 0% | Wake | How many repeats stutter. |
| Drift | 0 to 100.0% | 0% | Wake | How far the pitch wanders. |
| Reverse | 0 to 100.0% | 0% | Wake | How many repeats play backwards. |
| Tone | 0 to 100.0% | 70.0% | Wake | How bright each repeat stays. |
| Mix | 0 to 100% | 50% | Wake | Dry/wet. |
| Input | 0 to 100% | 50% | Wake | Level into the delay. |
| Becalm | Off / On | Off | Wake | Hold the repeats. Left pot push. |
| Clear | - / Clear | - | Wake | Empty the repeats (a rising edge). Right pot push. |
| Wet level | 0.0 to 12.0 dB | 0 dB | Wake | Make-up gain on the repeats. |
| Time change | Tape glide / Crossfade | Tape glide | Wake | How Time moves. |
| Tempo | 20 to 300 BPM | 120 | Clock | Used when no clock is available. |
| Clock input | a bus, or None | None | Clock | A pulse input that sets the tempo. |
| Clock PPQN | 1 / 2 / 4 / 24 | 4 | Clock | Pulses per beat on the Clock input. |
| MIDI clock | Off / On | Off | Clock | Follow the NT's MIDI clock (24 per beat). |
| Left input | a bus | Input 1 | Routing | Left audio in. |
| Right input | a bus, or None | None | Routing | Right audio in. None: left feeds both sides. |
| Left output, Right output | a bus, or None | Output 1, Output 2 | Routing | Where the stereo output goes. |
| Output mode | Add / Replace | Replace | Routing | Replace writes the mix to the bus, Add sums it onto what is there. |

### Routing

| Signal | Default | Notes |
|---|---|---|
| Left input | Input 1 |  |
| Right input | None | Left feeds both sides, so a mono source gives a stereo trail. Set it to a bus for a true stereo input. |
| Left output | Output 1 | None writes nothing. |
| Right output | Output 2 | None sends both sides, summed, to the left output. |
| Output mode | Replace | Applies to both outputs. Mix already carries your dry signal, so Replace is the natural choice. Use **Add** only to sum onto a busy bus, with Mix at 100% wet. |

## Troubleshooting

**Wake doesn't appear in the NT's algorithm list.** Update the module's firmware (Wake needs 1.19 or newer) and check that `wake.o` really is inside `programs/plug-ins/ormermodular/`.

**I hear nothing.** Check the Routing page: the input bus has to carry your audio and the outputs have to go where you are listening. With Mix at zero you hear only the dry signal.

**I hear the dry signal but no repeats.** Check Mix is above zero, Input isn't at zero, and Becalm isn't on with nothing in the loop (becalm shuts new input out). A very low Distance gives just a few short repeats.

**Reverse does nothing.** Reverse only works while the delay is at most half the Max time. Choose a shorter Time step, a faster tempo, or re-add Wake with a longer Max time.

**The pitch swoops when I change Time.** That is the tape glide. Change it slowly, or set **Time change** to Crossfade for no pitch change at all.

**The Tempo pot does nothing.** A clock is set on Clock input, or MIDI clock is On and ticking, and it takes over. Set Clock input to None and MIDI clock to Off, or stop the clock for four seconds. If the tempo is a multiple or fraction of what you expect, check Clock PPQN.

**The encoders do nothing on Wake's screen.** On purpose: on this screen they would edit a parameter hidden behind the picture. Press button 2 (Params) for the parameter list, where they work as usual.

**Where are Becalm and Clear?** On the pot pushes: left pot push is Becalm, right pot push is Clear. They are also on the Wake page of the parameter list, and you can map a gate to either.

**Wake won't add, or the NT says it is out of memory.** Choose a shorter Max time. Each second of delay takes about 192 KB.

**The trail at full Distance won't die.** By design: in the last 5% the feedback holds. Lower Distance, or push the right pot to Clear.

## Specifications

| | |
|---|---|
| Format | disting NT algorithm, free, closed source |
| Version | 1.0.0 |
| Firmware | 1.19 or newer (pot takeover after a page change) |
| Engine | stereo delay with feedback; leveller and low-pass in the loop; per-repeat stutter; reversed output tap; Drift on the delay time (sine, then random wander and tape) |
| Time | 25 steps, 1/32 to 4 bars, from MIDI clock, a clock input or 20 to 300 BPM; steps longer than the Max time halve until they fit |
| Max time | 5 to 30 s, chosen when the algorithm is added (default 10 s); stored as 16-bit stereo, about 192 KB per second at 48 kHz |
| Audio | about ±5 V, in and out; right input optional (None: left feeds both sides) |
| Parameters | 22, on three pages: Wake, Clock and Routing |
| Tag | Effect, Delay |
