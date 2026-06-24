# The American Scene 2.0
### A Federal Art Project for the Algorithmic Age

A proof-of-concept for the [LACMA Art + Technology Lab Grant](https://www.lacma.org/lab), 2026.
Built by Michael Sullivan.

---

## What it is

The WPA's Federal Art Project (1935–1943) put civic murals in post offices, schools, and hospitals across America — the largest public art program in U.S. history. Algorithmic feeds have since colonized that same public attention, optimizing for engagement rather than community.

**American Scene 2.0** proposes using AI to rebuild that civic infrastructure: an autonomous, distributed network that generates WPA-style art from civic themes and broadcasts it to community display nodes — ranked by bridging score, not clicks.

---

## Setup

No installation. No server. No API key.

1. Download `american_scene_2.html`
2. Open it in any browser (Chrome, Safari, Firefox)
3. That's it

Images are generated live via [Pollinations.ai](https://pollinations.ai) — a free, open image generation API.

---

## How it works

**Pick a civic theme** — transit workers, community gardens, water rights, public housing — or type your own.

**Choose a print style** — WPA mural, lithograph, silkscreen, woodcut, documentary photograph.

**Select an artist agent** from the LACMA permanent collection:

| Artist | Tradition | Works at LACMA |
|--------|-----------|----------------|
| Diego Rivera | Mexican Muralism | 205 |
| George Grosz | German Expressionism | 189 |
| Honoré Daumier | French Caricature | 586 |
| Francisco Goya | Spanish Romanticism | 92 |
| Otto Dix | New Objectivity | 86 |
| Pablo Picasso | Cubism | 91 |
| Wassily Kandinsky | Abstraction | 97 |
| Ansel Adams | American Photography | 142 |
| Henri Cartier-Bresson | Street Photography | 144 |
| Robert Mapplethorpe | Studio Photography | 1,090 |
| Edward Ruscha | LA Conceptual | 202 |
| Katsushika Hokusai | Ukiyo-e | 126 |
| Utagawa Hiroshige | Ukiyo-e Landscape | 215 |
| Rufino Tamayo | Mexican Modern | 98 |
| *+ 6 more* | | |

Artists operate in two modes:
- **Creator** — the AI prompt shifts to their stylistic vocabulary
- **Judge** — they deliver a characteristic voice critique of the generated work

**14 LACMA curators** (from real staff data) serve as institutional voice agents in the judge rotation — each responding from their departmental perspective.

---

## The Bridging Score

Based on the [Bridging-Based Ranking](https://www.belfercenter.org/publication/bridging-based-ranking) framework. Instead of optimizing engagement within a single community, it measures resonance *across* different groups.

Each generated work is scored 0–100 by matching its content against 8 art-tradition clusters represented by LACMA agents:

| Cluster | Example Agents |
|---------|----------------|
| Social Realism | Rivera, Grosz, Daumier, Naima J. Keith (VP, LACMA) |
| Photography | Adams, Cartier-Bresson, Rebecca Morse (Photography Curator) |
| Expressionism | Kirchner, Beckmann, Timothy Benson (Rifkind Center) |
| Conceptual / Contemporary | Ruscha, Rauschenberg, Eve Schillo (Contemporary Art) |
| Asian Art | Hokusai, Hiroshige, Stephen M. (South & SE Asian Art) |
| Decorative Arts & Design | Hammersley, Bobbye Tigerman (Decorative Arts Curator) |
| Latin American | Rivera, Tamayo, Rachel Kaplan (Latin American Art Curator) |
| American Scene | Adams, Weston, Shannon Vittoria (American Art Curator) |

A work scoring 80+ resonates across at least 6 clusters — the kind of breadth that, at 50,000 display nodes, spans zip codes, languages, and art traditions simultaneously.

---

## Next steps

- [ ] Replace simulated node grid with Leaflet.js map of LA County
- [ ] Add localStorage persistence so the archive accumulates across sessions
- [ ] Scheduled task: auto-generate one civic work per hour, unmanned
- [ ] Replace pre-written judge voices with live Claude API calls
- [ ] Curator review panel as a separate modal
- [ ] WebSocket distribution to simulate real-time node updates

---

## Technical notes

- Single HTML file — all HTML, CSS, and JS in one place
- No build tools, no npm, no dependencies
- `ARTISTS` array: 20 agents with keyword resonance profiles
- `CURATORS` array: 14 LACMA staff as institutional agents
- `CLUSTERS` array: 8 tradition clusters for bridging computation
- `computeBridgingScore()`: keyword matching against combined theme + style + artist corpus
- Image API: `https://image.pollinations.ai/prompt/{encoded_prompt}`

---

## License

MIT — use it, fork it, build on it.
