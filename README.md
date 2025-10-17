# Smooth text cards for canvases
@obsidianms CSS snippet for smooth text cards in canvases. It visually synchronizes cards reading and editing views.


# Installation
1. Download all `.css` files from `src` folder of this repo
2. Open Obsidian app and go to Settings → Appearance → CSS Snippets
3. In Obsidian: Press "Open snippets folder" button (with folder icon)
4. Move downloaded files to that folder
5. In Obsidian: Press "Reload snippets" button (with arrows icon)
6. In Obsidian: Turn on the appropriate snippet in the list


# Usage
To add synchronized vertical space between elements:
 - add plain new line (via enter)
 - then add this code `<span class=vertical-space>&nbsp;</span>`

<img width="400px" src="https://github.com/user-attachments/assets/3a934215-5f97-4ca7-b85c-8e5904820267"/>

See examples in `assets/test.canvas` file (you need to copy it to your obsidian's vault first).


# Configure
You can setup [`espanso`](https://github.com/espanso/espanso) app to create:
 - [automatic text trigger](https://espanso.org/docs/matches/basics/#static-matches) (e.g. `:vs`) to insert vertical space's code:
   ```yaml
   matches:
      - label: "Vertical space for Obsidian's canvas"
        trigger: ":vs"
        replace: "\n\n<span class=\"vertical-space\">&nbsp;</span>"
   ```
 - [keyboard shortcut trigger](https://espanso.org/docs/matches/basics/#keyboard-triggers) (only CTRL+… supported) to insert vertical space's code:
   ```yaml
   matches:
      - label: "Vertical space for Obsidian's canvas"
        trigger: "\x13"  # ctrl-s
        replace: "\n\n<span class=\"vertical-space\">&nbsp;</span>"
        force_mode: keys
   ```

# Configure for MacOS
You can setup [Karabiner Elements](https://karabiner-elements.pqrs.org) app to create <kbd>⌥⏎</kbd> (option + enter) keyboard shortcut.

## For single english-only keyboard layout:
1. In Karabiner Elements: Open Settings → Complex Modifications → Add your own rule
2. Add contents of `config/karabiner-elements/single-layout.json` file to model window and press the save button.
3. That's all. Note: new keyboard shortcut is working only in Obsidian app.

## For multiple keyboard layouts:
1. Install the util to change current keyboard layout to english: [`xkbswitch-macosx`](https://github.com/myshov/xkbswitch-macosx)
2. Open terminal and switch keyboard layout to English
3. Run this command to find keyboard layout id: `xkbswitch -g`. Remember the number
4. In Karabiner Elements: Open Settings → Complex Modifications → Add your own rule
5. Add contents of `config/karabiner-elements/multiple-layouts.json` file to model window
6. Find this text:  `/usr/local/bin/xkbswitch -s 1` and change number `1` to your keyboard id
7. Press the save button
8. That's all. Note: new keyboard shortcut is working only in Obsidian app.


# Changelog:
 * v1 (2025-10-17) - vertical space for h1, h2, h2, p, table, ol, ul and sync ol, ul
