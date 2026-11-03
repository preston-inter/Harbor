# Privacy in Harbor for Mac

**Harbor works on your Mac. It has no accounts, no analytics and no tracking, and it uploads nothing you type, say, copy or see.**

This page lists everything Harbor connects to, what each permission is for, and what it keeps on your Mac. The tables are generated from Harbor's own code and checked with every release, so they can't quietly go out of date.

## Every connection Harbor makes

<!-- harbor:network:start -->
| What | Server | When | What's sent |
|---|---|---|---|
| Update checks | github.com (Harbor's releases) | When Harbor opens and every 30 minutes while automatic updates are on, and when you click Check for Updates… | A plain request for the update list. Nothing about you or your Mac (Sparkle's system profiling is off). |
| Spotify album art | Spotify's image server | While Spotify plays, to show the cover in the island | A request for the cover picture Spotify itself names for the song playing. |
<!-- harbor:network:end -->

That's all. Some things you start yourself go through Apple or another app, not Harbor:

- **Speech models**: on newer Macs, dictation can ask macOS to download Apple's on-device speech model when you click Download in Settings. Speech is then recognized on your Mac.
- **Shortcuts**: Focus and Do Not Disturb run your own Shortcuts through Apple's `shortcuts` tool.
- **Links you click**, such as Join for a meeting or a link read from a QR code, open in your browser or the meeting app.

## Permissions

Allow only what you want to use. Anything you skip turns off the features that need it.

<!-- harbor:permissions:start -->
| Permission | What it's for | Used by |
|---|---|---|
| Accessibility | Lets Harbor notice when you hover the Dock, move and switch windows, use its keyboard shortcuts, and type dictated text. | Replace macOS's volume and brightness pop-ups, Dock previews, Window buttons on previews, Previews in ⌘⇥, Window switcher, Dock clicks, Hold to talk, Start and stop dictation, Typing your words, Clipboard history, Paste as plain text, Quit protection, Window snapping, Green button maximizes, Quit on last window, Window layouts, Text snippets |
| Screen Recording | Lets Harbor show pictures of your windows in previews and the switcher, and read or capture what you select on screen. A picture is taken only when you ask and is never uploaded; only captures you take are kept. | Copy text from the screen, Capture to shelf, Dock previews (optional) |
| Microphone | Lets Harbor hear you while you hold the dictation key, and only then. | Hold to talk, Start and stop dictation |
| Speech Recognition | Turns what you say into text, on this Mac. | Hold to talk, Start and stop dictation, Transcribe recordings |
| Calendar | Shows your next event in the island. Harbor only reads your calendar and never changes it. | Next calendar event (optional), Join meetings (optional) |
| Bluetooth | Lets the island show a pop-up when a keyboard, mouse or other Bluetooth device connects, and lets Harbor disconnect your headphones while your Mac sleeps. Headphones and speakers pop up without it. | AirPods and Bluetooth (optional), Bluetooth while asleep (optional) |
| Camera | Shows your camera in the island so you can check how you look before a call. The camera is on only while that panel is open, and nothing is recorded. | Camera check (optional) |
| Downloads folder | Lets the island see files arriving in your Downloads folder, to show their progress. macOS asks the first time. | Download progress |
| Automation | Lets Harbor control Music and Spotify and switch Dark Mode. macOS asks the first time you use each. | Now Playing, Timer and controls |
<!-- harbor:permissions:end -->

### The sensitive parts, plainly

