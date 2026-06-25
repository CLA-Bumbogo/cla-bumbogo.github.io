# Christian Life Assembly — Bumbogo Branch

The official static landing hub for the **CLA Bumbogo** congregation. This site is a
lightweight information hub for members and visitors: a place to watch/listen to past
Sunday sermons, browse weekly photo galleries, and read the latest church
announcements — all while staying visually and institutionally consistent with the
CLA Central Headquarters site at [clarwanda.org](https://clarwanda.org).

> **Live site:** hosted free on **GitHub Pages**.

---

## 1. Zero-Cost Architecture

This project is intentionally designed to run at **near-zero operational cost** and to
be maintainable by non-technical church/media volunteers. There is **no server, no
database, and no paid hosting**.

| Concern            | How we solve it (for free)                                              |
| ------------------ | ----------------------------------------------------------------------- |
| **Website hosting**| **GitHub Pages** — free static hosting straight from this repository.   |
| **Sermons (video)**| **Embedded from YouTube** via `<iframe>`. We never store video files.   |
| **Sermons (audio)**| **Embedded from Spotify** (podcast/episode) via `<iframe>`.             |
| **Photo galleries**| **Shared Google Drive / Google Photos album links.** We link out, not host. |
| **Announcements**  | Plain text edited directly in `index.html` (no CMS needed).             |

### The golden rule: **No binary media in this repo**
We **never** commit videos, large image files, or audio into this repository. Heavy
files make the site slow and the repo bloated. Instead we **embed or link** to media
that already lives on free external platforms (YouTube, Spotify, Google Drive/Photos).
The repo should only ever contain code, small logos/icons, and text.

---

## 2. Layout Rule — Consistency with HQ

The Bumbogo site **mirrors the layout and structure** of the CLA Central HQ site
([clarwanda.org](https://clarwanda.org)):

- A **fixed top header** with the logo on the left and horizontal navigation on the right.
- A **large, clean hero** statement directly below the header.
- The same calm, faith-centered tone.

The **branding** (colours, logo) is the **Bumbogo branch identity** taken from our
official flyer: deep **olive / forest greens**, warm **ochre / orange**, and soft cream
neutrals. The footer always **links back to HQ** (clarwanda.org) so the branch remains
clearly part of the wider CLA family.

---

## 3. Project Files

| File         | Purpose                                                                 |
| ------------ | ----------------------------------------------------------------------- |
| `index.html` | The entire homepage. **Edit text, links, and embeds here.**             |
| `style.css`  | All styling. Colours live at the top in `:root` variables.              |
| `README.md`  | This file — project documentation.                                      |
| `context.md` | Project rules for the Cursor AI assistant (and human contributors).     |

### For the media team — how to update content (no coding required)
Open `index.html` and look for the bright `<!-- EDIT: ... -->` comments. They tell you
exactly which line to change for:
- **Adding a sermon** → paste a YouTube or Spotify embed link.
- **Updating the gallery** → paste a new Google Photos / Drive album link.
- **Posting an announcement** → copy an existing announcement block and change the words.

You only ever change the text **between** the tags, never the tags themselves.

---

## 4. Git Collaboration Rules (`main` vs `dev`)

We use a simple, safe two-branch workflow so the live site never breaks.

| Branch | Role                                                                       |
| ------ | -------------------------------------------------------------------------- |
| `main` | **Production.** This is what GitHub Pages publishes to the public. Always stable. |
| `dev`  | **Workspace.** All new work, edits, and experiments happen here first.      |

### Workflow
1. **Never commit directly to `main`.** All changes start on `dev`.
2. Pull the latest `dev` before you start: `git pull origin dev`
3. Make and commit your changes on `dev`:
   ```bash
   git checkout dev
   git add .
   git commit -m "Add: this Sunday's sermon embed"
   git push origin dev
   ```
4. When `dev` is reviewed and looks correct, open a **Pull Request** from `dev` → `main`.
5. Merging into `main` automatically **publishes** the changes to the live site.

> Rule of thumb: **`dev` is where we build, `main` is what the world sees.**

---

## 5. Local Preview

No build tools required. Just open the file, or run a tiny local server:

```bash
# Option A: double-click index.html in your file explorer

# Option B: lightweight local server (Python 3)
python3 -m http.server 8000
# then visit http://localhost:8000
```

---

_Built with care for the CLA Bumbogo family. © Christian Life Assembly._
