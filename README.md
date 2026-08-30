# IP Paris Seminar Incentives and Computation

Website for the seminar on incentives and computation at Institut Polytechnique de Paris.

**Live site:** https://julprat.github.io/ip-paris-incentives-computation/

The whole site is one file, `index.html`, with the CSS inline. There is no build step: edit the
file, commit, push, and GitHub Pages redeploys within a minute.

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
| Co-organizer names | `<!-- ORGANIZERS` marker — replace the two placeholder `<li>` blocks and remove `class="placeholder"` |
| Location, once confirmed | Two places: the `meta-line` in the header and the Location row in the Next session card |
| "Last updated" date | Bottom of the file, in `<footer>` |

## Local preview

    open index.html
