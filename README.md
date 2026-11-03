# Harbor for Mac

**One menu bar app that makes your Mac feel finished.** Harbor turns the notch into a live island, shows window previews when you hover the Dock, types what you say, and adds the clipboard history, window snapping and other little tools macOS leaves out.

It's built natively in Swift and SwiftUI and runs on **macOS 14 Sonoma or later**. The Liquid Glass look and the newest speech engine need macOS 26 or later. Everything runs on your Mac: nothing is uploaded, there are no accounts, and there's no tracking.

**Free during early access.** Harbor Pro is coming, and early users will get a big discount.

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
- [Updates and getting started](#updates-and-getting-started)
- [Experimental features](#experimental-features)
- [FAQ](#faq)

---

## 🏝 Notch Island

The notch becomes a living part of your Mac. When it's closed, the island is exactly the size of your notch. Rest the pointer on it (or click it, if you prefer) and it opens.

<!-- harbor:area-notchIsland:start -->
- **The island**: Rest the pointer on the notch, or click it if you prefer, and the island opens; closed, it's exactly the size of your notch. Make it 60% to 130% the size, black to blend into the notch or Liquid Glass, with your own delay and animation speed. Macs without a notch get a floating island at the top center.

**Now Playing**
- **Now Playing**: While music plays, album art sits on the left of the notch and moving level bars on the right. Open the island for the title, artist, a progress bar, and play, pause and skip. Works with Music and Spotify out of the box.
- **Now Playing for every app** *(experimental, off by default)*: Music and Spotify use Apple-approved methods. All apps also covers browsers, Podcasts and more, but relies on an unofficial part of macOS that could stop working after an update. If it does, Harbor goes back to Music and Spotify.

**Pop-ups**
- **Volume, brightness, battery and Focus pop-ups**: A volume bar when you change the volume or mute (it follows headphones and AirPods), a pop-up for the brightness keys, battery pop-ups when you plug in, finish charging or run low, and a note when a Focus turns on or off. They show alongside Apple's own, and each kind can be turned off.
- **Replace macOS's volume and brightness pop-ups** *(experimental, off by default)*: Experimental, off by default: Harbor takes the volume, mute and brightness keys and makes the change itself, so only the island's pop-up appears instead of two at once. Same steps as macOS (⌥⇧ for quarter steps). Any key Harbor can't apply, such as a speaker whose volume can't be set or an external display's brightness, goes to macOS as usual, and if Harbor stops responding the keys go back to macOS within a second. Brightness uses an unofficial part of macOS.
- **Exact brightness level** *(experimental, off by default)*: macOS has no approved way for apps to read the brightness level, so this uses an unofficial part of macOS. It only reads the level and never changes it. Without it, the pop-up shows which way brightness changed.
- **AirPods and Bluetooth**: When AirPods, headphones, a speaker, keyboard or mouse connects, see its name and battery, with left, right and case levels for AirPods. Low levels show in orange. Headphones and speakers need no permission; keyboards, mice and controllers need Bluetooth permission.
- **Download progress**: A progress ring beside the notch while Safari, Chrome, Firefox or Finder saves a file: real percentages when the browser reports them, the growing size when it doesn't. Click the Done pop-up to show the file in Finder.
- **Camera and microphone in use**: A green dot beside the notch while the camera is on, an orange one for the microphone. Open the island to see which apps are using the microphone. Harbor's own dictation never counts.

**When the island is open**
- **Quick buttons and timers**: Round buttons in the open island: Keep Awake, Dark Mode, Lock Screen, sound output, and a timer with 5, 15, 25 and 60 minute presets that tells you when it's done.
- **Sound output picker**: Switch between speakers, AirPods, headphones and displays, or pick another microphone, right from the island. Press and hold the volume pop-up to get there fast.
- **Next calendar event**: Your next event and how soon it starts, in the open island. Click it to open Calendar. Harbor only reads your calendar and never changes it.
- **App volume** *(macOS 14.2+)*: Set each app's volume on its own, in the island's sound panel or Mixer… in the menu bar: turn Spotify down under a call, mute a noisy tab, or lift a quiet video above its normal level. Harbor remembers each app's level. Louder than normal goes up to 1.5× on headphones and 1.3× on the MacBook speakers, with a limiter so sound never crackles or goes past the speakers' safe level. Apps you haven't changed are left completely alone. Needs System Audio Recording permission and macOS 14.2.
- **Camera check**: Check your camera before a call: a mirrored preview opens in the island from the camera button next to a meeting or in the sound panel, and you can switch between your Mac's camera, an iPhone or a USB camera. The camera is on only while the preview is open, and nothing is recorded.
- **Join meetings**: When your next event has a Zoom, Google Meet, Teams, Webex or FaceTime link, a Join button appears next to it, and the island pops up a minute before it starts. Zoom links open straight in the Zoom app.
- **Pomodoro**: 25-minute work sessions and short breaks, with a long break every four (all adjustable). The countdown is red while you work and green on breaks, today's count shows in the island, Settings keeps a 7-day history, and it can turn on Do Not Disturb while you work.
- **File shelf**: Drag files onto the notch to set them aside, then drag them back out when you need them; the shelf points to your files instead of copying them. Right-click (or ⌘-click several) to AirDrop, zip, resize an image (50%, 1080p, 720p or any width) or convert HEIC, PNG and JPEG. The result is always a new file next to the original.

**Music while you're away**
- **Player over the screensaver**: A Now Playing card over the screensaver, so you can pause or skip before your Mac locks.
- **Player on the lock screen** *(experimental, off by default)*: Shows the Now Playing card on the lock screen, like on an iPhone. It uses an unofficial part of macOS, and anyone at your locked Mac can see what's playing and pause or skip it.
<!-- harbor:area-notchIsland:end -->

---

## 🪟 Dock Previews

See your windows before you switch to them.

<!-- harbor:area-dock:start -->
- **Dock previews**: Rest the pointer on a Dock icon to see a live picture of each of its windows, each card shaped like its window, and click one to jump straight to it. Minimized windows show their last picture, titles sit under each preview, and you can include windows on other desktops. Without Screen Recording permission you see app icons instead.
- **Window buttons on previews**: Hover a preview, in the Dock or the window switcher, to close, minimize or full-screen that window. The preview updates on the spot.
- **Previews in ⌘⇥**: While Apple's app switcher (⌘⇥) is open, Harbor shows the selected app's windows above it. Click one to jump to it; Apple's switcher still works exactly as before.
- **Window switcher**: Switch between windows rather than apps, with a picture of each. Hold the modifier, tap Tab to move, add ⇧ to go back and let go to switch; Esc cancels. Windows on this desktop come first, then other desktops, then minimized ones.
- **Dock clicks**: Optional: click the Dock icon of the app you're using to minimize its windows, hide it, or step through its windows one by one. With a mouse that has a middle button, middle-click an icon to quit the app (it still asks about unsaved work), or hold ⌥ to force quit after a confirmation. Finder and Harbor are never quit this way.
<!-- harbor:area-dock:end -->

Pictures are taken only at the moment a preview opens. Harbor never records continuously, and nothing is saved.

---

## 🎙 Dictation

Type with your voice in any app.

<!-- harbor:area-dictation:start -->
- **Hold to talk**: Hold the key, speak and let go: your words are typed wherever your cursor is, and appear live in the island as you speak (or in a small pill if the island is off). A quick tap does nothing, so the key still works normally. Many languages, some with a one-time download, all transcribed on your Mac.
- **Start and stop dictation**: For longer dictation, press the shortcut to start and again to stop, so you don't have to hold a key.
- **Punctuation and clean-up**: Capitals, punctuation and a question mark when you ask a question, with “um”s and “uh”s left out. Used whenever smart clean-up is off or unavailable.
- **Smart clean-up** *(macOS 26+)*: Apple's on-device AI fixes grammar, drops false starts and handles corrections like “Monday, actually Tuesday”. If its result ever looks wrong, Harbor uses basic clean-up instead. Nothing leaves your Mac.
- **Typing your words**: Harbor types straight into the text field when it can, and otherwise pastes and puts back what you had copied. If no text field is selected, the text waits on your clipboard instead of landing somewhere unexpected. Optional start and stop sounds.
- **Custom vocabulary**: Teach it names, brands and slang so the recognizer and smart clean-up spell them right, and add fixes like “chat gpt” → “ChatGPT” for words it keeps getting wrong. Import and export the list.
- **Style per app**: Formal in Mail, casual in Messages and Slack, and exactly what you said in Terminal and code editors. The app in front when you start picks the style, and you can change any app in Settings.
- **Dictation history**: Your recent dictations, searchable, with what was heard and what was typed. Copy one, insert it again, or add a word from it to your vocabulary. Off until you turn it on; then kept privately (or in memory only), 50 entries for 30 days by default.
- **Transcribe recordings**: Drop a voice memo, lecture, meeting or video on the notch (or open the Transcribe window) and get text with timestamps, made on your Mac. Hours-long files work, with progress and time left. Export as text, Markdown or .srt subtitles, and get an on-device summary on Macs with Apple Intelligence.
<!-- harbor:area-dictation:end -->

Speech is transcribed **entirely on your Mac** and never leaves it.

---

## 🧰 Quality of Life

Small tools you'll use every day.

<!-- harbor:area-qualityOfLife:start -->
- **Clipboard history**: Remembers text, links, images and files you copy: open it, type to search and press Return to paste. Pin items with ⌘P, delete with ⌘⌫, and keep 50 to 500 items. Copies from password managers and anything marked private are never saved, and history can stay in memory only if you prefer.
- **Paste as plain text**: Press ⌃⌥V to paste what you copied without its fonts, colors, sizes or links, in any app. Your clipboard keeps the original. In clipboard history, ⌥Return pastes the chosen item as plain text.
- **Auto-clear the clipboard**: Empties the clipboard a set time after each copy, or when your Mac locks or goes to sleep, so a password or address you copied doesn't linger. Clipboard history keeps what it saved.
- **Bluetooth while asleep**: Disconnects your Bluetooth headphones and speakers (or every device) when your Mac goes to sleep, so they don't stay tied to a sleeping Mac and can connect to your phone. When it wakes, Harbor reconnects only the devices it disconnected. Bluetooth itself stays on.
- **Clean links**: Optional: when you copy a web link, Harbor removes the tracking added to it (utm tags, fbclid, gclid, igsh, and the share IDs on YouTube, Spotify, TikTok and X links) and a note by the notch says how many. The rest of the link is untouched, so it opens the same page. Done on your Mac; nothing is looked up.
- **Quit protection**: Optional: the first ⌘Q only shows “Press ⌘Q again to quit” by the notch; press again, or hold the keys, to quit. It can also guard ⌘W on an app's last window. Pick apps it should leave alone.
- **Quit Apps**: Quit Apps lists every open app, from the island's Windows panel or Quit Apps… in the menu bar. Quit them one at a time, all at once, or all but the one in front; Quit All asks for a second click first. Apps with unsaved changes still ask before quitting, and Finder and Harbor are never listed.
- **Keep Awake**: Stop your Mac from sleeping, until you turn it off or for a set time, from the menu bar or the island's ☕ button. Optionally let the screen turn off while downloads and music keep running.
- **Keep Awake while working**: Turn on “While working” under Keep Awake and Harbor keeps your Mac awake only while real work is running, such as an export in Premiere Pro or Final Cut, a HandBrake encode, Claude or Terminal busy on a task, a download, or a script started with `harbor awake`, and if you like whenever it's plugged in or has an external display. When the work stops, it sleeps as usual. Optionally it keeps working with the lid closed, even on battery, through a small helper you approve once. On battery it gives up at 20% (you can change it) and lets the Mac sleep if it runs hot, so it never runs your Mac flat. The screen may turn off meanwhile.
<!-- harbor:area-qualityOfLife:end -->

**Windows**

<!-- harbor:area-windows:start -->
- **Window snapping**: Snap the front window with the keyboard: halves with the arrow keys, thirds with D, F and G, full screen with Return and centered with C, all with ⌃⌥. An adjustable gap keeps windows apart, and every shortcut can be changed.
- **Green button maximizes**: Optional: the green button makes a window fill the screen (keeping the menu bar, the Dock and your desktop) instead of opening a full-screen space. Click it again and the window goes back to where it was. ⌥-click and the View menu still do what macOS does.
- **Quit on last window**: Optional: pick apps (Preview, TextEdit, System Settings…) that quit as soon as you close their last window, like on Windows, instead of staying open in the Dock. Apps with windows on another desktop or minimized stay open.
- **Window layouts**: Save where all your windows are (“Coding”, “Writing”), then put them back with one click from the menu bar or the island, or with a shortcut. Apps that aren't open are opened, and if a monitor is missing the layout is fitted onto the screens you have.
- **Presenting**: One switch hides your desktop icons, turns on Do Not Disturb, keeps your Mac awake and quiets Harbor's pop-ups and clipboard history. Switch it off and everything is exactly as before.
<!-- harbor:area-windows:end -->

**Screen tools**

<!-- harbor:area-screenTools:start -->
- **Copy text from the screen**: Drag a box around anything on screen (a picture, a video, a PDF, an app that won't let you select) and its text is copied, read on your Mac in any language Apple supports. QR codes too: Harbor copies what they say and offers to open the link.
- **Capture to shelf**: Press the shortcut and drag a box (or click for the whole screen). The picture is copied and waits on the island's shelf, ready to drag into a message or document. No editor and no uploads: for recording or markup, macOS's own ⌘⇧5 is there.
- **Color picker**: A magnifier to pick any pixel on screen. The color is copied as HEX, RGB, HSL, SwiftUI or NSColor, your choice, and your last 10 colors wait in the island: click to copy again, right-click for another format.
<!-- harbor:area-screenTools:end -->

**Typing and the menu bar**

<!-- harbor:area-typing:start -->
- **Scratchpad**: Optional: press ⌃⌥N (or open it from the island's Windows panel or the menu bar) and a note drops down under the notch. Type while the app you're in stays in front; Esc or a click elsewhere puts it away. It's saved as you type, only on your Mac.
- **Text snippets**: Type a trigger like ;email in any app and it expands into your saved text, with {date}, {time}, {clipboard} and {cursor} filled in. Never in password fields or password managers, and you can exclude any app. Import and export your list. Off until you turn it on; ;date, ;time and ;shrug are ready to try.
- **Menu bar icon hider**: Optional: ⌘-drag menu bar icons to the left of Harbor's thin divider, then click the arrow to hide or show them; they tuck away again on their own. A short guide shows you how the first time.
<!-- harbor:area-typing:end -->

---

## 🎨 Make it yours

<!-- harbor:area-appearance:start -->
- **Appearance**: Settings → Appearance changes every Harbor panel at once: Liquid Glass (macOS 26), Frosted or Solid; Clear or Frosted glass with a strength slider; the system accent, a preset or any custom color, optionally tinting the glass; and corners and opacity. With Reduce Motion on, springs become gentle fades.
<!-- harbor:area-appearance:end -->

Every feature can be switched off on its own, and every setting has an ⓘ button that explains it.

---

## Shortcuts, backups and your own messages

<!-- harbor:area-platform:start -->
- **Shortcuts actions**: 12 Harbor actions for the Shortcuts app, including Grab Text (returns the text), Pick Color (returns the value), Start or Stop Dictation, Start Timer, Pomodoro, Snap Window, Apply Window Layout, Keep Awake, Presenting, Add File to Shelf, Switch Audio Output and Show Island Message. Many work from Spotlight and Siri too: “Grab text with Harbor”.
- **Island messages**: Any script or app can show a message in the island, with an icon, a progress bar and a link: through Shortcuts, a harbor:// link or the bundled harbor command-line tool. Each sender is listed in Settings and can be muted or blocked.
- **Back up and restore settings**: Export every setting, shortcut, snippet, vocabulary word and window layout to one .harbor file, and import it on another Mac. You see exactly what will change first, and your current settings are backed up automatically. Histories are never included.
<!-- harbor:area-platform:end -->

See [WIDGETS.md](WIDGETS.md) for island messages from your own scripts and apps.

## Install

1. Download **Harbor-x.y.z.dmg** from the [latest release](https://github.com/preston-inter/Harbor/releases/latest).
2. Open the DMG and drag **Harbor** into **Applications**.
3. Open Harbor. macOS says it can't check it for malicious software, because Harbor isn't from the App Store. Click **Done**.
4. Go to **System Settings → Privacy & Security** and click **Open Anyway** next to Harbor. You only need to do this once.

Harbor lives in the menu bar (the ⚓ icon). The guide opens the first time to show you around.

## Permissions

Allow only what you want to use. Anything you skip simply turns off the features that need it, and Harbor never crashes because of a missing permission.

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
| Automation | Lets Harbor control Music and Spotify and switch Dark Mode. macOS asks the first time you use each. | Now Playing, Quick buttons and timers |
<!-- harbor:permissions:end -->

You can see and fix them in **Settings → Permissions**. A "Fix…" link appears in the menu whenever a feature is waiting for one.

## Keyboard shortcuts

<!-- harbor:shortcuts:start -->
| Shortcut | What it does |
|---|---|
| Hover a Dock icon, or ⌘⇥ | Window previews |
| ⌥⇥ | Window switcher |
| Hold Right ⌥ | Dictate (hold) |
| ⌃⌥Space | Dictate (start/stop) |
| ⇧⌘V | Clipboard history |
| ⌃⌥V | Paste as plain text |
| ⌃⌥ ← / → | Snap left / right half |
| ⌃⌥ D / F / G | Snap to thirds |
| ⌃⌥ ↩ / C | Full screen / center |
| ⌃⌥ ↑ / ↓ | Snap top / bottom half |
| Set your own in Settings | Present |
| ⌃⌥O | Copy text from the screen |
| ⌃⌥S | Capture to shelf |
| ⌃⌥P | Pick a color |
| ⌃⌥N | Scratchpad |

Every shortcut can be changed in Settings.
<!-- harbor:shortcuts:end -->

## Privacy

Harbor works on your Mac: no accounts, no analytics, no tracking, and nothing you type, say, copy or see is uploaded. It connects to the internet only for these:

<!-- harbor:network:start -->
| What | Server | When | What's sent |
|---|---|---|---|
| Update checks | github.com (Harbor's releases) | When Harbor opens and every 30 minutes while automatic updates are on, and when you click Check for Updates… | A plain request for the update list. Nothing about you or your Mac (Sparkle's system profiling is off). |
| Spotify album art | Spotify's image server | While Spotify plays, to show the cover in the island | A request for the cover picture Spotify itself names for the song playing. |
<!-- harbor:network:end -->

- The camera and microphone indicator only checks whether they're in use. Harbor never sees or hears what they capture.
- Dictation and smart clean-up run **on your Mac only**.
- Window pictures are taken on demand and never saved.
- Clipboard history skips passwords and private items, and is stored readable only by your account, or kept in memory only if you prefer.

The full details, including what each permission sees and how to check it yourself, are on the [privacy page](PRIVACY.md).

## Updates and getting started

<!-- harbor:area-general:start -->
- **Welcome guide**: A short tour of every feature with animated examples, ending with a cheat sheet of your own shortcuts. New and updated features are marked until you've seen them. Open it any time from the menu bar or Settings → General.
- **Open at login**: Starts Harbor in the background when you log in, so the island and shortcuts are always ready. macOS may ask you to approve it under Login Items.
- **Automatic updates**: Harbor checks for updates when it opens and every 30 minutes, and asks before installing; Check for Updates… in the menu bar checks right away. Every update is signed, only updates signed with Harbor's own key are installed, and your settings are backed up and brought up to date as it installs.
- **Remove Harbor completely**: Settings → General → Remove Harbor Completely… turns off Open at Login and the lid helper, resets Harbor's permissions, and moves its settings (with a last backup), histories, shelf, captures and Harbor itself to the Trash. Nothing is deleted outright, so you can change your mind until you empty the Trash.
- **What's New**: After an update, a small pop-up by the notch says what changed, once. One click shows the highlights, with a way to try each new thing and to set up only what's new. Every version's notes stay under What's New in the menu bar.
<!-- harbor:area-general:end -->

## Experimental features

A few extras rely on parts of macOS that Apple doesn't officially offer to apps. They're **all off by default**, clearly labeled, and could stop working after a macOS update. If one does, Harbor falls back on its own.

<!-- harbor:experimental:start -->
- **Now Playing for every app**: Music and Spotify use Apple-approved methods. All apps also covers browsers, Podcasts and more, but relies on an unofficial part of macOS that could stop working after an update. If it does, Harbor goes back to Music and Spotify.
- **Replace macOS's volume and brightness pop-ups**: Experimental, off by default: Harbor takes the volume, mute and brightness keys and makes the change itself, so only the island's pop-up appears instead of two at once. Same steps as macOS (⌥⇧ for quarter steps). Any key Harbor can't apply, such as a speaker whose volume can't be set or an external display's brightness, goes to macOS as usual, and if Harbor stops responding the keys go back to macOS within a second. Brightness uses an unofficial part of macOS.
- **Exact brightness level**: macOS has no approved way for apps to read the brightness level, so this uses an unofficial part of macOS. It only reads the level and never changes it. Without it, the pop-up shows which way brightness changed.
- **Player on the lock screen**: Shows the Now Playing card on the lock screen, like on an iPhone. It uses an unofficial part of macOS, and anyone at your locked Mac can see what's playing and pause or skip it.
<!-- harbor:experimental:end -->

## FAQ

**Does it work on a Mac without a notch?**
Yes. The island sits at the top center of the screen. The Liquid Glass island style looks especially good there.

**Does it replace Apple's volume and brightness pop-ups?**
No, it shows alongside them.

**Does it slow my Mac down?**
Harbor is event-driven and idles at well under 1% CPU. Window pictures are only taken when a preview opens.

**How do I uninstall it?**
Settings → General → **Remove Harbor Completely…** takes away everything Harbor added (settings, histories, Open at Login, the lid helper, permissions) and moves Harbor to the Trash.

---

Made for macOS with Swift and SwiftUI.
