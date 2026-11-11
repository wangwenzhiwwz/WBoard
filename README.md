# WBoard

A lightweight, local-first infinite whiteboard. No backend, build step, API key, or dependency required.

## Features
- Infinite canvas with pan and zoom
- Sticky notes, text, rectangles, ellipses, arrows, and freehand drawing
- Select and move objects
- Undo / redo
- Browser local autosave
- JSON import/export and PNG export
- Responsive layout and keyboard shortcuts

## Deploy to GitHub Pages
1. Create a public GitHub repository named `WBoard`.
2. Upload the contents of this project to the repository root (including `.github/workflows/deploy.yml`).
3. Open **Settings → Pages** and set **Build and deployment → Source** to **GitHub Actions**.
4. The workflow deploys the site automatically after each push to `main`.
5. Your URL will be `https://wangwenzhiwwz.github.io/WBoard/`.

## Run locally
Open `index.html` in a modern browser.

## Keyboard shortcuts
`V` select · `H` hand/pan · `N` note · `T` text · `R` rectangle · `O` ellipse · `A` arrow · `P` pen · `Delete` remove · `Ctrl/Cmd+Z` undo · `Ctrl/Cmd+Y` redo

Data is stored in the current browser's localStorage. Export JSON regularly for backup. This first release is single-user and does not sync across devices.

## Workspace features

- Project space with multiple projects and descriptions
- Task kanban: Todo, In progress, Review, Done
- Task owner and due date fields
- Per-project mind maps with draggable nodes, editable labels, parent-child connections
- Local browser persistence
- GitHub sync to `data/workspace.json` through the GitHub Contents API

### Enable GitHub sync

1. Open the deployed WBoard site and choose **GitHub 设置** (or **GitHub 同步**).
2. Create a GitHub token with **Contents: Read and write** permission for `wangwenzhiwwz/WBoard`.
3. Paste the token into WBoard. It is kept in `sessionStorage` for the current browser session only.
4. Use **GitHub 同步** to save the project/task/mind-map data to `data/workspace.json`. When the same browser session reconnects, WBoard loads that file from GitHub.

Do not share your token. Anyone who obtains it may be able to modify the repository within the token's granted permissions. Local browser storage remains available without a token.
