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
- **Progress tracking** (📈 Progress): per-lick history with an accuracy-by-pass chart, best accuracy at each speed, a goal tempo with a "mastered" mark (90%+ twice at your goal), practice time and streak. A **bar-by-bar trouble-spot map** shows where you miss or play wrong notes, and you can tap bars to loop them or use "Loop my weakest bars". The app suggests a next step (speed up, slow down, or focus on weak bars) and reports whether you tend to play early or late, with a one-tap latency adjustment. Export and import your progress as a file. Everything is saved in your browser.
- **Imported licks** are saved in your browser too.

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

- **Fingerstyle / solo arrangements** (one track with melody, chords and bass together, like guitar tabs exported from Guitar Pro): the importer detects this, keeps the top notes as the melody, and plays the notes underneath as the backing band, with chords detected from them.
- **MIDI**: if the file has several tracks, the app picks the most likely melody track (by name, single-note lines and range). You can change it in the track menu. Where notes overlap, the highest note is kept.
- **MusicXML**: if the file contains a transposition (for example an alto sax part), it is applied automatically. Chord symbols (`<harmony>`) in the file are read into the chord chart, so they show above the notes and drive the backing band. They follow the same *Pitches are* setting as the notes. You can still change them with ✏ Chords….
- Choose whether the file's pitches are **concert pitch** or **written for your horn**.

Timing is snapped to a sixteenth or triplet-eighth grid so the notation stays readable.

### Fixing mistakes (scanned music)

Music that was converted from a PDF or photo by a scanning program (for example Audiveris, MuseScore or PlayScore) usually has a few wrong notes. Open the lick, switch to the notation view and press **✎ Edit notes**. Tap a note, compare it with your page, then change its pitch (♯/♭ or octave), make it shorter or longer, move it a sixteenth earlier or later, add a note after it, or delete it. **Undo** goes back one step, and edits are saved on your device. If you edit a built-in lick, the app edits a copy.

## Built-in practice lines

The lick menu is grouped:

- **Warm-ups**: scales, a blues lick, a ii–V–I pattern and a chromatic exercise.
- **Bebop & enclosures (concert C)**: twelve original lines with chords: bebop scales, enclosures of the root, 3rd and 5th, a minor ii–V–i, chromatic approach notes, a ♭9 cell, a turnaround and a blues phrase. Use the **Key** menu, or **Practice all keys**, to play them in every key.
- **Beginner exercises (written for alto)**: long tones, scales, arpeggios, rhythm patterns and simple folk tunes (Hot Cross Buns, Mary Had a Little Lamb, Twinkle Twinkle, Ode to Joy and others), printed the way a beginner alto book writes them. The Key menu shows concert key names, so the original key appears as E♭.

The same lines are also provided as MusicXML files (`Sax-Tutor-practice-lines.zip`) that can be added one at a time with **＋ Import / type a lick**.

## Phones and tablets

- **Android (Chrome):** MIDI works over USB-OTG or Bluetooth MIDI, the same as on a computer.
- **iPhone and iPad:** Safari and Chrome on iOS don't support Web MIDI. A browser app that adds it (for example MidiWeb) lets a MIDI controller connect, so open the app's address inside that browser. The microphone mode also works in any iOS browser.
- On narrow screens the controls collapse into tappable cards, and Start/Pause/Stop, speed and note stepping stay pinned at the bottom. The screen is kept awake while you play where the browser allows it.
- Home-screen "web app" mode on iOS uses Safari's engine and has no MIDI, so use a browser tab instead.

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
