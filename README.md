# Noise Logger

A single-page noise-level logger that runs in a laptop browser. It turns the
microphone signal into one loudness number every 100 ms and logs one row per
second (average and max dB). No audio is saved or sent anywhere; the numbers
are stored only in the browser that runs the page.

- Live level, the day's Leq, loud-event count, a chart of the day with events
  shaded, and by-hour charts of Leq and event counts.
- Loud event: the level stays above the rolling 10-minute median by a margin
  (default 12 dB) for at least 0.5 s. Events less than 3 s apart are merged.
- Export a levels CSV, an events CSV and a one-page PNG summary per day.
- The dB offset approximates real-world dB from the mic's raw level. Levels
  are relative, not calibrated.

The page needs HTTPS or localhost for microphone access, so it is served from
GitHub Pages. To run it locally:

```bash
python3 -m http.server 8792
```

Then open http://localhost:8792. Keep the tab open and the laptop awake while
logging.
