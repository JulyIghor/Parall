# Parall for macOS - Multi-Instance App Launcher

**Create independent macOS shortcuts for apps, files, folders, and command-line tools.**  
Run multiple app instances with separate data and settings, give each shortcut its own Dock icon, and keep everything native, private, and offline.

[Visit Website](https://parall.app) | [Download on the Mac App Store](https://apps.apple.com/app/apple-store/id6754065114?pt=127627850&ct=github&mt=8)

---

## About Parall

**Parall** creates lightweight shortcut bundles that launch your existing macOS apps, files, folders, or command-line tools without modifying the original target.

For app shortcuts, each shortcut behaves like a standalone app where macOS supports it: it can have its own Dock icon, name, arguments, environment variables, data folder, HOME override, Dock effects, icon label, and optional menu bar icon.

Parall is designed for workflows where one app is not enough:

- Separate browser profiles with separate Dock icons.
- Multiple native app accounts side by side.
- Isolated development environments for tools such as VS Code, Cursor, JetBrains apps, Terminal apps, and command-line launchers.
- Multiple isolated Philips Hue Sync instances with different data folders for different display setups.
- WhatsApp shortcuts with notifications, unread badges, menu bar background mode, and separate data paths.

Parall works locally, has no telemetry, does not run background services after you quit it, and does not use Electron or a bundled Chrome engine.

---

## Key Features

- **Multiple App Instances** - Run supported macOS apps side by side as separate shortcuts.
- **Separate Data Storage** - Use automatic data separation for supported non-sandboxed apps, Chromium-based browsers, Firefox-based apps, ToDesktop-based apps, Eclipse-based apps, and many other apps.
- **Menu Bar Icons** - Add an optional menu bar icon for any shortcut while the target app is running, with controls for icon scale, grayscale, and template-mask behavior.
- **Browser Actions** - For supported browsers, open new or private/incognito windows directly from the shortcut menu bar icon.
- **Dock Shortcuts** - Pin app, file, folder, and command-line shortcuts to the Dock.
- **Dock Effects and Labels** - Apply per-shortcut Dock icon animations, visual effects, and drawn text labels.
- **Custom Icons** - Extract icons from apps or files, or choose a custom icon for each shortcut.
- **Arguments and Environment Variables** - Configure per-shortcut command-line arguments, custom environment variables, working directories, and HOME overrides.
- **Advanced Info.plist Overrides** - Override selected shortcut bundle parameters for experienced workflows.
- **WhatsApp Support** - Run WhatsApp through a lightweight native WebKit frame with push notifications, unread badges, optional menu bar background mode, and separate shortcut data paths.
- **Limited iOS/iPadOS Shortcuts** - On Apple silicon Macs, create limited shortcuts for iOS and iPadOS apps. These can launch and receive arguments or environment variables, but cannot separate data or provide a dedicated Dock icon.
- **No System Modifications** - Parall does not alter system files, target app bundles, or app binaries.
- **Private by Design** - No telemetry, no background daemons, and no network requests from Parall itself.

---

## Supported Apps

Parall supports a wide range of macOS apps. Compatibility depends on whether the target app allows multiple instances and whether macOS permits its data to be redirected.

Verified or specially handled app families include:

- Chromium-based browsers and apps, including Google Chrome, Chromium, Microsoft Edge, Brave, Vivaldi, Dia Browser, Perplexity Comet, and OpenAI Atlas.
- Firefox-based apps, including Mozilla Firefox, Zen Browser, Opera, and Tor Browser.
- ToDesktop-based apps and many Electron-style desktop apps.
- Eclipse-based apps, JetBrains apps, Android Studio, VS Code, Cursor, OpenAI Codex, Windsurf, DBeaver, Sublime Text, Sublime Merge, iTerm2, Ghostty, Terminal-style apps, and other developer tools.
- Communication and productivity apps such as Slack, Discord, Telegram Desktop, Viber, Signal, Notion, Claude, Beeper Desktop, Spark Desktop, Evernote, Dropbox, Anki, OBS, Philips Hue Sync, Spotify, Zoom, and many more.
- WhatsApp through Parall's native WebKit web frame.

Sandboxed Mac App Store apps are partially supported. They can often be launched as shortcuts, but macOS keeps their data inside the system container, so custom data or HOME redirection is not available.

Apple apps and apps with bundle identifiers starting with `com.apple.` may behave differently depending on macOS version, and not all Parall features are guaranteed for them.

For the current compatibility table, see [parall.app/compatibility](https://parall.app/compatibility/).

---

## Technical Notes

- Parall-created app shortcuts are standalone `.app` bundles that launch the original target directly.
- Shortcut bundles are **unsigned** and **not sandboxed** by design because they need to execute the target app bundle.
- Parall itself is sandboxed, works offline, and does not send telemetry.
- Shortcuts do not inject code into target apps and do not modify app binaries.
- Shortcuts point to the original app bundle, so when the original app updates, the shortcut uses the updated app after restart.
- On macOS 11 and older, newly created shortcuts may require manual signing before they can be launched normally.
- Some apps with built-in updaters may need macOS App Management permission when launched from a shortcut. Parall recommends granting this only to the shortcut instance you use for target-app updates.
- WhatsApp support uses the system Safari/WebKit engine, not Electron or bundled Chrome.

---

## Requirements

- macOS **10.11 El Capitan** or newer
- Apple Silicon or Intel Mac
- Apple silicon is required for limited iOS/iPadOS app shortcuts

---

## Privacy

Parall is privacy-friendly by design:

- Works offline.
- Sends no telemetry.
- Makes no network requests from the Parall app itself.
- Runs no background services after you quit it.

Shortcuts that launch online services still use whatever network access those target services require. For example, a WhatsApp shortcut connects to WhatsApp Web because it runs `web.whatsapp.com`.

The website uses [Plausible Analytics](https://plausible.io/), a privacy-respecting, cookie-free analytics tool.

Read the full privacy policy at [https://parall.app/privacy-policy](https://parall.app/privacy-policy).

---

## Support

- Website: [https://parall.app](https://parall.app)
- FAQ: [https://parall.app/faq](https://parall.app/faq)
- Compatibility: [https://parall.app/compatibility](https://parall.app/compatibility/)
- Contact: [https://parall.app/support](https://parall.app/support)
- Issues: [https://github.com/JulyIghor/Parall/issues](https://github.com/JulyIghor/Parall/issues)

---

## Credits

Parall is developed by **Ihor July**, the creator of [DockLock Lite and DockLock Plus](https://docklockpro.com).

---

## License

Copyright (c) Ihor July.  
All rights reserved.  
Parall is distributed via the Mac App Store.

---

**[Get Parall on the Mac App Store](https://apps.apple.com/app/apple-store/id6754065114?pt=127627850&ct=github&mt=8)**
