# Album Drum Curriculum Package

This package consolidates the 20-song curriculum into a single app-ready structure and expands songs 11-20 into scaffolded curriculum modules. It also includes a deep-dive master-class treatment for one flagship song.

## Build rationale
- Abe Cunningham's style is strongly associated with groove, dynamics, atmosphere, and ghost-note-aware backbeat playing rather than constant technical density. [web:8][web:11][web:45]
- Electronic and hybrid drumming workflows benefit from relaxed, repeatable pattern building and sound consistency, which suits an album-driven learning system. [web:11][web:45]
- Practice routines are most effective when they combine warmup, focused exercises, songs, and creative application, which matches this album-as-curriculum design. [web:56]
- Logic Pro can route and translate drum ideas into Superior Drummer through MIDI-based workflows, which supports building each song as a repeatable module. [web:41][web:55][web:61]

## Full schema

```ts
type DrumCurriculumSong = {
  id: number;
  slug: string;
  title: string;
  influences: string[];
  stage: 1 | 2 | 3 | 4 | 5;
  difficulty: 1 | 2 | 3 | 4 | 5;
  tempoRangeBPM: { min: number; max: number };
  primaryMeter: string;
  feel: string;
  tonalCenter: string;
  tuningNotes: string;
  sections: { name: string; bars: number; description: string }[];
  arrangementTimeline: { track: "Drums" | "Guitars" | "Bass" | "Moog"; summary: string }[];
  drumGoals: string[];
  limbFocus: string[];
  kitFocus: string[];
  groove: { label: string; description: string; meter: string; asciiNotation: string }[];
  fills: { label: string; description: string; asciiNotation: string }[];
  practiceBpmLadder: number[];
  milestones: string[];
  roadmap: string;
  commonMistakes: string[];
  dynamicsNotes: string;
  logicNotes: {
    midiRecordingTips: string;
    quantizeStrategy: string;
    humanizeStrategy: string;
    superiorDrummerMapTips: string;
  };
  guitars: { role: string; chordIdeas: string; effectNotes: string }[];
  bass: { role: string; patternIdea: string; effectNotes: string };
  moog: { role: string; motifIdea: string; modulationNotes: string };
  tags: string[];
};
```

## 20-song overview table

| # | Title | Stage | Difficulty | Main focus |
|---|---|---:|---:|---|
| 1 | Tide of Static | 1 | 1 | Slow backbeat, restraint, hat control |
| 2 | Glass Cities | 1 | 2 | 16th hats, dance feel, offbeat kicks |
| 3 | Ashen Bloom | 1 | 2 | Ghost notes, slow shoegaze dynamics |
| 4 | Black Circuit Sky | 2 | 3 | Heavy single-kick stamina, restrained thrash |
| 5 | Neon Bones | 2 | 2 | Alt-rock pocket, open hats, short fills |
| 6 | Midnight Static | 2 | 2 | New-wave endurance, disco kick/hats |
| 7 | Echo Harbors | 2 | 3 | Tom ostinato, long-form control |
| 8 | Wireframe Sleep | 3 | 3 | 7/8 to 4/4 transitions |
| 9 | Frozen Lanterns | 3 | 3 | Ride drive, tom variation, half-time drop |
| 10 | City of Haze | 3 | 4 | Fast rock stamina, breakdown control |
| 11 | Fractured Neon | 3 | 3 | Four-on-the-floor + rock sync hybrid |
| 12 | Red Sand Engine | 3 | 3 | Swung sludge-blues pocket |
| 13 | Spectral Lines | 3 | 2 | Sparse ambient timekeeping |
| 14 | Mercury Teeth | 4 | 4 | Mid-tempo heavy riff support |
| 15 | Horizon Collapse | 4 | 3 | Post-metal build architecture |
| 16 | Broken Neon Saints | 4 | 4 | Faster punk/hardcore control |
| 17 | Signal Drift | 4 | 2 | Ambient repetition and dynamic patience |
| 18 | Chrome Narrows | 5 | 4 | Linear groove coordination |
| 19 | Afterimages of Heat | 5 | 4 | 6/8 to 4/4 transitions, cinematic ending |
| 20 | Iron Halos Suite | 5 | 5 | Consolidation track: sludge, groove, fills, pacing |

## Consolidated data model notes
- Songs 1-10 are considered fully authored modules.
- Songs 11-20 below are scaffolded at enough depth to begin app integration and practice testing.

## Songs 11-20 scaffold modules

