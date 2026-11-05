# SmallVideoCraft PRD (draft 0 — pre-implementation)

**Status:** draft, 2026-11-05. The flagship (`ittybittyvideos`) runs; this
PRD scopes the umbrella, not the flagship.

## 1. Model

A short project: `{ script, scenes[], narration, aspect, footage[], captions,
render }`. Scenes reference footage (stock, home-video, AI clip, stills);
narration carries voice + timing; aspect is vertical/square/landscape;
render is the recipe. Same document-pattern as the other crafts.

## 2. Verbs (planned)

- `script new --topic "..."` — outline + narration draft
- `footage gather --source stock|plex|ai|stills` — B-roll collection
- `narrate --voice ...` — voiceover render (local model or user-token cloud)
- `render --aspect 9:16` — offline render + artifact
- `caption --style ...` — burned-in captions
- `publish --target shorts|reels` — export package with metadata
- `mcp` — stdio server over the same dispatch bus

## 3. Phases

- **0 (done 2026-11-05):** name reserved, plan published, flagship named.
- **1:** scope freeze + flagship alignment — ittybitty's verbs mapped onto §2
  (adopt, don't rewrite; gaps become the build list).
- **2:** `footage gather` + `publish` as the first native verbs (the two the
  flagship lacks as headless CLI).
- **3:** first democraft recipe (`shorts/script-to-short` on fixtures).
