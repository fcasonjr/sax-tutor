# 🎷 Sax Tutor

A browser-based practice app for saxophone, built for working through jazz licks. Follow along with scrolling colour-coded notes or standard notation, slow things down, loop tricky bars, and get scored live from a MIDI wind controller (such as the Roland Aerophone AE-20) or a microphone.

It's a single `index.html` file with no dependencies and no build step.

## Features

- **Game view**: colour-coded notes scroll toward a hit line, with a fingering diagram for the current and upcoming notes. Each note is graded Perfect, Good, OK, Missed or Wrong, with combo and timing stats.
- **Notation view**: a staff with a moving playhead. Tap a bar to set the loop start and another to set the end.
- **Practice tools**: speed from 25% to 150%, bar-range looping, count-in, metronome, "Hear the lick", "Wait for me" mode, and swing.
- **Practice all keys**: run a lick around the circle of 4ths, up by semitone or whole tone, or down in 4ths. The register refits to your horn each time.
- **Horn selection**: alto, tenor, soprano, baritone or concert pitch. Notation, note names and fingerings follow the horn you choose.
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

- **MIDI**: if the file has several tracks, pick the melody track. Where notes overlap, the highest note is kept.
- **MusicXML**: if the file contains a transposition (for example an alto sax part), it is applied automatically.
- Choose whether the file's pitches are **concert pitch** or **written for your horn**.

Timing is snapped to a sixteenth or triplet-eighth grid so the notation stays readable.

## Keyboard shortcuts

| Key | Action |
|-----|--------|
| `Space` | Start / pause |
| `Esc` | Stop |
| `V` | Switch between game and notation view |

## Limitations

- Fingerings cover written Bb3 to C♯6. Palm-key notes above that show a "see your chart" message.
- Imported scores are reduced to a single melodic line. Repeats, voltas and grace notes are ignored.
- Only partwise MusicXML is supported.
- Web MIDI and microphone access require a browser and hosting that allow them (a normal web page, not an embedded preview).

## Running locally

Open `index.html` in a browser, or serve the folder with any static server. To publish, host the file on any static host such as Netlify, GitHub Pages or Cloudflare Pages.
