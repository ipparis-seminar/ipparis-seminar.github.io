# IP Paris Seminar Incentives and Computation

Website for the seminar on incentives and computation at Institut Polytechnique de Paris.

**Live site:** https://ipparis-seminar.github.io/

The site is `index.html` with the CSS inline, plus two logo images. There is no build step: edit
the file, commit, push, and GitHub Pages redeploys within a minute.

| File | Used for |
|---|---|
| `index.html` | The whole page, CSS inline |
| `ip-paris-logo.png` | IP Paris mark + wordmark, in the header |
| `ip-paris-schools.png` | The five member schools, in the footer |

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

## Other things to update

| What | Where |
|---|---|
| Co-organizer names | `<!-- ORGANIZERS` marker — replace the remaining placeholder `<li>` and remove `class="placeholder"`, or delete the `<li>` if there is no third organizer |
| Location, once confirmed | Two places: the `meta-line` in the header and the Location row in the Next session card |
| "Last updated" date | Bottom of the file, in `<footer>` |
| Links | External links carry `target="_blank" rel="noopener"`; keep that on any new ones. The `mailto:` link deliberately does not. |
| Logos | Replace `ip-paris-logo.png` / `ip-paris-schools.png`, keeping the `width`/`height` attributes on the `<img>` tags in sync |

## Local preview

    open index.html
