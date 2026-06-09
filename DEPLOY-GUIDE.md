# Deploy to GitHub Pages

Goal: get the site live at `https://<your-username>.github.io/mcneal-research/`

Everything in this folder is ready to upload. Follow these steps in your browser.

## 1. Create a GitHub account
1. Go to https://github.com/signup
2. Enter your email (your Towson address is fine), a password, and a username. Your username becomes part of the site URL, so pick something clean (e.g. `pmcneal` or `pmcneal-towson`).
3. Verify your email when GitHub prompts you.

## 2. Create the repository
1. Go to https://github.com/new
2. Repository name: `mcneal-research`
3. Set it to **Public** (required for free GitHub Pages).
4. Leave "Add a README" unchecked.
5. Click **Create repository**.

## 3. Upload the site files
1. On the new repo page, click the **"uploading an existing file"** link (or **Add file → Upload files**).
2. Open this folder on your Mac: `Documents/Claude Cowork/Outputs/McNeal Research Site`
3. Select the **contents** of the folder — not the folder itself. (Open the folder, press Cmd+A to select everything inside, then drag it onto the GitHub upload area.)
   - This must include the `images`, `docs`, and `posters` subfolders. GitHub keeps the folder structure.
   - Do NOT drag the parent "McNeal Research Site" folder in — that would nest everything one level too deep and break the site.
4. Wait for all files to finish uploading (you'll see the file count climb — there are ~75 files).
5. Scroll down and click **Commit changes**.

## 4. Enable GitHub Pages
1. In the repo, click **Settings** (top tab).
2. Left sidebar → **Pages**.
3. Under "Build and deployment", Source: **Deploy from a branch**.
4. Branch: **main**, folder: **/ (root)**. Click **Save**.
5. Wait 1–2 minutes. Refresh the page; a banner will show your live URL:
   `https://<your-username>.github.io/mcneal-research/`

## 5. Check it
Open the URL. Click through the pages, confirm images and the PDF/poster links load.

---

## Notes
- **Old WordPress links:** fixed. Both backlinks (`team.html`, `cognition-wild.html`) now point to `posters/poster-cognition-2.pdf`. No `wp.towson.edu` links remain. (Note: the "Learn More" link on `cognition-wild.html` now points to a poster already shown in the Project Posters section above it — slightly redundant. Say the word if you'd rather remove that list item.)
- **`.nojekyll` (optional):** the folder includes a `.nojekyll` file, but macOS hides dotfiles so it likely won't upload via drag-and-drop. The site doesn't need it (no Jekyll-sensitive files), so skip it. If you ever add a folder or file starting with `_`, create a `.nojekyll` file in the repo (Add file → Create new file → name it `.nojekyll` → Commit).
- **Custom domain / shorter URL:** the URL above is the free default. A custom domain (or moving to a `<username>.github.io` root repo) is possible later if you want.
