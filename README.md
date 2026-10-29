# Harbor

**One menu bar app that makes your Mac feel finished.** Harbor turns the notch into a live island, shows window previews when you hover the Dock, types what you say, and adds the clipboard history, window snapping and other little tools macOS leaves out.

It's built natively in Swift and SwiftUI and runs on **macOS 14 Sonoma or later**. The Liquid Glass look and the newest speech engine need macOS 26 or later. Everything runs on your Mac: nothing is uploaded, there are no accounts, and there's no tracking.

**[⬇ Download the latest version](https://github.com/preston-inter/Harbor/releases/latest)**

---

## Contents

- [Notch Island](#-notch-island)
- [Dock Previews](#-dock-previews)
- [Dictation](#-dictation)
- [Quality of Life](#-quality-of-life)
- [Make it yours](#-make-it-yours)
- [Install](#install)
- [Permissions](#permissions)
- [Keyboard shortcuts](#keyboard-shortcuts)
- [Privacy](#privacy)
- [Updates](#updates)
- [Experimental features](#experimental-features)
- [FAQ](#faq)

---

## 🏝 Notch Island

The notch becomes a living part of your Mac. When it's closed, the island is exactly the size of your notch. Rest the pointer on it (or click it, if you prefer) and it opens.

**Now Playing**
- While music plays, album art sits on the left of the notch and moving level bars on the right.
- Open the island for the title, artist, a progress bar, and play, pause and skip.
- Works with Music and Spotify out of the box. An experimental option covers every app, including browsers and Podcasts.

**Pop-ups**
- **Volume:** a bar under the notch when you change the volume or mute. It follows whatever is playing sound, including headphones and AirPods.
- **Brightness:** a pop-up when you press the brightness keys. An experimental option shows the exact level.
- **Battery:** a short pop-up when you plug in or unplug, when charging finishes, and when the battery runs low.
- **Focus:** a pop-up when Do Not Disturb or another Focus turns on or off.
- **Dictation:** a microphone, a level meter and your words appearing live as you speak.
- **Keep Awake:** a coffee cup and the time left while a timed Keep Awake runs.
- **AirPods and Bluetooth:** when headphones, a speaker, keyboard or mouse connects, see its name and battery, with left, right and case levels for AirPods. Low levels show in orange.
- **Downloads:** a progress ring beside the notch while Safari, Chrome, Firefox or Finder saves a file. Real percentages when the browser reports them, the growing size when it doesn't. Click the Done pop-up to show the file in Finder.

**Camera and microphone**
- A green dot beside the notch while the camera is on, an orange one for the microphone.
- Open the island to see which apps are using the microphone. Harbor's own dictation never counts.

**When the island is open**
- **Next calendar event** and how soon it starts. Click it to open Calendar.
- **Quick buttons:** Keep Awake, Dark Mode, a timer, sound output and Lock Screen.
- **Timer:** pick a length; the island lets you know when it's done.
- **Join meetings:** when your next event has a Zoom, Google Meet, Teams, Webex or FaceTime link, a Join button appears next to it, and the island pops up a minute before it starts. Zoom links open straight in the Zoom app.
- **Sound output:** switch between speakers, AirPods, headphones and displays, or pick another microphone, right from the island. Press and hold the volume pop-up to get there fast.
- **Pomodoro:** 25-minute work sessions and short breaks, with a long break every four (all adjustable). The countdown is red while you work and green on breaks, today's count shows in the island, and Settings keeps a 7-day history. It can turn on Do Not Disturb while you work, using two shortcuts the guide helps you make.
- **File shelf:** drag files onto the notch to set them aside, then drag them back out of the island when you need them. Right-click a file (or ⌘-click several) to AirDrop it, compress it to a .zip, resize an image (50%, 1080p, 720p or any width) or convert HEIC, PNG and JPEG. The result is always a new file next to the original, and lands on the shelf too.

**Music while you're away**
- A Now Playing card over the screensaver.
- An experimental option puts it on the lock screen too, just like on an iPhone.

**Look and feel**
- Size slider from 60% to 130%, scaling the open island and its text together.
- Black (blends into the notch) or Liquid Glass style.
- Open on hover or on click, with an adjustable delay and animation speed.

---

## 🪟 Dock Previews

See your windows before you switch to them.

- **Hover a Dock icon** to see a live picture of each of that app's windows, each card shaped like its window. Click one to jump straight to it.
- **Minimized windows** show up too, with the last picture of what they looked like.
- **Window titles** under each preview.
- **⌘⇥ previews:** while Apple's app switcher is open, Harbor shows the selected app's windows above it. Apple's switcher still works exactly as before.
- **Window switcher (⌥⇥):** switch between windows rather than apps, with a picture of each. Add ⇧ to go back, let go to switch, and Esc cancels.
- **Window buttons:** hover a preview, in the Dock or the switcher, to close, minimize or full-screen that window. The preview updates on the spot.
- **Click to minimize (optional):** click the Dock icon of the app you're using to minimize its windows or hide it. Click again to bring it back.
- **Middle-click to quit (optional, for mice with a middle button):** middle-click a Dock icon to quit that app (it still asks about unsaved work). Hold ⌥ to force quit, with a confirmation. Finder and Harbor are never quit this way.
- **Your choice of scope:** see only the windows on your current desktop (the default) or every desktop.
- Three preview sizes and an adjustable hover delay.

Pictures are taken only at the moment a preview opens. Harbor never records continuously, and nothing is saved.

---

## 🎙 Dictation

Type with your voice in any app.

- **Hold Right Option, speak, and let go.** Your words are typed wherever your cursor is. A quick tap does nothing, so the key still works normally.
- **Hands-free mode:** press ⌃⌥Space to start and again to stop, for longer dictation.
- **Live words** appear in the island as you speak, or in a small floating pill if the island is off.
- **Smart clean-up** uses Apple's on-device AI to fix grammar, drop "um"s and false starts, and handle corrections like *"Monday, actually Tuesday"*. If its result ever looks wrong, Harbor uses its basic clean-up instead.
- **Basic clean-up:** capitals, punctuation, and a question mark when you ask a question.
- **Many languages,** some with a one-time download.
- **Safe typing:** Harbor types straight into the text field when it can, otherwise it pastes and puts back what you had copied. If no text field is selected, the text waits on your clipboard instead of landing somewhere unexpected.
- **Your vocabulary:** teach it names, brands and slang, and fixes like "chat gpt" → "ChatGPT". Import and export the list.
- **Adapts to the app:** formal in Mail, casual in Messages and Slack, and exactly what you said in Terminal and code editors. Change any app in Settings.
- **History:** your recent dictations, searchable, with what was heard and what was typed. Copy one, insert it again, or add a word from it. Kept privately (or in memory only), and deleted after 30 days.
- **Transcribe recordings:** drop a voice memo, lecture, meeting or video on the notch (or the Transcribe window). Hours-long files work, with progress and time left. Export as text, Markdown or .srt subtitles, and get an on-device summary on Macs with Apple Intelligence.
- Optional start and stop sounds, and your choice of push-to-talk key.

Speech is transcribed **entirely on your Mac** and never leaves it.

---

## 🧰 Quality of Life

Small tools you'll use every day.

**Clipboard history (⌘⇧V)**
- Remembers text, links, images and files you copy. Open it, type to search, and press Return to paste.
- Pin items you use often (⌘P), delete with ⌘⌫.
- Keep 50 to 500 items. Pinned items are never removed.
- Skips passwords: copies from password managers and anything marked private are never saved.
- Choose to keep history after Harbor quits (stored privately, readable only by your account) or in memory only.

**Window snapping**
- ⌃⌥ with arrow keys: left, right, top and bottom halves.
- ⌃⌥ D / F / G: left, middle and right thirds.
- ⌃⌥ Return to maximize, ⌃⌥ C to center.
- An adjustable gap between windows, and every shortcut can be changed.
- **Drag to snap (optional):** drag a window to a screen edge for half, the top for full screen, or a corner for a quarter, with a preview. Harbor tells you if macOS's own tiling is also on.

**Window layouts**
- Save where all your windows are ("Coding", "Writing"), then put them back with one click from the menu bar or the island, or with a shortcut.
- Apps that aren't open are opened. If a monitor is missing, the layout is fitted onto the screens you have.

**Text snippets**
- Type a trigger like `;email` in any app and it expands into your saved text. Use `{date}`, `{time}`, `{clipboard}` and `{cursor}` inside.
- Never reads or expands in password fields, and skips password managers and any app you exclude. Import and export your list.

**Tidy menu bar (optional)**
- ⌘-drag icons to the left of Harbor's thin divider, then click the arrow to hide or show them. They tuck away again on their own.

**Presenting**
- One switch hides your desktop icons, turns on Do Not Disturb, keeps your Mac awake and quiets Harbor's pop-ups and clipboard history. Switch it off and everything is exactly as before.

**Keep Awake**
- Stop your Mac from sleeping, indefinitely or for a set time.
- Optionally let the screen turn off while downloads and music keep running.
- Switch it on from the menu bar or the island's ☕ button.

**Text grab (⌃⌥O)**
- Drag a box around anything on screen (a picture, a video, a PDF, an app that won't let you select) and its text is copied. Read on your Mac in any language Apple supports.
- QR codes too: Harbor copies what they say and offers to open the link.

**Color picker (⌃⌥P)**
- A magnifier to pick any pixel. The color is copied as HEX, RGB, HSL, SwiftUI or NSColor, your choice.
- Your last 10 colors stay in the island: click to copy again, right-click for another format.

**File shelf**
- Drop files onto the notch and pick them up later. The shelf points to your files instead of copying them.
- Right-click to AirDrop, zip, resize or convert. Originals are never changed.

---

## 🎨 Make it yours

**Settings → Appearance** changes every Harbor panel at once:

- **Surface:** Liquid Glass (macOS 26+), Frosted or Solid.
- **Glass:** Clear, like the macOS Dock, or Frosted, with a strength slider.
- **Accent color:** the system accent, a set of presets, or any custom color, with an option to tint the glass.
- **Corners** and **opacity.**

Harbor also respects **Reduce Motion**, switching springs to gentle fades, and can **open at login**.

Every feature can be switched off on its own, and every setting has an ⓘ button that explains it. A built-in guide walks you through each feature with animated examples, and ends with a cheat sheet.

---

## Shortcuts, backups and your own messages

- **Shortcuts app:** 12 Harbor actions, including Grab Text (returns the text), Pick Color (returns the value), Start or Stop Dictation, Start Timer, Pomodoro, Snap Window, Apply Window Layout, Keep Awake, Presenting, Add File to Shelf, Switch Audio Output and Show Island Message. Many work from Spotlight and Siri too: "Grab text with Harbor".
- **Back Up & Restore:** export every setting, shortcut, snippet, vocabulary word and window layout to one `.harbor` file, and import it on another Mac. You see exactly what will change first, and your current settings are backed up automatically. Histories are never included.
- **Your own island messages:** any script or app can show a message, with a progress bar, in the island. Use a `harbor://` link, the bundled `harbor` command-line tool, or Shortcuts. You can mute or block any sender. See [WIDGETS.md](WIDGETS.md).

## Install

1. Download **Harbor-x.y.z.dmg** from the [latest release](https://github.com/preston-inter/Harbor/releases/latest).
2. Open the DMG and drag **Harbor** into **Applications**.
3. Open Harbor. macOS says it can't check it for malicious software, because Harbor isn't from the App Store. Click **Done**.
4. Go to **System Settings → Privacy & Security** and click **Open Anyway** next to Harbor. You only need to do this once.

Harbor lives in the menu bar (the ⚓ icon). The guide opens the first time to show you around.

## Permissions

Allow only what you want to use. Anything you skip simply turns off the features that need it, and Harbor never crashes because of a missing permission.

| Permission | What it's for |
|---|---|
| Accessibility | Dock previews, the window switcher, dictation typing, snapping, clipboard pasting |
| Screen Recording | Window pictures in previews (without it, you see app icons) |
| Microphone | Dictation |
| Speech Recognition | Dictation on macOS 14–25 |
| Calendar | The next event in the island |
| Bluetooth | Pop-ups for keyboards, mice and controllers (headphones and speakers work without it) |
| Downloads folder | Download progress in the island |
| Automation | Controlling Music and Spotify, and the Dark Mode button |

You can see and fix them in **Settings → Permissions**. Automation is asked for the first time you use it. A "Fix…" link appears in the menu whenever a feature is waiting for one.

## Keyboard shortcuts

| Shortcut | Action |
|---|---|
| Hold Right Option | Dictate (push to talk) |
| ⌃⌥Space | Start or stop dictation |
| ⌥⇥ | Window switcher |
| ⌘⇥ | Apple's app switcher, with Harbor's window previews |
| ⌘⇧V | Clipboard history |
| ⌃⌥ ← → ↑ ↓ | Snap to a half |
| ⌃⌥ D / F / G | Snap to a third |
| ⌃⌥ Return | Maximize |
| ⌃⌥ C | Center |
| ⌃⌥ O | Copy text from the screen |
| ⌃⌥ P | Pick a color |

Every shortcut can be changed in Settings.

## Privacy

- **No network use** except checking GitHub for updates.
- The camera and microphone indicator only checks whether they're in use. Harbor never sees or hears what they capture.
- Dictation and smart clean-up run **on your Mac only**.
- Window pictures are taken on demand and never saved.
- Clipboard history skips passwords and private items, and is stored readable only by your account, or kept in memory only if you prefer.
- No accounts, analytics or tracking.

## Updates

Harbor checks for updates when it opens and every 30 minutes, and asks before installing. You can also choose **Check for Updates…** from the menu bar. Every update is signed, and Harbor installs only updates signed with its own key.

## Experimental features

A few extras rely on parts of macOS that Apple doesn't officially offer to apps. They're **all off by default**, clearly labeled, and could stop working after a macOS update. If one does, Harbor falls back on its own.

- **Now Playing for all apps** (beyond Music and Spotify)
- **Exact brightness level** in the brightness pop-up (read-only)
- **Player on the lock screen.** Anyone at your locked Mac can see what's playing and pause or skip it.

## FAQ

**Does it work on a Mac without a notch?**
Yes. The island sits at the top center of the screen. The Liquid Glass island style looks especially good there.

**Does it replace Apple's volume and brightness pop-ups?**
No, it shows alongside them.

**Does it slow my Mac down?**
Harbor is event-driven and idles at well under 1% CPU. Window pictures are only taken when a preview opens.

**How do I uninstall it?**
Quit Harbor from its menu, then drag it from Applications to the Trash.

---

Made for macOS with Swift and SwiftUI.