### Song 11 — Fractured Neon
- Influences: Deadmau5, Radiohead, electronic rock. 
- Stage/Difficulty: 3 / 3.
- Tempo: 122-128 BPM, 4/4.
- Focus: four-on-the-floor kick endurance, offbeat guitar integration, synth-led drop discipline.
- Core groove:
  ```
  Count: 1e&a 2e&a 3e&a 4e&a
  Kick : K--- K--- K--- K---
  Snare: ---- S--- ---- S---
  HH   : x-x- x-x- x-x- x-x-
  ```
- Album challenge: move from straight quarter kicks to occasional syncopated extra kick on "& of 3" without disturbing the dance pulse.
- Logic note: hard-quantize the quarter-note kicks, lighter quantize on hats to preserve hand feel. [web:41][web:61]

### Song 12 — Red Sand Engine
- Influences: sludge, blues rock, Mastodon-adjacent heaviness.
- Stage/Difficulty: 3 / 3.
- Tempo: 84-96 BPM, swung 4/4.
- Focus: heavy laid-back pocket, ride bell time, snare authority.
- Core groove:
  ```
  Count: 1 & 2 & 3 & 4 &
  Kick : K - - - K - - -
  Snare: - - S - - - S -
  Ride : R - R - R - R -
  ```
- Add a dragged kick before beat 3 once base time is stable.
- Bass should lock to kick and leave space after beat 2.

### Song 13 — Spectral Lines
- Influences: Pink Floyd, ambient rock.
- Stage/Difficulty: 3 / 2.
- Tempo: 60-70 BPM.
- Focus: sparse timekeeping, rim-click control, cymbal swells.
- Core groove:
  ```
  Count: 1 & 2 & 3 & 4 &
  Kick : K - - - K - - -
  Snare: - - C - - - C -   (cross-stick)
  HH   : - - - - - - - -
  ```
- Goal: make silence feel intentional; no overplaying.
- Moog pad should lead section changes, not the drums.

### Song 14 — Mercury Teeth
- Influences: Mastodon, Tool.
- Stage/Difficulty: 4 / 4.
- Tempo: 98-112 BPM.
- Focus: sync with chug riffs, half-time bridge, tom accents.
- Core groove:
  ```
  Count: 1 & 2 & 3 & 4 &
  Kick : K - K - K - - -
  Snare: - - S - - - S -
  HH   : x x x x x x x x
  ```
- Bridge variation: snare on 3, floor tom on "& of 2".
- Keep double pedal only as a 2-note pickup into transitions.

### Song 15 — Horizon Collapse
- Influences: Russian Circles, post-metal.
- Stage/Difficulty: 4 / 3.
- Tempo: 72-84 BPM.
- Focus: section growth, cymbal restraint, tom phrasing.
- Core groove:
  ```
  Count: 1 & 2 & 3 & 4 &
  Kick : K - - - - - K -
  Snare: - - - - S - - -
  FT   : - - T - - - T -
  ```
- Goal: crescendo over 16 bars without speeding up.
- Logic note: automate MIDI velocities upward over the build rather than manually overplaying.

### Song 16 — Broken Neon Saints
- Influences: AFI, Thrice, melodic hardcore.
- Stage/Difficulty: 4 / 4.
- Tempo: 146-162 BPM.
- Focus: fast hats, simple punk kick, chorus crash endurance.
- Core groove:
  ```
  Count: 1 & 2 & 3 & 4 &
  Kick : K - - - K - K -
  Snare: - - S - - - S -
  HH   : x x x x x x x x
  ```
- Treat as stamina sibling to City of Haze, but slightly more melodic and less dense.
- Practice in 30-second bursts to avoid sloppy high-tempo habits. [web:60]

### Song 17 — Signal Drift
- Influences: ambient post-rock, Sigur Rós, shoegaze.
- Stage/Difficulty: 4 / 2.
- Tempo: 66-74 BPM.
- Focus: patience, repetition, slight dynamic arcs.
- Core groove:
  ```
  Count: 1 & 2 & 3 & 4 &
  Kick : K - - - - - - -
  Snare: - - - - S - - -
  HH   : x x x x x x x x
  ```
- This is a reset song between heavier modules.
- Use it to improve relaxed posture and time consistency.

### Song 18 — Chrome Narrows
- Influences: Tool, Deftones groove language.
- Stage/Difficulty: 5 / 4.
- Tempo: 96-108 BPM.
- Focus: simple linear groove sequencing, kick-snare-hat separation.
- Core groove:
  ```
  1e&a 2e&a 3e&a 4e&a
  K-H-S-H K-H-H-S
  ```
- Expand by orchestrating H notes between closed hat and splash.
- This is one of the clearest Abe-adjacent coordination studies because it emphasizes space, sequencing, and groove over flash. [web:8][web:11]

