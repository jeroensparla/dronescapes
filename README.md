# dronescapes
Apps to create and generate drone- and soundscapes

GENERATE ENDLESS DRONES
Compose evolving worlds of sound directly in your browser

Looking for new textures that never sit still?
Tonal Weave and the 8-Track Drone Mixer are two free creative tools built for composers and producers who sculpt atmosphere and emotion.

Tonal Weave generates harmonic MIDI patterns that slowly drift and interlock—perfect for ambient beds, film scoring, or modular experimentation.
8-Track Drone Mixer lets you layer, crossfade, and modulate up to eight audio stems into infinite, breathing soundscapes.

Everything runs locally in your browser. No installs, no accounts—just pure creation.

🎧 Build evolving drones. Shape time. Paint space.
Try them free and start weaving your own sonic universe:
[Tonal Weave + Drone Mixer – Open in Browser]

—————————————————————————————————————————————————————————————————————————————
This package contains:

	•	HTML app: Tonal Weave — MIDI 8-Track Generator (v4.0)
	•	HTML app: 8-Track Drone Mixer • Presets + WebM Recorder + LFO Pan
	•	Sample files

Created by Jeroen KJM Sparla - https://soundcloud.com/jsparla

—————————————————————————————————————————————————————————————————————————————
Manual 1: Tonal Weave — MIDI 8-Track Generator (v4.0)
For creating source material for evolving drone and underscore textures.

Tonal Weave generates 8 interlocking MIDI loops that share one harmonic universe, but each loop can have a different length and role. The result is a slow shifting pattern that never quite repeats in the same way. You export MIDI, feed it to your synths or samplers in your DAW, print stems, and later use those stems in the Drone Mixer.

Below is a practical, “just make music” guide for a composer who knows basic harmony and DAWs, without having to read code.
	1.	Core idea

You have 8 tracks.
Each track:
	1.	Follows the same 8-bar chord progression.
	2.	Has its own musical role (bass, pad, melody, etc).
	3.	Has its own loop length in bars.

Because loop lengths differ, the full 8-track pattern only lines up once in a long while. This is what creates that “endless, evolving” feel that works well for ambient, film, and game soundscapes.
	2.	First session: from zero to usable MIDI in a few clicks
	3.	Open the HTML file in a modern browser with sound and downloads enabled.
	4.	At the top, pick a Preset such as “Nocturne Drift”. This instantly sets key, mode, roles, loop lengths and feel.
	5.	Check Key & Mode. For a dark, cinematic palette, try D harmonic minor or Phrygian. For hopeful or neutral, use major, lydian or mixolydian.
	6.	Set Tempo. Typical drone / underscore ranges between 40 and 80 BPM.
	7.	Leave the other defaults as they are for your first try.
	8.	Click “Generate MIDI”. The app creates a multi-track MIDI file and suggests a filename.
	9.	Save the file and drag it into your DAW.
	10.	Route each MIDI track to a fitting sound: bass to a low synth or contrabass, pads to long textures, melody/counter to softer leads, drone to organs or granular beds, sparkles to high soft bells or reversed textures.
	11.	Let the loop run for a few minutes and listen. You now have a harmonically consistent evolving bed.
	12.	Controls in plain English

Presets
A preset is a starting recipe: key, mode, tempo, chord progression, loop lengths, role layout, density and expression. Choosing a preset updates the fields so you can either use it “as is” or tweak from there.

Key & Mode
“Key Root” is your tonal center.
“Mode” defines the color of the scale.
Internally, everything is constrained to that scale and its chords, so you almost never get random wrong notes, only color tones around the chords.

Tempo (BPM)
Sets the musical tempo and is written into the MIDI file as tempo meta data, so your DAW picks it up.

Global Transpose
Shifts all notes up or down in semitones. Useful if the preset key works musically, but you want it lower for cellos or higher for synths.

Swing
Subtle timing offset on 8th notes. Values between 0.02 and 0.08 give a gentle human feel. Higher values start to “lilt” more. It is applied algorithmically instead of random slop.

Humanize timing (ms)
Adds a small random offset on note start times. Low values (5–20 ms) create life without making it drunk. Higher values become more experimental.

PPQ (resolution)
MIDI timing resolution. 480 is a solid default. Only change if you have a specific technical reason.

Velocity min / max
Global dynamic window. The generator picks velocities between these values, with each role having its own typical loudness curve. Narrow this range for more static drones, widen it for more expressive movement.

