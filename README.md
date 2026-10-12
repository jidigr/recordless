# Record-less

A mode for creating musical events without recording performance.

## What is it?

Record-less separates **search** from **capture**. You play, try, explore — nothing is fixed. When you find what you want, you capture it. Consciously. In a specific point of musical time.

Modern DAWs inherit the paradigm of 20th-century hardware sequencers: **play → record → playback → edit**. There are only two states — play (nothing is fixed) and record (everything is fixed). Record-less introduces a third:

> **I am not recording a performance — I am fixing a musical intention.**

This is not another variant of Record. It is the opposite concept.

In Record mode, the DAW says: *"I will record what you are playing right now."*

In Record-less mode: *"You decide when a musical action becomes a musical event."*

## The problem

In a conventional MIDI workflow there are only two states.

**Playing without Record:**
key pressed → sound → no event in the Piano Roll.

**Recording:**
key pressed → sound → event is recorded in time.

But when a composer searches for material, they try variants. Plink one key. Another. Change the chord. Try another rhythm. Listen. Again. Change the note. This is **search**, not performance of finished material.

In a conventional DAW, every search gesture either becomes a recorded event (polluting the project) or is lost entirely.

## Core concept

The key switch is **Event Capture ON/OFF**.

| State | Behaviour |
| :--- | :--- |
| **Capture OFF** | Free search. Keys sound, but nothing is fixed in the Piano Roll |
| **Capture ON** | The next key presses become real musical events in the project |

> **searching for a musical idea ≠ fixing a musical idea**

This simple distinction substantially changes the workflow: you can freely noodle on the keyboard and search for what exactly you want to drop into the track, without fear of cluttering the project with dozens of random notes.

Found it → turned on capture → realised what you found.

## Step input modes

When capture is enabled, Record-less offers several input methods.

| Mode | Behaviour |
| :--- | :--- |
| **By Cursor** | Pressed key creates a note at the current cursor position |
| **By Bar** | Note is created at the beginning of the current bar |
| **Overlay** | New events are added on top of existing ones |
| **Replace** | New events replace existing ones at the selected position |
| **Live Input** | Temporal sequence of played notes is preserved without global Record. This is not recording everything that happens, but local event input |
| **Auto-Advance** | After creating an event, the cursor moves to the next grid position automatically |

Auto-Advance example:

pressed C → note appeared → cursor moved 1/16 further → pressed E → next note

Step-by-step construction of a musical phrase.

## Step automation

The same Capture ON/OFF logic applied to automation.

Instead of: turn on automation recording → move a knob → stop recording → edit the resulting curve.

You can have: choose musical time → set parameter value → create automation point.

Example:

1. Encoder moves the cursor to the desired position
2. Set cutoff = 73
3. Press a button
4. At that point, an automation point with the value 73 is created
5. The cursor automatically moves on

Works with DAW-internal parameters and VST/AU instruments.

Unified logic for notes and parameters: **find → decide → fix**.

## Note parameters on physical knobs

*Extended concept — emerged from discussion, not in the original text.*

Each note parameter can be assigned to a dedicated knob or fader:

| Parameter | What it does |
| :--- | :--- |
| **Velocity** | Press strength (volume/timbre) |
| **Note Length (Gate)** | Note duration |
| **Pan** | Note panning |
| **Micro-timing** | Offset from the grid |
| **Probability** | Chance of triggering |
| **Pitch Bend (MPE)** | Pitch bend |
| **Pressure (MPE)** | Pressure |
| **Timbre / CC74 (MPE)** | Timbre |
| **Release Velocity** | Release speed |
| **Articulation** | Articulation |
| **Humanize** | Random deviation |
| **Note Offset** | Offset of the whole note |

Model shift:

| Conventional DAW | Record-less |
| :--- | :--- |
| note → parameters | parameters → note |

You set the state first, then create the note. The note absorbs the current state of the knobs.

## Physical time and track control

- **Time Encoder** — navigation through musical time (bars, beats, ticks; rotation speed = movement speed)
- **Track Encoder** — track selection (left/right = previous/next, press = activate)
- After track selection, the controller receives the context of that track

> **turn the encoder → move through time; press a key → create an event here.**

This is no longer just controlling the Piano Roll. This is a physical interface to musical time.

Physical model:

| Control | Function |
| :--- | :--- |
| **Track Encoder** | Selects the track |
| **Time Encoder** | Selects musical time |
| **Record-less controls** | Determine the mode of operation |
| **Keyboard / Pads** | Create musical events |

## Distribution across multiple controllers

Record-less is not tied to one device. It accepts input from **any number of MIDI controllers simultaneously**.

| Controller | Role |
| :--- | :--- |
| **Controller 1** | Musical events / Record-less |
| **Controller 2** | Conventional performance |
| **Controller 3** | Mixer |
| **Pads** | Drums / samples |
| **Encoder** | Musical time |
| **Encoder** | Track selection |

Each has a permanent, clear role. No mode switching. No conflicts.

This also means:
- you don't need to buy a specific controller;
- you can start with one device and expand later;
- you can use what you already have;
- the concept scales from one cheap controller to a full hardware setup.

Record-less is not about specific hardware. It is about logic that can be distributed across any number of physical interfaces.

## Local mappings per track

The controller can hold the context of the selected track:

