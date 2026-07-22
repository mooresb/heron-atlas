# Heron Atlas

An interactive, **single-file** data visualization mapping every extant heron species (family *Ardeidae*) of the world — where each one lives, how threatened it is, and how the migratory ones move across the seasons.

The entire app is one self-contained `index.html`: all CSS, JavaScript, fonts, icons, the mapping library, and the data are inlined, so it runs in any modern browser with **no build step and no internet connection**.

## Viewing it

- **Locally:** open `index.html` in any modern browser (double-click it, or drag it into a browser window).
- **On the web (GitHub Pages):** in this repo, go to **Settings → Pages**, set the source to **Deploy from a branch** → **`main`** / **`/ (root)`**, and save. Your dashboard will be live at `https://<your-username>.github.io/heron-atlas/` within a minute or two.

Because everything is inlined, opening the file directly works too — but for phones it's most reliable over a real URL (Pages, or a local server), since some in-app file previews don't execute JavaScript.

## What's inside

The dashboard has four views, switched from the top navigation (a tab strip on phones, a sidebar and top nav on larger screens):

- **Species Atlas** — a world map plotting every location each heron species occurs, colored by IUCN Red List status and sized by how many species share a location. Pick a species (from the finder or the Conservation Watch list) to isolate it on the map; filter the whole map by conservation status.
- **Spotlight** — a data-rich profile for any of the species: size, population, conservation status, habitat, diet, and a **Seasonal Chronology** month-scrubber showing where the species is recorded through the year.
- **Species Gallery** — the full collection of species, grouped by type (herons, egrets, night herons, pond herons, tiger herons, bitterns), each with its key traits and range.
- **Citations** — the data sources behind every figure, with attribution.

It's fully responsive — a single-column, map-first layout on phones, a two-column layout on tablets, and the full map-background-with-floating-panels layout on desktop. Light and dark themes and metric/US units are toggleable in the header.

## How it's built

- **Tailwind CSS** — compiled from the design tokens and inlined (no CDN dependency).
- **Leaflet** — draws the world map from inlined vector country polygons (no map tiles required, so it renders offline).
- **Fonts & icons** — Playfair Display, Hanken Grotesk, JetBrains Mono, Sora, and a subset of Material Symbols, all embedded as data URIs.
- **Data** — the species records, occurrence points, traits, migration tracks, and monthly distribution cubes are embedded as JavaScript globals, all joined on scientific name (IOC taxonomy).

## Data sources & attribution

The figures come from open ornithological datasets, credited in full on the **Citations** tab inside the app:

- **IOC World Bird List** — taxonomy (scientific names, the join key across everything).
- **IUCN Red List** — conservation status.
- **GBIF** — species occurrence points (used for the map and residence lists). GBIF occurrence downloads are cited by their DOI in the app.
- **eBird Status & Trends** — breeding / non-breeding ranges for the migratory species.
- **Wikidata / Birds of the World** — body measurements and traits.

A note on honesty in the data: nothing is invented. Fields are left blank where a value is genuinely unknown, and a species only shows a seasonal/migration arc when eBird Status & Trends actually models it — the absence of an arc for a poorly-surveyed tropical heron is accurate, not a gap.

The species portraits in the gallery are **AI-generated and illustrative only** — they may not accurately reflect a species' real appearance, size, or scale. For verified photographs and reference imagery, see the Macaulay Library (Cornell Lab of Ornithology).

## Credits

Data assembly and visualization by **Sarah Moore**, data-viz engineer and birder.

---

*Heron Atlas is an interactive prototype for exploring the global distribution and conservation of the world's herons.*
