# AppLauncherUI Themes

A collection of drop-in CSS themes for [AppLauncherUI](https://github.com/Tommy1250/AppLauncherUI) — a desktop app/game launcher. Each theme is a single self-contained `.css` file that overrides the launcher's color variables/style, so installing one is as simple as copy-pasting a file removing one is just deleting a file.

## Installing a theme

1. Pick a theme in this repo and download its `.css` file.
2. Open AppLauncherUI, go to **Settings** (gear icon in the top right), and click **Open Themes Folder**.
3. Drop the downloaded `.css` file into that folder.
4. Back in Settings, pick the theme from the **Select Theme** dropdown — it applies immediately, no restart needed.
5. Press **Save changes** From the bottom of the settigs page

To go back to a default look, just select **Dark** or **Light** again. To remove a custom theme entirely, delete its `.css` file from the themes folder.

## Repo structure

Each theme lives in its own folder:

```
theme-name/
├── theme-name.css   # the theme itself — a set of CSS variable overrides
├── preview.png      # A preview of the theme that's usually 1280x720
└── readme.md        # metadata shown to users
```

`readme.md` follows a simple format:

```
Author: Your Name
Description: A short description of the theme.
![theme preview](preview.png)
```

## Browsing themes

See the [gallery site](https://tommy1250.github.io/applauncher/themes/) for a visual preview of every theme in this repo before downloading.

## Contributing a theme

Want to add your own? See [CONTRIBUTING.md](CONTRIBUTING.md) for the folder conventions, the full list of themeable variables, and how to submit it.