**Track 1 — Bass:**

Encoder 1 → Cutoff
Encoder 2 → Resonance
Encoder 3 → Volume

**Track 2 — Pad:**

Encoder 1 → Attack
Encoder 2 → Release
Encoder 3 → Filter

**Track 3 — Drums:**

Pads → individual MIDI notes
Encoder 1 → Kick level
Encoder 2 → Snare level

Switching the track automatically switches the mappings. The controller becomes a **physical interface to the current musical object**.

## User workflow examples

**Example 1: Step-by-step note creation**

1. Select track with encoder
2. Record-less is on
3. Capture OFF
4. Play on the keyboard, searching for material — nothing is accidentally fixed
5. Found the phrase. Capture ON
6. Turn the time encoder
7. Find the desired position
8. Press the keys
9. Notes appear exactly there

**Example 2: Step-by-step automation creation**

1. Select track
2. Choose the desired musical time
3. Capture OFF
4. Turn a parameter, listen to the result
5. Found the value. Capture ON
6. Fix the value
7. At that point, an automation point appears

Without Record. Without necessarily using the mouse. Without having to first record exploratory playing and then clean it up.

## Fundamental difference

| Conventional DAW | Record-less |
| :--- | :--- |
| Performance → Recording → Event | Search → Decision → Musical time → Capture → Event |
| Event is the result of recording | Event is the result of intention |
| Record ON/OFF | Capture ON/OFF |
| All or nothing | Only what you decide |

A musical event stops being exclusively the result of recording a performance. It becomes an **independent object** that can be directly created, modified, and moved in musical time.

## Why this is possible now

A computer DAW already knows:

- current musical time
- cursor position
- grid
- selected track
- instrument parameters
- MIDI controller state
- existing events

Therefore there is no fundamental need to force the user through the model: "first play — then record." One can work directly with musical events.

At the user-model level this looks natural:

MIDI event arrived → DAW determined the current context → determined the musical position → created or modified the event according to the selected Record-less mode.

## Relation to existing features

| Existing | Difference from Record-less |
| :--- | :--- |
| **Capture MIDI (Ableton)** | Retroactive: "rescue what was already played." Record-less is proactive: "fix what you decided to fix" |
| **Step Sequencer (Elektron, Squarp)** | Programming steps in a separate device. Record-less works with DAW time directly |
| **Piano Roll + mouse** | Drawing notes with a mouse. Record-less uses a physical controller, with search/fixation separation |

## Analogy: from musical staff to digital musical space

A composer sits before a blank sheet of manuscript paper and writes a note on the staff. They did not perform that note. They did not record sounding music. They **directly created a musical object** by defining its position in the system of notation.

Paper does not require the composer to first play the music before being able to write it down. Why should a digital musical environment necessarily require this?

Piano Roll already allows drawing MIDI notes directly. But Record-less extends the principle of direct event creation to interaction with keyboards, controllers, and physical controls — **without necessarily entering performance recording mode**.

Record-less is an attempt to bring into the digital environment the freedom of a composer who creates a musical record directly, rather than only capturing a performance.

Not instead of traditional recording. Not instead of Piano Roll. And not instead of the usual workflow. But as **an additional way of working** with musical material, where creating an event does not have to be a consequence of performing it.

## Applicability

Potentially applicable to: FL Studio · Cubase · Ableton Live · Bitwig · REAPER · Studio One · and others.

Not necessarily implemented identically. The concept itself is universal.

**Who it is for:** composers · people who do not play the keyboard virtuosically · hardware MIDI users · those who build music polyphonically · those who prefer step-by-step construction · people who think in musical objects, not only in performance.

The most important thing: it separates search from result. A musician does not always need to immediately record what they play. Sometimes they are just searching. This note? No. This one? Also no. What if I put another one here? Now that's it. And only after that do they want to tell the system: "Keep this." And that is the moment when capture turns on.

## Controller state display

If the controller has LEDs or a display, it can show the current state:

RECORD-LESS: ON
CAPTURE: ON
MODE: OVERLAY

This makes the state of the system physically tangible and does not require searching for the corresponding item in the interface.

## Why not just Record?

Why do you need this if there is Record?

For the same reason you need a text editor if you have a voice recorder. Because thinking and typing is not the same as speaking. And composing music is not the same as playing it.

## Status

- Concept: **complete**
- Prototype (REAPER + ReaScript/EEL2): **in development**
- Video demo: **coming soon**

## License

Concept text: **CC BY-NC 4.0** — attribution required, commercial use requires permission.

Code (when published): **MIT**.

You are free to read, copy, distribute, adapt, quote, and reference the text — under the condition of attribution (**BY**).

Prohibited without separate permission: commercial use (**NC**), including embedding the concept into commercial products, paid DAWs, paid plugins.

To obtain permission for commercial use — contact the author.

© 2026 Lin Auric

## Author

Lin Auric
*Cano musicam, ergo manifestor.*

---

> Record-less does not propose changing or cancelling the existing way DAWs work. The usual workflow remains as users are used to it: Play → Record → Playback → Edit. Record-less is just an additional mode. Those who don't need it simply don't turn it on and continue as before. Those who need it get another way of interacting with musical events: Search → Decide → Capture → Event. No revolution and no coercion. Just another tool.