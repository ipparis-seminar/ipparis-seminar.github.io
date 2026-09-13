# IP Paris Seminar Incentives and Computation

Website for the seminar on incentives and computation at Institut Polytechnique de Paris.

**Live site:** https://ipparis-seminar.github.io/

The site is `index.html` with the CSS inline, plus two logo images and two calendar files. There is no build step: edit
the file, commit, push, and GitHub Pages redeploys within a minute.

| File | Used for |
|---|---|
| `index.html` | The whole page, CSS inline |
| `ip-paris-logo.png` | IP Paris mark + wordmark, in the header |
| `ip-paris-schools.png` | The five member schools, in the footer |
| `seminar.ics` | Subscribable calendar feed — every session, one file |
| `seminar-2026-10-12.ics` | Single-session download for the October talk |

Both images are cropped from the official IP Paris lockup and have a solid white background, so the
page is deliberately light-only — there is no dark-mode stylesheet, and `color-scheme: light` is set
on `:root`. If you ever add a dark mode, the logos need transparent or white-on-dark variants first.

## Adding a talk

1. Open `index.html` and find the `<!-- SCHEDULE START -->` marker.
2. Copy the commented-out template row just below the existing rows, uncomment it, and fill in the
   date, speaker, affiliation and title. Keep rows in chronological order.
3. If the talk you added is the next one coming up, also update the **Next session** card — search
   for `<!-- NEXT SESSION` near the top of the body — and drop the `tba` class from any field you
   have now filled in.
4. Add the same talk to `seminar.ics` (see below). This is easy to forget — the website and the
   calendar feed are maintained separately.

## The calendar feed

`seminar.ics` is what people subscribe to; the links sit under the schedule table. Copy an existing
`VEVENT` block and edit it. Three rules:

- **Times are in UTC** (the trailing `Z`). Paris is UTC+2 in summer, UTC+1 from late October, so a
  2:00 pm talk is `120000Z` in October but `130000Z` in November. Get this wrong and the talk shows
  up an hour off in everyone's calendar.
- **`UID` must be unique per talk and must never change.** Subscribers' calendars match on it, so
  editing an event in place updates it for everyone; changing the `UID` creates a duplicate instead.
  The convention here is `YYYY-MM-DD-speaker@ipparis-seminar.github.io`.
- **Commas and semicolons inside text need escaping** as `\,` and `\;`. Lines over 75 characters
  wrap with a single leading space on the continuation.

Placeholder entries for dates without a confirmed speaker are fine — keep the `UID` when you fill in
the real name and it updates in place.

After pushing, subscribers pick up changes on their client's own schedule: Apple Calendar within
minutes to hours, Outlook every few hours, Google often a day or more. Don't rely on the feed for
last-minute changes — email those.

## Other things to update

| What | Where |
|---|---|
| Co-organizer names | `<!-- ORGANIZERS` marker — uncomment the commented-out `<li>` template and fill it in |
| Location, once confirmed | Two places: the `meta-line` in the header and the Location row in the Next session card |
| "Last updated" date | Bottom of the file, in `<footer>` |
| Links | External links carry `target="_blank" rel="noopener"`; keep that on any new ones. The `mailto:` link deliberately does not. |
| Logos | Replace `ip-paris-logo.png` / `ip-paris-schools.png`, keeping the `width`/`height` attributes on the `<img>` tags in sync |

## Local preview

    open index.html
