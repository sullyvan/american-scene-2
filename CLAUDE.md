# The American Scene 2.0
**A Federal Art Project for the Algorithmic Age**
Michael Sullivan · 2026 Proof of Concept

---

## What this project is

American Scene 2.0 is a proof-of-concept for an LACMA Art + Technology Lab grant proposal. It reimagines the New Deal's Federal Art Project (WPA, 1935–1943) as an AI-driven, distributed public art network for Los Angeles County.

The core argument: the WPA put civic art in post offices, schools, and hospitals across America. Algorithmic feeds have colonized that same public attention with engagement-optimized content. This project proposes using AI to regenerate a civic art infrastructure — autonomous, distributed, and ranked by bridging score rather than engagement.

---

## Project files

| File | Description |
|------|-------------|
| `american_scene_2.html` | Main POC — open in any browser, no server needed |

---

## How the app works

**Single HTML file** — fully self-contained, no dependencies, no build step. Open directly in Chrome/Safari/Firefox.

**Three systems running together:**

1. **AI Art Generation** — Pollinations.ai (free, no API key). Takes a civic theme + print style + artist agent and generates a WPA-aesthetic image.

2. **Artist Agents** — 20 LACMA collection artists (Rivera, Grosz, Daumier, Goya, Dix, Picasso, Kandinsky, Adams, Cartier-Bresson, Mapplethorpe, Ruscha, etc.) act as either:
   - **Creator**: shifts the generation prompt to their stylistic vocabulary
   - **Judge**: delivers a characteristic voice critique of the generated work

3. **Bridging Score** — computed live against 8 art-tradition clusters (Social Realism, Photography, Expressionism, Conceptual, Asian Art, Decorative Arts, Latin American, American Scene). Score 0–100 reflects how broadly the work resonates across traditions — *not* how many people clicked it.

**14 LACMA curators** (from real staff data) also serve as institutional voice agents — their departmental responses appear in judge rotation.

---

## The Bridging Score explained

Based on the Bridging-Based Ranking framework (Twitter/Jigsaw research). Instead of optimizing for engagement within a community, it ranks content by resonance *across* different groups.

In this app: a work that only appeals to German Expressionists scores ~20. A work that activates Social Realism + Photography + Latin American + American Scene clusters scores 70+. The goal at 50,000 nodes is a score that spans zip codes, languages, and art traditions simultaneously.

---

## Next development steps

- [ ] Replace simulated node grid with real Leaflet.js map of LA County
- [ ] Add localStorage persistence so the archive accumulates across sessions
- [ ] Wire a scheduled task to auto-generate one civic work per hour (unmanned broadcast)
- [ ] Add real Claude API call for judge voices (currently pre-written character responses)
- [ ] Build the curator review panel as a separate page/modal
- [ ] Explore WebSocket distribution to simulate real node updates

---

## Context for Claude Code

When working on `american_scene_2.html`:
- It's a single-file app — all HTML, CSS, and JS live in one file
- The ARTISTS array (~line 200) contains all artist agent data including keyword profiles
- The CURATORS array contains LACMA staff institutional voices
- The CLUSTERS array (8 clusters) defines the bridging score computation
- `computeBridgingScore()` is the core algorithm — keyword matching against corpus
- Images load from `https://image.pollinations.ai/prompt/{encoded}` — this is a free external API
- No build tools, no npm, no server required

---

## LACMA proposal context

Submitted to the 2026 Art + Technology Lab Grant (deadline Thu Apr 25, 2026).
Grant range: $10,000–$50,000. Residents may also receive in-kind support.
Previous participants include IBM, SpaceX, Intel, Nvidia, NASA Jet Propulsion Laboratory.

The proposal title is "The American Scene 2.0." This POC is the working demonstration that the concept is technically viable and scalable.
