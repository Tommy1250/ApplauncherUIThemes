# Contributing a theme

Thanks for making a theme! Here's everything you need — folder conventions, the variable reference, how to test it, and how to submit it.

## 1. Set up your folder

Create a new folder at the root of the repo, named after your theme in lowercase-with-hyphens:

```
my-theme-name/
├── my-theme-name.css
├── preview.png # Add it when you're done (just screen shot the app with a few games)
└── readme.md
```

- The `.css` file name should match the folder name.
- Make sure to include a `preview.png` to the folder, it should be 1280x720 atleast or any 16:9 resolution
- `readme.md` needs to be exactly like that:

  ```
  Author: Your Name

  Description: One short sentence about the theme.

  ![theme preview](preview.png)
  ```

## 2. Write the theme

A theme is just a `:root` block that overrides whichever CSS variables you want to change. **You don't need to override every variable** — anything you leave out falls back to the launcher's default, so a small, focused theme (e.g. just recoloring the background and accent) is completely valid.

```css
:root {
    --body-bg-color: #0d0d12;
    --body-text-color: #f1f1f1;
    --appDiv-hover-bg: #ff4d6e46;
    /* ...only what you're actually changing */
}
```

Keep the file to variable overrides only — don't redeclare element selectors (`.app-div`, `.search-box`, etc.) unless you're doing a "hyper custom" theme, since that can break layout for everyone who installs it.

## 3. Variable reference

### Global
| Variable | Used for |
|---|---|
| `--body-bg-color` | Page background |
| `--body-text-color` | Default text color |
| `--hr-color` | Divider lines |

### Search bar
| Variable | Used for |
|---|---|
| `--search-input-text` / `--search-input-bg` | Search box text/background |
| `--search-button-bg` / `--search-button-border` / `--search-button-text` | "Clear" button |
| `--search-button-hover-text` / `--search-button-focus-active` | Search button hover/focus states |

### Icon buttons (add, filter, settings, etc.)
| Variable | Used for |
|---|---|
| `--iconbtn-color` | Icon color |
| `--iconbtn-hover` / `--iconbtn-active` | Hover/active states |

### App grid & posters
| Variable | Used for |
|---|---|
| `--appDiv-hover-bg` | Background when hovering an app tile |
| `--appDiv-bottom-button-color` / `--appDiv-bottom-button-hover-bg` | The "…" menu button under each poster |
| `--app-category-overlay-bg` / `--app-category-overlay-text` | Category tag chip shown on a poster |
| `--controller-focus-color` | Focus ring when navigating the grid with a controller |
| `--app-checkbox-border-color` / `--app-checkbox-checked-bg` | Multi-select checkbox on a poster — sits directly on top of app art, so only touch this for a deliberately unusual theme |

### Tooltip
| Variable | Used for |
|---|---|
| `--tooltip-bg` / `--tooltip-text` / `--tooltip-border` | Hover tooltips |

### Settings page inputs
| Variable | Used for |
|---|---|
| `--settings-input-bg` / `--settings-input-text` | Text/password fields |
| `--settings-input-disabled-bg` / `--settings-input-disabled-text` | Disabled fields |
| `--utilaction-button-bg` / `--utilaction-button-text` / `--utilaction-button-hover-text` | Small icon buttons next to inputs (e.g. show/hide password) |

### Buttons & controls
| Variable | Used for |
|---|---|
| `--controls-button-bg` / `--controls-button-text` | Default button state |
| `--controls-button-hover-bg` / `--controls-button-hover-text` | Hover state |
| `--controls-button-active-bg` / `--controls-button-active-text` | Active/pressed state |

### Toggle switches
| Variable | Used for |
|---|---|
| `--switch-slider-bg` / `--switch-slider-before-bg` | Off state track/knob |
| `--switch-checked-bg` | On state track |

### "Change position" modal
| Variable | Used for |
|---|---|
| `--movemodal-bg` / `--movemodal-boder` / `--movemodal-text` / `--movemodal-backdrop` | Modal box and backdrop |
| `--movemodal-movebutton-bg` / `--movemodal-movebutton-text` / `--movemodal-movebutton-hover-bg` | The "Move" button |
| `--movemodal-head-button-text` / `--movemodal-head-button-hover-text` | Close (×) button |

### Categories / info dialogs
| Variable | Used for |
|---|---|
| `--categories-dialog-bg` / `--categories-dialog-box-shadow` / `--categories-dialog-backdrop` | Dialog box and backdrop |
| `--title-bar-h3-color` | Dialog title text |
| `--custom-checkbox-label` / `--custom-checkbox-checkmark-bg` / `--custom-checkbox-checkmark-border` | Category checkboxes |
| `--custom-ckeckbox-checked-checkmark-bg` / `--custom-ckeckbox-checked-checkmark-border` / `--custom-ckeckbox-ckeckmark-after-border` | Checked state |

### Context menu (right-click + submenus)
| Variable | Used for |
|---|---|
| `--context-menu-bg` / `--context-menu-border` / `--context-menu-box-shadow` | Menu background/border/shadow — also used by submenus |
| `--context-menu-li-hover-bg` | Hovered menu item |
| `--context-menu-checkbox-label-text` / `--context-menu-checkbox-check-border` | Checkbox items inside the menu (e.g. category toggles) |

### Controller bar & focus
| Variable | Used for |
|---|---|
| `--controller-info-bg` / `--controller-info-text` | Connected-controller info panel |
| `--controller-focus-color` | Focus ring on the currently selected grid item / menu row |
| `--controller-bar-bg` / `--controller-bar-border` / `--controller-bar-text` / `--controller-bar-shadow` | The bottom button-prompt bar shown during controller navigation |

### Scrollbar
| Variable | Used for |
|---|---|
| `--scrollbar-track` | Track |
| `--scrollbar-thumb` / `--scrollbar-thumb-hover` | Thumb / thumb hover |

### Misc
| Variable | Used for |
|---|---|
| `--active-item-color` / `--active-item-hover-color` / `--active-item-active-color` | Used on one specific highlighted button |
| `--image-clear-search-disabled` / `--image-search-disabled-text` | Disabled image-search bar colors |

## 4. Test it

Use the same install steps from the README: open the launcher's Settings, click **Open Themes Folder**, drop your `.css` file in, then select it from the theme dropdown. It applies immediately, so you can iterate — edit, save, and press `Ctrl+R` refresh.

Check a few different screens while testing, not just the main grid:

- The app grid with a mix of posters, including one focused via keyboard/controller
- The search bar, both empty and with text typed in
- Settings page (inputs, toggles, buttons)
- Right-click context menu and a submenu (e.g. Manage categories)
- A dialog (Filter categories and the move-position popup)
- The edit and add menus
- The image search menu
- The microsoft store add window

## 5. Submit it

1. Fork the repo and add your theme folder.
2. Open a pull request with one theme per PR.
3. Include a screenshot or two of the launcher with your theme applied in the PR description — it makes review much faster and doubles as a preview for the gallery.
