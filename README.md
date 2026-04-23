# CCD Agent Web Widget

This repository is structured for GitHub Pages to open directly from the site root.

## Publish Structure

- `index.html`
  Main landing page and embedded Google CES / Conversation Agent widget.
- `assets/`
  Static files used by the page:
  - `Black.png`
  - `camera-icon.png`
  - `saint.otf`

GitHub Pages looks for `index.html` at the repository root, so this layout works with:

- Branch: `main`
- Folder: `/ (root)`

## What The Site Does

`index.html` is a frontend wrapper for your deployed CCD chatbot.

It includes:

- a custom landing page UI
- a styled embedded chat window
- Google widget scripts and styles
- the deployment reference that connects the page to your chatbot

It does not contain the chatbot logic itself.

The actual chatbot still lives in Google Cloud and depends on:

- your deployed agent
- your instructions
- your uploaded knowledge files

## Local Preview

Open `index.html` in a browser for a quick check.

## GitHub Pages Setup

1. Push the repository to GitHub.
2. Open `Settings > Pages`.
3. Under `Build and deployment`, choose:
   - `Source`: `Deploy from a branch`
   - `Branch`: `main`
   - `Folder`: `/ (root)`
4. Save and wait for the deployment to finish.

Your site should then open directly from:

```text
https://YOUR_USERNAME.github.io/YOUR_REPO/
```

## Before Publishing

Check these items first:

1. Your Google Cloud agent deployment is still active.
2. The `deploymentName` inside `index.html` points to the correct deployment.
3. Your widget access settings allow your website to use the agent.
4. If you want stricter security, replace `url-allowlist="*"` with your real domain allowlist.

## Troubleshooting

### The page loads but the chatbot does not appear

Check:

- the deployment is still active
- the deployment name is correct
- the widget is allowed to load on your site
- browser console errors

### The title font does not change

Check:

- `assets/saint.otf` exists
- the filename matches exactly

### The background or icon does not load

Check:

- `assets/Black.png` exists
- `assets/camera-icon.png` exists
- the paths inside `index.html` still point to `./assets/...`

## Customization

You can edit `index.html` to change:

- title text
- colors
- borders and metallic styling
- layout
- entry cards
- widget title

## License

No license has been added yet.
