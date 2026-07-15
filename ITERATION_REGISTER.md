# ITERATION REGISTER — THE AMERICAN SCENE 2.0

Public record of iterations, pivots, and productive failures, following the
iteration-tracking schema from the project dossier (meta map, §04):
`iteration_id · parent · status [BUILD|TEST|FAIL|SHIP] · failure_mode · lessons · artifacts · timestamp`.

Negative results are valid research output. Abandoned approaches are recorded
here with the same care as shipped ones. All entries below are factual and
derived from the git history and session records of this repository.

---

## IT-001 — Initial proof of concept (v1)
- **parent:** none
- **status:** SHIP
- **failure_mode:** null
- **timestamp:** 2026-06-15
- **artifacts:** `c0b7cf6`
- **lessons:** Single-file HTML app is viable for the POC: AI generation
  (Pollinations), artist/judge voices, and a live bridging score in one page,
  no build step.

## IT-002 — Generation reliability pass
- **parent:** IT-001
- **status:** SHIP (after FAIL observed in the field)
- **failure_mode:** Pollinations API intermittently returns HTML from its rate
  limiter, which the browser blocks as ERR_BLOCKED_BY_ORB; images silently fail.
- **timestamp:** 2026-06-24
- **artifacts:** `bfa3930`
- **lessons:** A remote free API is a real dependency: retry logic and a
  placeholder fallback are mandatory, not polish. Carried forward as a v3 risk
  (kiosk mode needs cached fallback images).

## IT-003 — Image Library workflow
- **parent:** IT-002
- **status:** SHIP
- **failure_mode:** null
- **timestamp:** 2026-07-01 → 2026-07-02
- **artifacts:** `8e1dccc`, `4bc503d`
- **lessons:** A manifest-driven `src/` folder lets curated works persist
  without a backend; "Save to Library" generates the manifest entry so the
  human only moves a file.

## IT-004 — Named artists → numbered agent registry
- **parent:** IT-003
- **status:** SHIP
- **failure_mode:** Prior design attributed generated styles to named artists.
- **timestamp:** 2026-07-10
- **artifacts:** `b0fe4f0`
- **lessons:** No named individuals as style proxies. 21 numbered agents in
  three documented tiers (WPA divisions / LACMA collection traditions /
  contemporary movements) keep the historical grounding without impersonation.

## IT-005 — Street View API path (ABANDONED) → Street Flag Compositor
- **parent:** IT-004
- **status:** FAIL → SHIP (replacement)
- **failure_mode:** Google Street View API key path was confusing in practice
  and added a paid dependency; abandoned same day (productive failure).
- **timestamp:** 2026-07-10
- **artifacts:** `b0fe4f0` (Street View tab), `43b4ffb` (pivot to flag
  compositor), `c526e12` (photo upload replaces API key)
- **lessons:** (1) A user-uploaded photo that never leaves the browser beats a
  keyed API for both privacy and comprehension. (2) Wikimedia images must use
  direct `upload.wikimedia.org` URLs — the `Special:FilePath` redirect strips
  CORS headers and breaks canvas compositing. (3) Physical display metaphors
  (drape, pole, bunting) communicate better than map coordinates.

## IT-006 — Countywide demonstration network
- **parent:** IT-005
- **status:** SHIP
- **failure_mode:** Central-LA-only node list did not test the distribution
  claim; score could look "bridging" while geographically narrow.
- **timestamp:** 2026-07-11
- **artifacts:** `305afe0`
- **lessons:** 8 nodes across 8 county regions, framed as demonstration
  research contexts — not partnerships. "Matched Nodes" became "Provisional
  Routing." Geographic polarization added as an explicit failure test.

## IT-007 — Transparency & honesty pass
- **parent:** IT-006
- **status:** SHIP
- **failure_mode:** Several UI claims outran reality: named living curators as
  voices, "on-device render," broadcast language implying autonomous public
  deployment, a "bridging score" presented as measurement, Detect state
  reading as surveillance.
- **timestamp:** 2026-07-13
- **artifacts:** `ca88684`, `fbe5fc7`, `156fd21`, `039fc68`, `14cb271`,
  `79d4738`, `70070fe`, `fcfed29`, `dfe9d72`
- **lessons:** (1) Replace named living curators with anonymized department
  agents — no words in real people's mouths without opt-in. (2) Say
  "submission and review," not "broadcast." (3) The score is a provisional
  semantic score; label it so everywhere. (4) Believable claims need the most
  care. This pass defines the factual-transparency bar for v3: nothing about
  LACMA, people, or measurements appears unless real or stamped
  SIMULATED FOR PROTOTYPE.

## IT-008 — v2 freeze & archive
- **parent:** IT-007
- **status:** SHIP (frozen)
- **failure_mode:** null
- **timestamp:** 2026-07-15
- **artifacts:** `c7c1f00` — `archive/` (both HTML versions with SHA-256
  hashes in `archive/MANIFEST.txt`, 16 full-page screenshots, version label
  `v2-freeze-2026-07-15`)
- **lessons:** The experimental meta map (dossier / kiosk / easel-mural
  divisions / provenance protocol) is preserved as a research map and
  component library — explicitly not a codebase. Its mock records (IRB
  numbers, consent claims, consensus scores) are design fiction and must never
  migrate into a public interface unstamped.

## IT-009 — v3 rebuild: A Working Model of a Public Cultural Economy (PLANNED)
- **parent:** IT-008
- **status:** BUILD (not started)
- **failure_mode:** n/a
- **timestamp:** planned from 2026-07-15
- **artifacts:** rebuild plan (session record, 2026-07-15); new folder
  `american-scene-3/` — separate from the live v2 file, which stays deployed
  untouched
- **lessons (design commitments):** Plain museum language; opening status
  board of estimate / actual / difference / interpretation with every figure
  stamped SIMULATED FOR PROTOTYPE; ten-step visitor journey from "the museum
  this week" to "distribution and public record"; generation demoted to
  step 6, downstream of a documented need; this register graduates into the
  v3 Public Work Register.
