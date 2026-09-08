# Parall for macOS - Multi-Instance App Launcher

**Run multiple independent instances of the same app on your Mac.**

Use supported apps side by side with separate accounts, profiles, data, and settings where supported. Give each instance its own name and Dock icon without copying or modifying the original app.

[Visit Website](https://parall.app) | [Download on the Mac App Store](https://apps.apple.com/app/apple-store/id6754065114?pt=127627850&ct=github&mt=8)

---

## About Parall

**Parall** lets you run multiple instances of supported macOS apps. Each instance can have its own identity and launch configuration, with separate accounts, profiles, and data when the target app supports separation.

Parall makes this possible by creating lightweight launcher app bundles called shortcuts. Each app shortcut launches the original installed app directly. It does not contain a copy of the target app or modify, repackage, or re-sign it. You can customize its name, Dock icon, arguments, environment variables, Dock effects, icon label, and optional menu bar icon. Data separation and HOME override depend on app compatibility.

Parall also creates Web App shortcuts for website URLs and shortcuts for files, folders, and command-line tools.

Parall is designed for workflows where one app instance is not enough.

- Separate browser profiles with separate Dock icons.
- Multiple native app accounts side by side.
- Separate development environments for supported tools such as VS Code, Cursor, JetBrains apps, Terminal apps, and command-line launchers.
- Multiple isolated Philips Hue Sync instances with different data folders for different display setups.
- Web App shortcuts for websites, including WhatsApp and Microsoft Teams, with separate data paths and notifications or unread badges where supported.

Parall works locally and offline for shortcut creation and launching. It has no automatic telemetry or background services after you quit it. The optional **Download Compatibility Settings** button makes a network request as explained below. Web App shortcuts use the system Safari/WebKit engine.

---

## Key Features

- **Multiple App Instances** - Run multiple instances of the same supported macOS app side by side.
- **Separate Data Storage** - Use automatic data separation for supported Chrome-based, Firefox-based, Electron-based, Eclipse-based, and ToDesktop-based apps, including supported sandboxed apps. Advanced HOME override works with many other compatible apps.
- **Menu Bar Icons** - Add an optional menu bar icon for any shortcut while the target app is running, with controls for icon scale, grayscale, and template-mask behavior.
- **Browser Actions** - For supported browsers, open new or private/incognito windows directly from the shortcut menu bar icon.
- **Dock Shortcuts** - Pin app instances, Web Apps, files, folders, and command-line shortcuts to the Dock.
- **Dock Effects and Labels** - Apply per-shortcut Dock icon animations, visual effects, and drawn text labels.
- **Custom Icons** - Extract icons from apps or files, or choose a custom icon for each shortcut.
- **Arguments and Environment Variables** - Configure per-shortcut command-line arguments, custom environment variables, working directories, and HOME overrides.
- **Advanced Info.plist Overrides** - Override selected shortcut bundle parameters for experienced workflows.
- **Web App Mode** - Open a website URL in a native WebKit window with its own Dock identity and data storage path. WhatsApp and Microsoft Teams are predefined targets. Notifications and unread badges depend on the website and its support in Parall.
- **Limited iOS/iPadOS Shortcuts** - On Apple silicon Macs, create limited shortcuts for iOS and iPadOS apps. These can launch and receive arguments or environment variables, but cannot separate data or provide a dedicated Dock icon.
- **No System Modifications** - Parall does not alter system files, target app bundles, or app binaries.
- **Private by Design** - No automatic telemetry or background daemons. Compatibility settings are downloaded only when you explicitly request them.

---

## Supported Apps

Parall supports a wide range of macOS apps. Compatibility depends on whether the target app allows multiple instances and whether macOS permits its data to be redirected.

Verified or specially handled apps and app families include the following.

- Chromium-based browsers and apps, including Google Chrome, Chromium, Microsoft Edge, Brave, Vivaldi, Dia Browser, Perplexity Comet, and OpenAI Atlas.
- Firefox-based apps, including Mozilla Firefox, Zen Browser, and Tor Browser.
- ToDesktop-based and Electron-based desktop apps.
- Eclipse-based apps, JetBrains apps, Android Studio, VS Code, Cursor, OpenAI Codex, Windsurf, DBeaver, Sublime Text, Sublime Merge, iTerm2, Ghostty, Terminal-style apps, and other developer tools.
- Communication and productivity apps such as Slack, Discord, Telegram Desktop, Viber, Signal, Notion, Claude, Beeper Desktop, Spark Desktop, Evernote, Dropbox, Anki, OBS, Philips Hue Sync, Spotify, Zoom, and many more.
- WhatsApp and Microsoft Teams through Parall's native WebKit web frames.

Sandboxing alone does not prevent data separation. Supported sandboxed Electron-based, Firefox-based, Chrome-based, and Eclipse-based apps can use separate data while the target app remains sandboxed. Select **Auto** under **Data Storage Mode** and a unique **Data Storage Path** for each instance. Other sandboxed apps may remain limited to their system container and cannot separate data with a plain HOME override.

Ihor July personally tests each app's compatibility with Parall and manually configures and tests every compatibility profile. Results come from actually running and using the apps, not guesses or AI testing. Compatibility can change after app or macOS updates.

Apple apps and apps with bundle identifiers starting with `com.apple.` may behave differently depending on macOS version, and not all Parall features are guaranteed for them.

For the current compatibility table, see [parall.app/compatibility](https://parall.app/compatibility/).

---

## Technical Notes

- Parall-created app shortcuts are standalone `.app` bundles that launch the original target directly.
- Regular app shortcut bundles are **not sandboxed** because they directly launch the installed target app. Their signing and approval requirements depend on the macOS version and setup. Web App shortcuts use sandboxed bundles.
- Parall itself is sandboxed and works offline, with the optional compatibility settings request described below.
- Shortcuts do not inject code into target apps and do not modify app binaries.
- Shortcuts point to the original app bundle, so when the original app updates, the shortcut uses the updated app after restart.
- On macOS 11 and older, newly created shortcuts require manual signing before they can be launched normally. Any signing or approval applies only to the launcher bundle. The target app's original developer signature remains intact.
- Updating Parall does not update existing shortcuts. To apply shortcut engine fixes, open Parall, press **Edit**, select the existing shortcut, and overwrite it with the regenerated version. Preserve its **Data Storage Path** to reuse its existing profile and data.
- Some apps with built-in updaters may need macOS App Management permission when launched from a shortcut. Parall recommends granting this only to the shortcut instance you use for target-app updates.
- WhatsApp and Microsoft Teams support use the system Safari/WebKit engine, not Electron or bundled Chrome.
- Passkeys are not supported in **Web App mode**. Use another sign-in method such as an authenticator app, SMS code, or phone call. If the website requires passkeys, use a full browser or its native app instead.

---

## Requirements

- macOS **10.11 El Capitan** or newer
- Apple Silicon or Intel Mac
- Apple silicon is required for limited iOS/iPadOS app shortcuts

---

## Privacy

Parall works locally by default.

- Works offline.
- Sends no automatic telemetry.
- Makes a compatibility settings request only when you press **Download Compatibility Settings**.
- Runs no background services after you quit it.

Shortcuts that launch online services still use whatever network access those target services require. For example, WhatsApp and Microsoft Teams shortcuts connect to their corresponding web services because they run through native WebKit web frames.

The optional compatibility request sends Parall version and build, macOS version and architecture, and the selected app's name and bundle identifier. The server uses app details, including sandbox status, to find the appropriate settings. It stores an IP-derived hash instead of the raw IP address. Requests also help identify demand for apps without profiles so Ihor July can prioritize testing and support.

This information is not linked to your identity and is not used for advertising or tracking. This optional request is why the Mac App Store privacy label lists **Other Data** under **Data Not Linked to You**. Documentation links may also include version information when you choose to open them.

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

Parall is designed, coded, and tested by **Ihor July**, a cybersecurity expert and reverse engineer. Its shortcut engine grew from personal research into native macOS behavior and direct app testing.

Ihor July also develops [DockLock Pro](https://docklockpro.com), [App Trust Preview](https://apptrustpreview.com), [LockLines](https://locklines.app), and [App Archiver](https://apparchiver.com).

---

## License

Copyright (c) Ihor July.  
All rights reserved.  
Parall is distributed via the Mac App Store.

---

**[Get Parall on the Mac App Store](https://apps.apple.com/app/apple-store/id6754065114?pt=127627850&ct=github&mt=8)**
