# CCD Agent Web Widget

This repository contains a single static HTML page that embeds a Google CES / Conversation Agent web widget for the CCD camera assistant.

## Files

- `ccd-index.html`
  The main web page with the custom UI and embedded chat widget.
- `saint.otf`
  Optional local font file used for the title styling. If this file is missing, the page will fall back to `Times New Roman`.

## What This HTML Does

`ccd-index.html` is a frontend wrapper for your deployed CCD chatbot.

It includes:

- a custom landing page UI
- a styled embedded chat window
- the widget script and styles from Google
- the deployment reference that connects the page to your chatbot

It does **not** contain the chatbot logic itself.

Your actual chatbot still lives in Google Cloud and depends on:

- your deployed agent
- your current instructions
- your uploaded knowledge files

## How To Use The HTML File

1. Keep `ccd-index.html` in your repository root.
2. If you want the custom title font, place `saint.otf` in the same folder as `ccd-index.html`.
3. Open `ccd-index.html` in a browser for a quick local check.
4. Upload the repository to GitHub.
5. Publish it with GitHub Pages if you want a public URL.

## Before Publishing

Check these items first:

1. Your Google Cloud agent deployment is still active.
2. The `deploymentName` inside `ccd-index.html` points to the correct deployment.
3. Your widget access settings allow your website to use the agent.
4. If you want stricter security, replace `url-allowlist="*"` with your real site domain allowlist.

## GitHub Upload Steps

### Option 1: Upload from the GitHub website

1. Create a new repository on GitHub.
2. Open the new repository page.
3. Click `uploading an existing file`.
4. Drag in:
   - `ccd-index.html`
   - `README.md`
   - `saint.otf` if you have it
5. Add a commit message such as `Add CCD Agent web page`.
6. Click `Commit changes`.

### Option 2: Upload with Git

Run these commands inside your project folder:

```bash
git init
git add ccd-index.html README.md saint.otf
git commit -m "Add CCD Agent web page"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

If you do not have `saint.otf` in the folder, remove it from the `git add` command.

## GitHub Pages Publishing Steps

1. Push the repository to GitHub.
2. Open the repository on GitHub.
3. Go to `Settings`.
4. In the left sidebar, click `Pages`.
5. Under `Build and deployment`, set:
   - `Source`: `Deploy from a branch`
   - `Branch`: `main`
   - `Folder`: `/ (root)`
6. Click `Save`.
7. Wait for GitHub Pages to finish publishing.
8. Open the generated GitHub Pages URL.

## Important Note About File Names

GitHub Pages automatically looks for `index.html` at the root of the published site.

Right now, this project uses:

- `ccd-index.html`

If you want GitHub Pages to open the site directly from the root URL, you should either:

1. rename `ccd-index.html` to `index.html`, or
2. keep it as `ccd-index.html` and open:

```text
https://YOUR_USERNAME.github.io/YOUR_REPO/ccd-index.html
```

## Recommended Setup

For the simplest GitHub Pages setup:

1. Rename `ccd-index.html` to `index.html`
2. Keep `README.md`
3. Keep `saint.otf` in the same folder if you want the custom title font
4. Publish from the `main` branch root

## Troubleshooting

### The page loads but the chatbot does not appear

Check:

- the deployment is still active
- the deployment name is correct
- the widget is allowed to load on your site
- browser console errors

### The title font does not change

Check:

- `saint.otf` exists in the same folder as `ccd-index.html`
- the filename matches exactly

### The page opens but the root GitHub Pages URL shows 404

That usually means GitHub Pages cannot find `index.html`.

Fix it by:

- renaming `ccd-index.html` to `index.html`, or
- opening the explicit file URL with `/ccd-index.html`

## Customization

You can edit `ccd-index.html` to change:

- title text
- colors
- borders and metallic styling
- layout
- entry cards
- widget title

## License

No license has been added yet.
