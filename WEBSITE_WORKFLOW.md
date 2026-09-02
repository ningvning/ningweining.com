# Website Maintenance Workflow

This website follows a simple cycle:

> Open the project → sync the latest version → preview locally → make changes → test → save with Git → upload to GitHub

## 1. Start work

Open this folder in VS Code:

```text
/Users/ningweining/Library/CloudStorage/Dropbox/website/ningweining.com
```

Open **Terminal → New Terminal**, then check the current state:

```bash
git status
```

Ideally, you will see `nothing to commit, working tree clean`.

Before editing, download the latest version from GitHub:

```bash
git pull
```

If `git status` shows unfinished changes, review them before pulling.

## 2. Start the local preview

Run:

```bash
npm run dev
```

This starts a private development version of the website on your Mac. Open the address shown in Terminal, normally:

```text
http://localhost:4321
```

Edit files in VS Code and save with **⌘S**. The browser usually refreshes automatically.

`npm run dev` does **not** publish anything. To stop it, return to Terminal and press **Control+C**.

## 3. Check the changes

In the local preview, check:

- desktop and narrow/mobile layouts
- images and links
- spelling and visible formatting

Then test the production build:

```bash
npm run build
```

Fix any errors before publishing.

## 4. Save and publish

Review which files changed:

```bash
git status
```

Add the changes to the next version:

```bash
git add .
```

Create a saved version with a short description:

```bash
git commit -m "Update homepage layout"
```

Upload it to GitHub:

```bash
git push
```

Once GitHub Pages is configured, pushing to GitHub triggers the website update automatically. Allow a few minutes, then check the live site.

## Quick checklist

```bash
git status
git pull
npm run dev
# Make and preview changes, then press Control+C
npm run build
git status
git add .
git commit -m "Describe the update"
git push
```

## Git command cheat sheet

| Command | What it does |
|---|---|
| `git status` | Shows the current branch and changed files |
| `git pull` | Downloads the latest version from GitHub |
| `git add .` | Selects all current changes for the next commit |
| `git commit -m "Message"` | Saves a named version locally |
| `git push` | Uploads saved commits to GitHub |
| `git log --oneline -5` | Shows the five most recent commits |
| `git diff` | Shows changes that have not been added yet |

