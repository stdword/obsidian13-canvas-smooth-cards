# Smooth text cards for canvases
[Obsidian](https://github.com/obsidianmd) CSS snippet for smooth text cards in canvases. It visually synchronizes cards reading and editing views.

<img width="600px" src="https://github.com/user-attachments/assets/ea524e8e-c849-43d2-a9bc-8d8726353095"/>

## The Solution:
<img width="600px" src="https://github.com/user-attachments/assets/f707ab36-57a9-4e59-a09f-b3a1775234b9"/>

### No view jumpings for long texts:
<img width="900px" src="https://github.com/user-attachments/assets/f87371a1-ea75-4ce1-b5ee-45b9a280c173"/>


# Usage
Just add this code to appropriate place:
```
<span class=vertical-space>&nbsp;</span>
```

<img width="600px" src="https://github.com/user-attachments/assets/2a7d4ac5-6cb4-4c66-b184-b329f92d8659"/>

<br/>
<br/>
<img width="1000px" src="https://github.com/user-attachments/assets/1103fe54-7432-45f4-bad1-39f31525adc5"/>

<br/>
<br/>
<img width="350px" src="https://github.com/user-attachments/assets/fca0caa6-3b64-499e-8cda-26e40c39e095"/>

See examples in `assets/test.canvas` file (you need to copy it to your obsidian's vault first).


# Snippets

- Main snippet: `canvas-smooth-cards.css`
- Additional snippet for callout support: `canvas-smooth-cards_addition.css`. It is currently in draft status as of 2026-03
   - Note: it changes the appearance of callout blocks even outside of canvases. If you don't like this behaviour — turn it off.


# Installation (auto)

> Note: this is recommended way, but you need to install two additional plugins

1. Install [BRAT plugin](https://github.com/TfTHacker/obsidian42-brat) by TfTHacker **from Marketplace**
2. In Obsidian: Via BRAT plugin's settings install [Snippet Downloader plugin](https://github.com/Mara-Li/obsidian-snippet-downloader)
   + It is no longer supported and removed from Marketplace, but still works (mart 2026)
   + But with one visual bug:
  
     <img width="600px" src="https://github.com/user-attachments/assets/54d2e102-241f-40ed-be56-3a79f3a6d2d2"/>
3. In Obsidian: Add this repository to the Snippet Downloader in it's settings
4. In Obsidian: Go to Settings → Appearance → CSS Snippets
5. In Obsidian: Press "Reload snippets" button (with arrows icon)
6. In Obsidian: Turn on the appropriate snippets in the list


# Installation (manual)

> Note: for every repository update you need to manually re-install snippets

1. Download all `.css` files from `src` folder of this repo
2. Open Obsidian app
3. In Obsidian: Go to Settings → Appearance → CSS Snippets
3. In Obsidian: Press "Open snippets folder" button (with folder icon)
4. Move downloaded files to that folder
5. In Obsidian: Press "Reload snippets" button (with arrows icon)
6. In Obsidian: Turn on the appropriate snippets in the list


# Configure
You can create [automatic text trigger](https://espanso.org/docs/matches/basics/#static-matches) (e.g. `:vs`) via [`espanso`](https://github.com/espanso/espanso) app. Use this config:
```yaml
matches:
  - label: "Vertical space for Obsidian's canvas"
    trigger: ":vs"
    replace: "\n\n<span class=\"vertical-space\">&nbsp;</span>"
```

You can create [keyboard shortcut trigger](https://espanso.org/docs/matches/basics/#keyboard-triggers) (only CTRL+… supported) via [`espanso`](https://github.com/espanso/espanso) app. Use this config:
```yaml
matches:
  - label: "Vertical space for Obsidian's canvas"
    trigger: "\x13"  # ctrl-s
    replace: "\n\n<span class=\"vertical-space\">&nbsp;</span>"
    force_mode: keys
```


# Configure for MacOS
You can create `⌥⏎` (option + enter) keyboard shortcut via [Karabiner Elements](https://karabiner-elements.pqrs.org) app. It's much more common to make vertical spaces using the Enter key.

## For single english-only keyboard layout:
1. In Karabiner Elements: Open Settings → Complex Modifications → Add your own rule
2. Add contents of `config/karabiner-elements/single-layout.json` file to model window and press the save button.
3. That's all. **Note**: new keyboard shortcut is working only in Obsidian app.

## For multiple keyboard layouts:
1. Install the util to change current keyboard layout to english: [`xkbswitch-macosx`](https://github.com/myshov/xkbswitch-macosx)
2. Open terminal and switch keyboard layout to English
3. Run this command to find keyboard layout id: `xkbswitch -g`. Remember the number
4. In Karabiner Elements: Open Settings → Complex Modifications → Add your own rule
5. Add contents of `config/karabiner-elements/multiple-layouts.json` file to model window
6. Find this text:  `/usr/local/bin/xkbswitch -s 1` and change number `1` to your keyboard id
7. Press the save button
8. That's all. **Note**: new keyboard shortcut is working only in Obsidian app.


# Changelog
 * v1 (2025-10-17) - vertical space for h1, h2, h2, p, table, ol, ul and sync ol, ul
 * v2 (2026-03-10) - fixed layout for headers and tables; added draft support for callouts
