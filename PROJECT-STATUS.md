# McNeal Research Site — Project Status

Last updated: 2026-08-18

## What this is
Static HTML site replacing the old WordPress site at `wp.towson.edu/pmcneal/`.
This folder (`Documents/Claude Cowork/Outputs/McNeal Research Site`) is the source of truth — edit here first.

## Current state: LIVE
- Deployed to GitHub Pages. Local git is now set up on Peggy's Mac (see "How to update the site" — as of 2026-08-18, `git push` from Terminal is the preferred update path; the GitHub-web-UI method still works as a fallback).
- Repo: `mcneal-research`, public.
- GitHub username: `pmcneal-towson`
- Live URL: https://pmcneal-towson.github.io/mcneal-research/
- Repo page (to edit/upload files): https://github.com/pmcneal-towson/mcneal-research
- Verified live 2026-06-09: home, team, and cognition-wild pages load; images render; both repointed links serve `poster-cognition-2.pdf` correctly.

## How to update the site (current: git push, set up 2026-08-18)
The Cowork session edits files via the device bridge, writes them into this folder, then commits and pushes with git. Peggy's Mac now has Xcode Command Line Tools (includes git) installed, and a GitHub personal access token is saved in her Mac's credential store from the 2026-08-18 push — `git push` should not prompt again unless the token expires or is revoked.

**For a future Claude session doing this:**
1. Stage the changed file(s) from this device folder into the Cowork session, edit them there, `SendUserFile`, then `device_commit_files` back to their paths in this folder (standard device-bridge round trip — this folder itself isn't directly writable from the session).
2. Use `mcp__remote-devices__device_bash` to run, inside this folder: `git add <files>`, `git commit -m "..."`, `git push`.
   - `device_bash` runs in a separate sandboxed VM, not Peggy's actual Mac shell — it does NOT have the git credential Peggy set up in Terminal. Expect the push to fail or hang on auth from `device_bash`.
   - So: commit locally via `device_bash` (that part works fine — no auth needed), but leave the actual `git push` to Peggy in her own Terminal. Tell her to open Terminal and run (no `cd` needed if she's already in the folder from a prior session):
     ```
     cd "/Users/pmcneal/Documents/Claude Cowork/Outputs/McNeal Research Site"
     git push
     ```
   - Give her a minute or two after a successful push before checking the live URLs — GitHub Pages needs to rebuild.
3. If Terminal prompts for a username/password again, the saved token likely expired (it was set with a 90-day expiration on 2026-08-18, so ~mid-November 2026) or was revoked. Walk her through creating a new one:
   1. https://github.com/settings/tokens → **Generate new token** → **Generate new token (classic)**
   2. Any note, e.g. "mcneal-research push"; expiration 90 days; check the **repo** scope checkbox; **Generate token**
   3. Copy the token (shown once, starts `ghp_...`)
   4. At Terminal's username prompt: `pmcneal-towson`; at the password prompt: paste the token (nothing will appear on screen — that's normal) and hit Enter.
4. If `git` itself is missing again (fresh machine, or she never installed it before this): running any `git` command in Terminal triggers a macOS popup offering to install "Command Line Developer Tools." She clicks Install, waits ~5–15 min, then retries.

**Fallback: GitHub web UI (no Terminal, no git needed)**
1. Edit existing page: open the file in the repo → pencil icon → edit → Commit changes.
2. Add/replace a file: Add file → Upload files → drag in → Commit. Same filename + same folder = overwrite. Open a subfolder (e.g. `images/`) before uploading into it.
3. Delete: open file → trash icon → Commit.

Either path: make edits in this Cowork folder first (so links/structure get checked) before pushing/uploading.

## Pages
- `index.html`, `research.html`, `team.html`, `publications.html`
- Project pages: `aser.html`, `aser-workshop-2023.html`, `cognition-wild.html`, `density-tanks.html`, `draw-earth-scientist.html`, `hydrogeology.html`, `meteorology.html`
- Assets: `images/` (48 files), `docs/` (3 outcomes-report PDFs), `posters/` (poster files), `style.css`

## Changes made during deployment (2026-06-09)
- Repointed the two remaining old-WordPress backlinks to a local file:
  - `team.html` "See Patrick's poster" → `posters/poster-cognition-2.pdf`
  - `cognition-wild.html` "Learn More" item → `posters/poster-cognition-2.pdf`
  - (Both pointed to the same student work: the "flashbulb memory" / emotions-and-memory poster, Schneider lead author.)
- Added `.gitignore` (excludes `.DS_Store`, `.fuse_hidden*`).
- Added `.nojekyll` (belt-and-suspenders; not strictly needed — no Jekyll-sensitive files).
- Verified: all 75 files' internal links and 48 image references resolve; no broken paths; no external WordPress URLs remain.

## Changes after launch
- 2026-06-09: `publications.html` — converted the top 4 full citations to the clean title-link format so all 11 entries are uniform (title as a clickable link to the DOI/source). Author/year/journal detail no longer displayed, per preference. Uploaded and verified live 2026-06-09.
- 2026-08-18: Added Frankie Bolen (Research Assistant, Temple University) to `cognition-wild.html` Project Members, next to Courtney Sheckler; added her headshot (`images/Frankie-Bolen-headshot.png` — only 140×140px, worth swapping for a higher-res version if one becomes available). Added the published "Mental Fluid Transformation" paper (`https://doi.org/10.3390/educsci16081280`) to the top of `publications.html`. Committed locally via `device_bash`, then Peggy pushed live from her own Terminal (see "How to update the site" above for the git-push setup this required).

## Open follow-ups (optional)
- The `cognition-wild.html` "Learn More" link now points to a poster already shown in the Project Posters section above it — slightly redundant. Could remove that list item.
- `_new-material/` is empty and unused.

## Reference
- `DEPLOY-GUIDE.md` — original step-by-step setup instructions (account, repo, upload, enable Pages).
