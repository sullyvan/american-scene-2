# Iteration Log: Learning Through Failure
**American Scene 2.0 — LACMA Art + Technology Lab 2026**

Master copy of the iteration register. Iterations 01–04 are as recorded in the
submission document (`Clients/Art Submissions/LACMA/American Scene 2 Iteration
Log.pdf`, 2 pp.); 05–08 continue the log from the working record of this
repository. Format follows the original: what we tried / what broke / what it
taught us. Failing forward is the deliverable, not the caveat.

---

## Iteration 01 — Named Artist Agents (abandoned)
**What we tried:** Early builds scored generated imagery against named LACMA
collection artists directly, using their names as style anchors for the
bridging clusters.

**What broke:** Estate rights review made clear this approach was a dead end
before any public deployment — the app couldn't legally reference living or
recently-deceased artists by name.

**What it taught us:** The constraint became the concept. Replacing named
artists with anonymous attribute-bundle agents (styleDesc, keywords, clusters,
judgments) wasn't a workaround — it mirrored the WPA's own uncredited-worker
model. The failure sharpened the thesis rather than diluting it.
*(Repo artifact: `b0fe4f0`, 2026-07-10.)*

## Iteration 02 — Full 50,000-Node Network Demo (scoped down)
**What we tried:** An early demo attempted to preview the entire civic
broadcast network across all eight preset LA neighborhoods simultaneously.

**What broke:** The full-network version obscured the mechanism it was trying
to show — reviewers couldn't tell what was actually being scored or why.

**What it taught us:** One neighborhood, one Street View composite, one visible
bridging-score run says more than eight at once. We're now building toward a
single legible "return moment" rather than a system-wide simulation.

## Iteration 03 — Pollinations.ai as Permanent Pipeline (flagged, not fixed)
**What we tried:** Using Pollinations.ai for all image generation through the
proposal and demo phase.

**What broke:** Nothing yet — but we identified it as proof-of-concept only,
unsuitable for anything deployed under LACMA's name.

**What it taught us:** Naming a known limitation honestly, before a reviewer
finds it, is itself part of the "half-baked proposal" ethos the Lab has
historically rewarded. The transition path (toward a vetted pipeline, e.g.
Anthropic API, an existing Lab partner) is part of the submission, not a
footnote.
*(Repo artifacts: `bfa3930` retry/fallback hardening, 2026-06-24; ORB failure
mode documented for kiosk-mode planning.)*

## Iteration 04 — Flat Agent List (restructured into three tiers)
**What we tried:** Initial agent architecture treated all style references as
a single undifferentiated list — WPA program figures, LACMA institutional
collection traditions, and contemporary movements all at the same level.

**What broke:** Without hierarchy, the system couldn't distinguish why an
agent existed — historical mandate vs. institutional collection vs.
contemporary practice read as interchangeable inputs, which flattened the
app's argument about lineage.

**What it taught us:** Numbering agents by tier (#001–099 WPA program
documentation, #100–299 LACMA collection traditions, #300+ contemporary
movements) turned a data-modeling problem into the app's clearest piece of
storytelling. The array structure stayed identical, so nothing load-bearing
had to change — the fix was entirely in classification, not consumption.
*(Repo artifact: `039fc68`, 2026-07-13.)*

## Iteration 05 — Street View API as Site Tool (abandoned same day)
**What we tried:** A Google Street View API integration so generated works
could be previewed on real streetscapes via a keyed map service.

**What broke:** The keyed-API path was confusing in practice, added a paid
dependency, and raised deployment questions the prototype couldn't answer. It
was removed the day it landed.

**What it taught us:** A user-uploaded photo that never leaves the browser
beats a keyed API for both privacy and comprehension. Physical display
metaphors — facade drape, outrigger pole, balcony flags, cross-street
bunting — communicate "public display" better than map coordinates. A side
lesson with teeth: Wikimedia images must use direct `upload.wikimedia.org`
URLs, because the `Special:FilePath` redirect strips CORS headers and breaks
canvas compositing.
*(Repo artifacts: `b0fe4f0` → `43b4ffb` → `c526e12`, all 2026-07-10.)*

## Iteration 06 — Central-LA Node List (rebuilt countywide)
**What we tried:** Demonstration nodes concentrated in central Los Angeles.

**What broke:** A central-only list couldn't test the project's distribution
claim — a work could score as "bridging" across art traditions while remaining
geographically narrow. The score was blind to spatial inequality.

**What it taught us:** Eight nodes across eight county regions (Boyle Heights,
Watts, Wilmington, Pacoima, Pomona, Lancaster, Altadena + LACMA/Wilshire
host), framed as demonstration research contexts rather than partnerships.
"Matched Nodes" became "Provisional Routing," and geographic polarization was
added as an explicit failure test rather than an embarrassment to hide.
*(Repo artifact: `305afe0`, 2026-07-11.)*

## Iteration 07 — Claims That Outran Reality (transparency pass)
**What we tried:** Interface language accumulated during fast iteration:
named living curators as institutional voices, an "on-device render" claim,
"broadcast" language implying autonomous public deployment, a bridging score
presented as measurement, a Detect state that read as surveillance.

**What broke:** Each claim was individually small and collectively corrosive —
the believable ones were the most dangerous, because reviewers and visitors
would have no reason to doubt them.

**What it taught us:** A standing factual-transparency bar: nothing about
LACMA, real people, or measurements appears in the interface unless it is real
or explicitly labeled simulated. Living curators became anonymized department
agents (no words in real mouths without opt-in); "broadcast" became
"submission and review"; the score is labeled a provisional semantic score
everywhere it appears.
*(Repo artifacts: nine commits, 2026-07-13: `ca88684` → `dfe9d72`.)*

## Iteration 08 — v2 Freeze & the Meta Map (archived, not merged)
**What we tried:** A parallel experimental HTML (WPA dossier, gallery kiosk,
easel/mural divisions, provenance protocol, office-delivery choreography)
built as a design sandbox alongside the live prototype.

**What broke:** As code, the sandbox was a palimpsest — duplicated handlers,
self-injecting tabs, mock records styled as real documents (IRB numbers,
consent claims, consensus scores). Merging it would have imported exactly the
credibility problems Iteration 07 removed.

**What it taught us:** Treat it as a research map and component library, not a
codebase. Both versions are now frozen and hashed (`archive/`, label
`v2-freeze-2026-07-15`, 16 full-page screenshots, SHA-256 manifest) before any
rebuild. The next build — "A Working Model of a Public Cultural Economy" —
starts in a separate folder (`american-scene-3/`), keeps the engines (bridging
computation, agent routing, street compositor), adopts the sandbox's
institutional imagination (status board, divisions, provenance records,
public work register), and stamps every simulated figure SIMULATED FOR
PROTOTYPE. The live v2 URL stays untouched as the demo of record.
*(Repo artifacts: `c7c1f00`, `5860ff5`, 2026-07-15.)*

---

**Closing note for reviewers** *(from the submitted log, still accurate):*
each iteration maps to the Lab's 2026 criteria — estate rights became an
artistic-merit and tech-engagement question (01), the scoped demo a
public-engagement question (02), pipeline honesty a shareable-output question
(03), tier restructuring all four at once (04). Iterations 05–08 continue the
pattern: privacy and comprehension (05), spatial equity (06), factual
transparency (07), and disciplined preservation before reinvention (08).
