# Showing your own messages in Harbor's island

Any app, script or shortcut can show a short message in Harbor's Notch Island: a title, an
optional detail line, an SF Symbol, a progress bar and a link. This is **island messages v1**,
available from Harbor 1.0.

Real third-party widgets (your own SwiftUI view living in the island) are **v2**. They're
designed below but **not available yet**.

---

## v1: island messages

### Three ways to send one

**1. Shortcuts:** use Harbor's **Show Island Message** action. It's also available in Spotlight and
Siri through any shortcut you build with it.

**2. A link:** open a `harbor://` URL from anywhere, for example a browser, `open` in Terminal, or
`NSWorkspace.open` in your app:

```
harbor://message?title=Build%20finished&subtitle=12%20tests%20passed&symbol=checkmark.seal&sender=CI
```

**3. The command-line tool:** it's bundled inside Harbor at `Harbor.app/Contents/Helpers/harbor`.
In Settings → General → Island messages, **Copy Install Command** gives you a one-line `sudo ln -s`
to put it on your PATH:

```sh
harbor message "Build finished" --subtitle "12 tests passed" --symbol checkmark.seal --from CI
harbor message "Uploading" --progress 0.4 --id upload      # later calls with --id upload update it
harbor --help
```

The tool only builds a `harbor://` link and opens it in the background, so all three ways follow
the same rules.

### Parameters

| URL parameter | CLI option | Meaning |
|---|---|---|
| `title` (required) | first argument | Up to 80 characters |
| `subtitle` | `--subtitle` | Up to 160 characters, shown on one line |
| `symbol` | `--symbol` | Any SF Symbol name; unknown names fall back to a speech bubble |
| `progress` | `--progress` | 0 to 1; shows a bar and the percentage |
| `id` | `--id` | Messages with the same id **update** the one on screen instead of stacking |
| `link` | `--link` | Opened by an **Open** button. Web, mail and app links only; `file:` and `javascript:` are refused |
| `duration` | `--duration` | 1 to 30 seconds (default 4). A message with progress below 1 stays up to 60 s |
| `sender` | `--from` | Who it's from, shown under the title and listed in Settings. Defaults: Shortcuts, "Link", "Terminal" |

### Rules

- **Rate limit:** each sender can show **10 messages a minute**. Extra messages are dropped, not
  queued. For a progress bar, update the same `id` a few times a second at most.
- **Mute and block:** every sender appears in Settings → General → Island messages, with how many
  messages it sent and when. From there you can choose:
  - **Mute for 1 hour** or **until tomorrow**: messages are dropped until then.
  - **Block**: dropped until you choose **Allow**.
  - **Forget**: removes the sender from the list.
- **Turning it off:** the switch at the top turns island messages off entirely.
- **Presentation mode:** messages are dropped while "Quiet Harbor" is on.
- **Privacy:** messages never leave your Mac. Harbor logs only that a message was shown or dropped,
  never its text.

### Sample: a build progress bar

`Samples/IslandProgress/` contains two things:
- `build-progress.sh`: a shell script that runs a fake build and moves a progress bar in the island,
  updating one message by its id.
- `IslandMessageKit/`: a tiny Swift package with `IslandMessage.send(title:…)`, which builds the
  link for you. It needs no dependencies and works from any macOS app.

---

## v2: island widgets (design, not available yet)

The goal is to let other apps ship a **real widget** for the island: their own SwiftUI view, live
data and buttons. It has to be done without ever loading their code into Harbor.

### Architecture

- **Extension point:** Harbor declares an ExtensionKit extension point,
  `dev.harbor.Harbor.island-widget`.
- **Shipping a widget:** an app adds a **sandboxed app extension** (`.appex`) with a type that
  conforms to Harbor's `IslandWidgetExtension` protocol, published as a small Swift package,
  `HarborWidgetKit`. The extension declares:
  - its display name and symbol
  - the sizes it supports: **wings** (a small item beside the notch) and **row** (a full-width
    line in the open island)
  - a SwiftUI `body`, provided through `AppExtensionSceneConfiguration`
- **Hosting:** Harbor shows the extension's scene with `EXHostViewController` inside the island.
  The view is drawn by the **extension's own process**. Harbor only hosts its remote view, so
  third-party code never runs inside Harbor.
- **Data:** it flows over the extension's XPC connection (`NSXPCConnection` from
  `EXHostViewController`), using a small Codable protocol:
  - **Harbor → widget:** `appearance` (accent, style, scale), `size` (wings or row), `isVisible`,
    `tap`
  - **Widget → Harbor:** `wantsAttention(until:)` (asks to be shown as a pop-up, rate-limited like
    v1), `openURL` (same link rules as v1)

### Approval and privacy

- **Approval first:** widgets are found with `AppExtensionPoint.Monitor`, but **none is shown until
  you approve it**. A sheet lists the app, the widget's name, and what it asks for (wings, row,
  pop-ups).
- **Managing widgets:** Settings gets an "Island widgets" list, where you can enable or disable,
  reorder and remove each one. Turning a widget off ends its extension process.
- **Limits:** widgets get no data from Harbor beyond appearance and size. Their pop-up requests
  follow the same per-sender limit, mute and block as v1.

### What has to be true before v2 ships

- **ExtensionKit hosting:** must work in Harbor's non-activating island panel. A prototype needs to
  confirm focus and hit-testing.
- **Performance:** a widget must not push the island above 1% CPU while idle, so Harbor will pause
  widgets that aren't visible.
- **A sample:** `Samples/IslandWidgetSample/` (still to come), a sample app with a weather-style
  widget, built against `HarborWidgetKit`.

Status: **designed, waiting for the go-ahead to build**.