CC11 Expression LFO
If enabled, the generator writes CC11 curves around notes.
“slow/medium/fast” define how fast that curve moves.
This is ideal for long pads, textures or orchestral libraries that respond nicely to expression.

Seed
A number that drives the random generator. Same settings + same seed = same result. Change the seed to get a new variant without touching the musical setup.

Progression (8 bars)
Text field with 8 chord symbols separated by hyphens. Example:
i-iv-V-i-VI-ii°-V-i
Each symbol is interpreted inside your chosen mode. Even with minimal theory: copying and slightly editing the example progressions is enough to explore. If you enter fewer or more than 8, the app warns in the log.

Bars per loop per track
CSV list of 8 numbers. Each number is how many bars that track’s loop spans. Example default:
7,9,10,11,12,13,14,15
Track 1 will loop every 7 bars, track 2 every 9, etc, all driven by the same 8-bar progression grid. This is the heart of the evolving effect. Shorter numbers feel more repetitive, larger and varied numbers feel more organic.

Role set
Eight roles, one per track, chosen from: Bass, Ostinato, Pad, Melody, Counter, Arp, Drone, Sparkles. Roles define rhythmic patterns, register use, and how strongly notes stick to chord tones or scale tones. For a cinematic bed:

Track 1: Bass
Track 2: Ostinato
Track 3: Pad
Track 4: Melody (very soft, or use texture)
Track 5: Counter
Track 6: Arp or soft shimmer
Track 7: Drone
Track 8: Sparkles (very subtle)

Register profile
Defines default pitch ranges for each role.

“orchestral spread” gives a natural top to bottom ensemble layout.
“bass heavy” puts more weight in the low range.
“pads high” floats more energy higher.
“custom” lets you type 8 ranges such as 36-52,48-67,... if you want full control.

Melodic density
Controls how many of the potential rhythmic “slots” become actual notes. Lower for sparse drones, higher for more active patterns.

Accent cycle
Creates soft accent patterns in velocities, for repeated pulses that breathe over time.

Generate MIDI
Builds the multi-track Standard MIDI File. The default option exports one file containing all tracks. There is also an option label “Also 8 isolated tracks”. In this version the implementation notes mention it, but the main export already includes separate tracks inside one MIDI file, which most DAWs can split easily.

Improvise seed
Randomizes the seed field to give a new variant with the same musical settings.

Save / Load Preset
Saves all current settings (not the generated MIDI) to a JSON file and reloads them later. Useful for building your own “worlds”.

Piano-roll preview
Shows a colored overview per track so you can visually confirm density, ranges and overall flow before importing.

Log
Textual trace of what the generator is doing, and any warnings if input is malformed.
	4.	Suggested workflow for soundscape / film composers

Start from a preset that matches your emotional intent.
Adjust key, mode and tempo to fit your cue.
Tune the loop bar lengths so some tracks are “short breathers” (6–8 bars) and others are “slow tectonic plates” (12–20 bars).
Choose sounds in your DAW that blur attack and emphasize sustain: granular pads, reversed pianos, processed strings, modular beds, subtle pulses.
Print long audio stems from each MIDI track.
Use those stems inside the 8-Track Drone Mixer to turn them into self-running ambient beds.

—————————————————————————————————————————————————————————————————————————————
Manual 2: 8-Track Drone Mixer • Presets + WebM Recorder + LFO Pan
For turning your rendered stems into endless evolving drones.

The Drone Mixer is a browser-based 8-track player and performance tool. You load up to 8 audio files (for example, stems you rendered from Tonal Weave), shape them with volume, filters, reverb and pan LFOs, and record the result as a finished stereo file.
	1.	Core idea

You are not sequencing here. All musical “composition” happened earlier.
In this app you:
	1.	Load your prepared drone-friendly samples.
	2.	Let them loop and drift against each other.
	3.	Use crossfades, filters and auto-panning to create movement.
	4.	Record the full output to WebM (or WAV fallback) with one click.
	5.	First session: from zero to a recorded drone
	6.	Open the HTML file in a modern browser.
	7.	In Track 1, click “Sample laden” and choose a long, low stem.
	8.	Repeat for a few more tracks with complementary textures.
	9.	Leave “Loop” enabled on each track so they repeat seamlessly.
	10.	Press “Play All”. The app:
	1.	Starts all loaded tracks.
	2.	Applies random start offsets if enabled, so they do not align mechanically.
	3.	Starts recording the master output automatically.
	11.	Adjust Master volume so it is comfortable on your system, and Master reverb for overall space.
	12.	Gently move the crossfade sliders (1–2, 3–4, etc) to bring pairs in and out.
	13.	Let it run until you are happy.
	14.	Press “Stop All”. Recording stops and a download link appears. Click it to save your stereo mix.
	15.	Global controls

