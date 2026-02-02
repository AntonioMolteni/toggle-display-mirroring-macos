# Toggle Display Mirroring macOS

A simple AppleScript for toggling display mirroring programmatically on macOS using the Command + F1 keyboard shortcut (Command + decrease display brightness).

## Overview

This script simulates pressing Command + F1 (brightness down key), which is macOS's built-in keyboard shortcut for toggling display mirroring when multiple displays are connected.

## Requirements

- macOS (any version that supports display mirroring)
- Multiple displays connected to your Mac
- Accessibility permissions for the application running the script

## Usage

### Method 1: Using Script Editor

1. Open the `toggle-display-mirroring.scpt` file with Script Editor (located in `/Applications/Utilities/`)
2. Click the "Run" button (▶️) in Script Editor to execute the script
3. Your display mirroring will toggle on/off

### Method 2: Running from Terminal

You can execute the script directly from the command line:

```bash
osascript toggle-display-mirroring.scpt
```

### Method 3: Creating a Quick Action / Service

1. Open **Automator** (in `/Applications/`)
2. Create a new **Quick Action** (or Service in older macOS versions)
3. Add a "Run AppleScript" action
4. Copy the script content into the action
5. Save with a name like "Toggle Display Mirroring"
6. You can now trigger it from the Services menu or assign a custom keyboard shortcut in System Preferences > Keyboard > Shortcuts > Services

### Method 4: Assigning a Keyboard Shortcut

Using a third-party app like **BetterTouchTool**, **Keyboard Maestro**, or **Alfred**:

1. Create a new trigger with your preferred keyboard shortcut
2. Set the action to execute the AppleScript file
3. Now you can toggle mirroring with your custom shortcut

## The Script

```applescript
#Toggle Display Mirroring
tell application "System Events"
	key code 145 using {command down} -- brightness down key + Command
end tell
```

The script uses key code 145, which corresponds to the F1/brightness down key on Mac keyboards, combined with the Command modifier.

## Permissions

When running the script for the first time, macOS may prompt you to grant accessibility permissions:

1. Go to **System Preferences** (or **System Settings** on macOS 13+)
2. Navigate to **Security & Privacy** > **Privacy** > **Accessibility**
3. Add and enable the application running the script (e.g., Script Editor, Terminal, or your automation app)

## Troubleshooting

**Script doesn't work:**
- Ensure you have multiple displays connected
- Verify that the standard Command + F1 shortcut works manually
- Check that accessibility permissions are granted
- On some Mac models, you may need to hold the Fn key (Fn + Command + F1)

**Nothing happens when running:**
- Make sure "System Events" has the necessary permissions
- Try running the script from Script Editor first to see if there are any error messages

## License

MIT License - Feel free to use and modify as needed.
