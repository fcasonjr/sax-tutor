# 🎷 Sax Tutor

A browser-based practice app for saxophone, built for working through jazz licks. Follow along with scrolling colour-coded notes or standard notation, slow things down, loop tricky bars, and get scored live from a MIDI wind controller (such as the Roland Aerophone AE-20) or a microphone.

It's a single `index.html` file with no dependencies and no build step.

## Features

- **Game view**: colour-coded notes scroll toward a hit line, with a fingering diagram for the current and upcoming notes. Each note is graded Perfect, Good, OK, Missed or Wrong, with combo and timing stats.
- **Fingering view**: the staff on top with note letters, and below it one lane per key (octave key, left hand, right hand, side and pinky keys). Blocks scroll toward circles that light up when that key should be down, so the fingers line up with the notes as they arrive.
- **Notation view**: a staff with a moving playhead and optional note letters above or below. Tap a bar to set the loop start and another to set the end.
- **Step through**: move one note at a time with the Prev/Next buttons or the arrow keys, hearing each note. Tick "Advance when I play it" to move on whenever you play the note shown.
- **Practice tools**: speed from 25% to 150%, bar-range looping, count-in, metronome, "Hear the lick", "Wait for me" mode, and swing.
- **Practice all keys**: run a lick around the circle of 4ths, up by semitone or whole tone, or down in 4ths. The register refits to your horn each time.
- **Horn selection**: alto, tenor, soprano, baritone or concert pitch. Notation, note names and fingerings follow the horn you choose.
- **Backing track**: chords appear above the notes in every view, transposed for your horn. The app plays a generated walking bass, piano comping and drums from the chord chart in Swing, Ballad or Bossa styles. For an imported MIDI file with other tracks, it can play the original band instead, and it detects a first-draft chord chart from the piano and bass. Edit chords any time with **✏ Chords…**.
- **Import**: MIDI (`.mid`), MusicXML (`.xml`, `.musicxml`) and compressed MusicXML (`.mxl`), or type a lick directly.
- **Progress**: best and last accuracy per lick, and the fastest tempo played at 90% or better. Imported licks and progress are saved in your browser.

## Getting started

1. Open the page in **Chrome or Edge** (desktop or Android). Safari does not support Web MIDI.
2. Choose your horn under **Horn & key**.
3. Pick a lick and press **Start** (or `Space`).

### Using a MIDI wind controller

1. Connect the instrument by USB or Bluetooth MIDI, then press **Connect MIDI** and allow access.
2. Press **Calibrate MIDI** and play the highlighted note. This corrects any octave or transposition difference between your instrument and the app.
3. If hits consistently read early or late, adjust the **Latency** slider.

### Using a microphone

Press **Mic** and allow access. Use headphones so the app's own playback isn't picked up. Mic mode detects pitch changes, so repeated notes on the same pitch aren't registered.

### No instrument connected

For testing, the computer keyboard works as a fallback: `A S D F G H J K` are the white keys, `W E T Y U` the black keys, and `Z` / `X` change octave.

## Chord charts

In **✏ Chords…**, write bars separated by `|`, in concert pitch:

```
| Dm7 | G7 | Cmaj7 | Cmaj7 |
```

Two chords in a bar share it evenly. Give beats with a colon (`Dm7:3 G7:1`), or use `%` as its own bar to repeat the previous bar. Common symbols like `m7b5`, `dim7`, `7#9`, `13`, `sus4` and slash chords (`Ebmaj7/G`) are understood. Tick "Repeat the chart to fill the song" to loop a short chart over a longer lick.

## Typing a lick

Use **Import / type a lick** and enter notes as `NoteOctave/length`:

```
D4/e F4 A4 C5 B4 G4 E4 C4/q r/q
```

| Code | Meaning |
|------|---------|
| `w` `h` `q` `e` `s` | whole, half, quarter, eighth, sixteenth |
| `t` | triplet eighth |
| `.` after a length | dotted (for example `q.`) |
| `#` / `b` after the letter | sharp / flat (for example `F#4`, `Bb3`) |
| `r` | rest |

A length carries over to following notes until you change it. Use `|` as an optional bar separator.

## Importing files

- **MIDI**: if the file has several tracks, the app picks the most likely melody track (by name, single-note lines and range). You can change it in the track menu. Where notes overlap, the highest note is kept.
- **MusicXML**: if the file contains a transposition (for example an alto sax part), it is applied automatically.
- Choose whether the file's pitches are **concert pitch** or **written for your horn**.

Timing is snapped to a sixteenth or triplet-eighth grid so the notation stays readable.

## Keyboard shortcuts

| Key | Action |
|-----|--------|
| `Space` | Start / pause |
| `Esc` | Stop |
| `V` | Cycle through game, fingering and notation views |
| `←` / `→` | Step to the previous / next note |

## Limitations

- Fingerings cover written B♭3 to F♯6, including the palm keys and side E / high F♯ keys. Altissimo notes above that show a "see your chart" message.
- Imported scores are reduced to a single melodic line. Repeats, voltas and grace notes are ignored.
- Only partwise MusicXML is supported.
- Web MIDI and microphone access require a browser and hosting that allow them (a normal web page, not an embedded preview).

## Running locally

Open `index.html` in a browser, or serve the folder with any static server. To publish, host the file on any static host such as Netlify, GitHub Pages or Cloudflare Pages.