Play All
Starts all tracks that have a loaded sample. If “Random start” is enabled for loops, each track begins a little later inside its file to avoid identical downbeats.

Pause All
Pauses all currently playing tracks by triggering their “Play/Pause” logic. Use it if you want to stop without resetting loop positions.

Stop All
Stops all tracks, resets their internal position, and stops the recording. Use this when you are done with a take.

Master Volume
Controls overall output level before the recorder.

Master Reverb
Sets how much of the global, built-in reverb is mixed into the output.

Crossfade 1–2, 3–4, 5–6, 7–8
Each pair controls the balance between two tracks routed into a shared crossfade group.
Slider center means both are equal.
Move towards one side to foreground that track and dim the other.
Use this for slow morphs between textures.

Auto crossfade (Auto + Speed)
If “Auto” is checked for a pair, the app moves that crossfade slider for you in a smooth sinus curve.
“Speed” is the cycle length in seconds. Larger values are slower movements.
This is perfect for fully hands-off evolving beds.

Random start / Max offset
If enabled, when you press Play All:
	1.	Each looping track is given a random start offset up to “Max offset (s)”.
	2.	This prevents phasey repetition and creates a more organic cloud.

Presets: Save / Load / Clear All
Save Preset stores:
	1.	All mixer settings per track (volume, pan, pitch, filter, reverb send, LFO settings, loop flags).
	2.	The loaded audio files themselves as base64 inside the JSON.

This means you can later Load Preset and restore the complete session, including samples, in one go in the same browser environment.
Clear All empties all tracks and stops playback and recording.
	4.	Per-track controls

Each of the 8 tracks has:

Sample laden
Opens a file browser to load an audio file (any browser supported audio). Status turns green when loaded.

Play / Stop
“Play” starts the track. When it plays, the button becomes “Pause”.
“Stop” stops and resets to the beginning.

Loop
If checked, the sample restarts automatically at the end. For drones you almost always leave this on.

Gain
Track volume inside the mix.

Pan
Base stereo position. The LFO Pan will modulate around this center.

Pitch
Transposes playback in semitones. Useful to tune textures against each other or your project key.

Filter (cutoff + type)
Lets you darken or thin out the sound.

“Off” uses an allpass (no tonal change).
“Low-pass” removes highs, ideal for softer beds.
“High-pass” removes lows, ideal for airy noise layers.

Reverb send
How much of this track goes into the global reverb.

LFO Pan (per track)
Simple auto-pan dedicated to slow movement.

On
Enables or disables the LFO for this track.

Speed (s/osc)
Time in seconds for one full pan cycle.

Depth
How wide the pan swings around the base pan.
Small depth: gentle drift.
Large depth: wide stereo motion.
	5.	Recording

When you hit “Play All”:
	1.	The app starts capturing the mixed output.
	2.	If your browser supports it, it records as WebM/Opus.
	3.	If not, it falls back to an internal WAV recorder.

When you hit “Stop All”:
	1.	Recording stops.
	2.	A download link appears below (“Download mix_YYYY-MM-DD_HH-MM-SS.webm” or “.wav”).
	3.	Save this file and use it directly as an ambient bed in your DAW or soundtrack project.

You can make multiple long takes with different combinations of stems, crossfade speeds and LFO settings, and build a library of bespoke evolving drones.
	6.	Practical pairing with Tonal Weave

Generate 8-track MIDI in Tonal Weave.
Assign each role to a complementary soft synth or sampler.
Bounce each track separately as a long, seamless audio stem (for example 10 seconds upto 2 minutes).
Load those stems into the Drone Mixer, group them logically into crossfade pairs (low vs mid, pad vs texture, etc), set very slow auto crossfades and pan LFOs, then print a long stereo take.
You now have a fully custom, harmonically disciplined, endlessly evolving soundscape that is still quick to reproduce and tweak.
—————————————————————————————————————————————————————————————————————————————

Have fun! Thank you for mentioning Jeroen KJM Sparla in your productions ;-)