- **Keys**: hold-to-talk dictation and text snippets watch the keyboard through Accessibility. Hold-to-talk only looks for its own key. Snippets keep the last 64 characters in memory to spot a trigger, and reset on a click or app switch. Nothing typed is saved or logged.
- **Screen**: a picture of the screen is taken only when you ask: a Dock preview opening, text grab, or a capture. Previews and text grab are never saved. Captures are kept in `~/Library/Application Support/Harbor/Captures` until you're done with them (a week off the shelf, then the Trash).
- **Microphone**: on only while you hold the dictation key or have dictation running. Audio is never saved.
- **App volume**: macOS calls this "System Audio Recording". Harbor turns the app's sound straight back into sound at the volume you chose. It's never saved or sent.
- **Camera**: on only while the camera check panel is open. Nothing is recorded.
- **Clipboard history** skips password managers, concealed and temporary items, and is readable only by your account (or kept in memory only, if you prefer).
<!-- harbor:privacy-notes:start -->
- **Replace macOS's volume and brightness pop-ups**: It watches the keyboard's media keys through Accessibility, and only the volume, mute and brightness keys: they're applied by Harbor instead of macOS. No other key is looked at, and nothing is saved or logged.
- **Agent status**: Set Up changes other apps' settings files, only when you click it: for Claude Code it adds three hooks to `~/.claude/settings.json`, for Codex it sets `notify` in `~/.codex/config.toml` (only if Codex has none). Before the first change Harbor copies the file next to it as `<file>.harbor-backup`. The added lines only run Harbor's `harbor` tool to show a message; nothing is read from the agents. To undo it, click Remove (Settings → General → Agent status), or Remove Harbor Completely, which takes the lines out; or restore the backup copy.
<!-- harbor:privacy-notes:end -->
- **The lid helper** (Keep Awake "While working" with the lid closed) runs as root after you approve it in Login Items. It can only run `/usr/bin/pmset` with fixed arguments to turn lid sleep off and back on, and it only accepts requests from Harbor signed by the same developer. It turns lid sleep back on by itself if Harbor quits, the battery runs low or the Mac gets hot.

## Experimental features

These use parts of macOS that Apple doesn't officially offer to apps. They're all off by default.

<!-- harbor:experimental:start -->
- **Now Playing for every app**: Music and Spotify use Apple-approved methods. All apps also covers browsers, Podcasts and more, but relies on an unofficial part of macOS that could stop working after an update. If it does, Harbor goes back to Music and Spotify.
- **Replace macOS's volume and brightness pop-ups**: Experimental: Harbor takes the volume, mute and brightness keys and makes the change itself, so only the island's pop-up appears instead of two at once. Same steps as macOS (⌥⇧ for quarter steps). Any key Harbor can't apply, such as a speaker whose volume can't be set or an external display's brightness, goes to macOS as usual, and if Harbor stops responding the keys go back to macOS within a second. Brightness uses an unofficial part of macOS.
- **Exact brightness level**: macOS has no approved way for apps to read the brightness level, so this uses an unofficial part of macOS. It only reads the level and never changes it. Without it, the pop-up shows which way brightness changed.
- **Player on the lock screen**: Shows the Now Playing card on the lock screen, like on an iPhone. It uses an unofficial part of macOS, and anyone at your locked Mac can see what's playing and pause or skip it.
<!-- harbor:experimental:end -->

## What Harbor keeps, and where

- **Settings**: `~/Library/Preferences/dev.harbor.Harbor.plist`.
- **Clipboard history, dictation history, the shelf and captures**: `~/Library/Application Support/Harbor`. Clipboard and dictation history are readable only by your account.
- **Settings backups** (made before each update changes settings, and when you import a backup): `~/Library/Application Support/Harbor/Backups`.

To remove everything, use **Settings → General → Remove Harbor Completely…**. It turns off Open at Login and the lid helper, resets Harbor's permissions, and moves all of the above and Harbor itself to the Trash.

## Check it yourself

- **Network**: a firewall like [LuLu](https://objective-see.org/products/lulu.html) (free) shows every connection Harbor makes. It should match the table above.
- **Activity**: Activity Monitor shows Harbor's CPU and energy use. It idles well under 1% CPU.
- **Signature**: `codesign -dv /Applications/Harbor.app` shows who signed it.
- **Download**: each release's notes list the DMG's SHA-256. Compare it with `shasum -a 256 ~/Downloads/Harbor-x.y.z.dmg`.

## Questions

Open an issue at [github.com/preston-inter/Harbor/issues](https://github.com/preston-inter/Harbor/issues).
