# SmallVideoCraft (alpha — plan first, flagship exists)

**Status:** `[ALPHA]` with an initial plan. The flagship product already runs:
[ittybittyvideos](https://github.com/sandraschi/ittybittyvideos) (script in,
shorts and explainers out — installer, web dashboard, MCP). SmallVideoCraft
is the studio roof over it: short video, not film. No implementation beyond
the plan in this repo yet; what runs today runs under the ittybitty brand,
which keeps its name, installer, and issues.

## Why "small"

Video is too broad a word — it stretches from a 15-second repo propaganda
clip to a Hollywood blockbuster. This craft owns the small end only: shorts,
explainers, demo clips, propaganda cuts, timelapses. Timelines, NLE editing
and VFX belong to Storytold's
[filmcraft](https://github.com/storytold/filmcraft) / effectcraft, which we
do not duplicate. Small is the moat and the boundary in one word.

## Scope (initial plan)

- **Script → short** — topic or script in, narrated vertical/square/landscape
  video out (flagship: ittybittyvideos, unchanged).
- **Footage gathering** — stock, Jellyfin/Plex home videos, local AI clips,
  stills (input path only; photo management stays with Photoprism/Immich).
- **Live-to-clip** — cut shorts from live production (`streamfog-mcp`: OBS AR
  lenses, Vtuber avatars). Streaming itself stays live; this craft cuts the
  replay.
- **First customers** — the democraft gallery (every craft needs a demo clip)
  and gamecraft web clips.

## Sources it consolidates

| Source | Role |
|---|---|
| `ittybittyvideos` (`videogen-mcp`) | flagship product — keeps brand, installer, issues |
| `streamfog-mcp` | live AR/stream input, Vtuber avatars |
| `rust-photoprism-mcp` (tentative) | stills input path |
| democraft gallery, gamecraft web | built-in demand: every craft ships a clip |

## Non-goals (explicit)

- **Not an NLE.** No multi-track timelines, no color suites, no VFX
  compositing — that is filmcraft/effectcraft territory, and theirs.
- **Not a rebrand.** ittybittyvideos keeps its name and traction; this repo
  is the studio umbrella, not a rename.
- **No cloud lock-in.** Local-first: renders fully local with no cloud tokens
  when the GPU is up to it; falls back to user-token cloud minutes when not.

## Harness (when built beyond the flagship)

Implements the Storytold craft-app harness like the rest of the fleet: one
binary that is both the human CLI and the agent MCP server (stdio),
headless-first, `run.json` + report artifacts.

## Lineage — the Storytold craft-app pattern

Storytold ArtCraft ([storytold/artcraft](https://github.com/storytold/artcraft) — "the IDE for artists") was the starting point. The 16 craft apps in the Storytold stable each ship one binary that is both the human CLI and the agent MCP server (stdio), headless-first, with `run.json` + report artifacts. That modus operandi and harness is what this repo implements; the code here is independent, the pattern is shared.