### Song 19 — Afterimages of Heat
- Influences: Deftones, Sigur Rós, Pink Floyd.
- Stage/Difficulty: 5 / 4.
- Tempo: 68-76 BPM in 6/8, then 72-80 BPM in 4/4 half-time.
- Focus: meter feel change, cinematic tom fills, ending control.
- Theme groove (6/8):
  ```
  Count: 1 2 3 4 5 6
  Kick : K - - - - -
  Snare: - - - S - -
  HH   : x x x x x x
  ```
- Heavy section: switch to 4/4 snare on 3 with big tom lead-ins.
- Use this as an emotional pacing exercise, not a complexity exercise.

### Song 20 — Iron Halos Suite
- Influences: sludge, dream metal, post-rock, alt metal.
- Stage/Difficulty: 5 / 5.
- Tempo: multiple sections, 72 / 96 / 112 BPM.
- Focus: final consolidation of everything learned — restraint, heavy pocket, hat openings, tom movement, half-time, selective speed.
- Suggested structure: Intro drone → slow riff groove → faster bridge → atmospheric break → final heavy reprise.
- Core learning idea: one long-form performance track that tests endurance, memory, and arrangement awareness.
- Milestones:
  - Complete all section transitions without stopping.
  - Maintain tempo integrity through 3 distinct feels.
  - Use no more than 3 fill types to avoid overplaying.

## Master class module: City of Haze

City of Haze is the best deep-dive candidate because it tests high-value skills without requiring advanced metal technique: fast 8th-note hats, dependable snare backbeats, compact motion, and a controlled half-time breakdown. Punk and post-hardcore drumming pedagogy consistently starts from a steady 8th-note hat pulse plus backbeat before adding kick variations, which matches this song's architecture. [web:60][web:56]

### Bar-by-bar practice plan
- Bars 1-4: hats only at target BPM, no kick or snare.
- Bars 5-8: add snare on 2 and 4.
- Bars 9-16: add kick on 1 and 3.
- Bars 17-24: upgrade verse groove to K on 1, & of 2, 3, and & of 3 only if stable.
- Bars 25-32: chorus with crash on bar 1 and 5, otherwise hats.
- Bars 33-40: breakdown; move snare to beat 3 and place floor tom on beat 1.
- Bars 41-48: return to verse groove, no fill.
- Bars 49-56: final chorus, same groove with more crashes.

### Three MIDI groove templates
1. Verse A (safe version)
   ```
   Count: 1 & 2 & 3 & 4 &
   Kick : K - - - K - - -
   Snare: - - S - - - S -
   HH   : x x x x x x x x
   ```
2. Verse B (album version)
   ```
   Count: 1 & 2 & 3 & 4 &
   Kick : K - K - K - K -
   Snare: - - S - - - S -
   HH   : x x x x x x x x
   ```
3. Breakdown
   ```
   Count: 1 & 2 & 3 & 4 &
   Kick : K - - - - - K -
   Snare: - - - - S - - -
   F1   : T - - - - - - -
   HH   : x x x x x x x x
   ```

### Suggested Logic region layout
- Region A: Intro pickup fill, 4 bars.
- Region B: Verse groove, 16 bars.
- Region C: Chorus groove, 8 bars.
- Region D: Verse groove with 1 fill variation, 16 bars.
- Region E: Breakdown groove, 8 bars.
- Region F: Final chorus groove, 8 bars.
- Region G: End crash tail, 2 bars.

This modular region approach is ideal in Logic because it lets you perfect one groove family at a time, then arrange the song from reusable blocks instead of forcing one full uninterrupted performance too early. [web:41][web:61]

### Superior Drummer suggestions
- Start with a tight modern rock kit and lower room mics for clarity at speed. [web:41]
- Map closed hats and slightly open hats clearly so chorus energy changes are obvious in the piano roll. [web:55]
- Keep snare velocity zones distinct: 70-80 for ghost/light notes, 105-120 for backbeats, so the groove remains readable and dynamic. [web:8]

### Physical coaching notes
- Use compact wrist motion for hats.
- Keep shoulders relaxed between phrases.
- Do not chase volume on the electronic kit; chase consistency and timing first, because hybrid/electronic workflows reward repeatable control more than brute force. [web:11][web:45]

## Recommended sequence for implementation
1. Put songs 1-10 into the app as full modules first.
2. Add songs 11-20 as scaffold modules with clear upgrade markers.
3. Build dedicated views for Song Ladder, Groove Builder, and Master Class mode.
4. Stress-test the progression physically by playing songs 5, 8, 10, 14, 18, and 20 in sequence; if that arc feels unrealistic, rebalance difficulty before expanding UI complexity.
