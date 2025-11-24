# Parall for macOS - The Parallel App Launcher for macOS

**Run multiple instances of any Mac app - easily, safely, and beautifully.**  
Create independent app shortcuts that behave like separate apps in your Dock.

🔗 [Visit Website](https://parall.app) | [Download on the Mac App Store](https://apps.apple.com/app/apple-store/id6754065114?pt=127627850&ct=github&mt=8)

---

## About Parall

**Parall** lets you create separate app shortcuts that launch new, independent instances of your existing macOS apps - all without modifying system files or the original app.

Parall is the first macOS app of its kind to do this properly and natively.

Each shortcut is a self-contained `.app` bundle that appears as a separate icon in your Dock.  
Shortcuts can also add an optional tray menu icon in the menu bar while the target app is running so you can show, hide or quit the app and, for supported browsers, open new or incognito windows directly from the tray.  
You can use Parall to run multiple copies of browsers, productivity apps, or any other app - with unique settings, arguments, or profiles.

---

## Key Features

- **Multiple App Instances** - Run apps side-by-side as if they were different applications.
- **Optional Tray Menu Icons** - Add a tray menu icon for any shortcut while the target app is running for quick show, hide, quit and, for supported browsers, one click new and incognito windows.
- **Dock Shortcuts** - Each shortcut appears as its own icon in the Dock and can be pinned.
- **Automatic Updates** - Shortcuts stay in sync when the original app updates.
- **Custom Command Line Arguments** - Configure per-shortcut options and pass additional command line arguments through the shortcut directly to the target app.
- **Optional Data Storage Separation** - Built in support for separate data folders for Chromium based browsers, Firefox based apps and many other non sandboxed apps.
- **Home Directory Override** - Override the HOME environment variable and combine it with app specific data layouts to separate data for more apps.
- **Per Shortcut Environment Variables** - Define custom environment variables per shortcut to fine tune how apps start and where they keep their data.
- **Fully Offline & Private** - Parall never connects to the Internet or sends data anywhere.
- **No Background Services** - Nothing runs when you close it.
- **No System Modifications** - Works entirely within the user space - no scripts, no hacks.

---

## Supported Apps

- Works with **most non sandboxed macOS apps**.
- Built in data storage isolation profiles for **Chromium based browsers**, **Firefox based apps** and many **ToDesktop based** apps.
- Many other non sandboxed apps can use HOME override and other data storage modes so each shortcut keeps its data fully separated.
- Sandboxed Mac App Store apps and iOS or iPadOS apps on macOS are not supported for data separation and often cannot be launched through shortcuts.
- **Note:** Apple system apps (bundle IDs starting with `com.apple.`) are not supported as targets.

---

## Technical Notes

- The shortcuts Parall creates are **unsigned** and **not sandboxed** by design and they can optionally launch a small helper that shows the tray menu icon while the target app is running.  
- Parall and its shortcuts **do not modify any files or applications**.
- Parall is **fully sandboxed**, **works offline**, and **never sends any data**.
- When you launch a shortcut with extra command line arguments Parall forwards those arguments directly to the target app.

---

## Requirements

- macOS **10.10 (Yosemite)** or newer
- Apple Silicon or Intel Mac

---

## Privacy

Parall is privacy-friendly by design:
- Works entirely offline  
- Sends **no data** and makes **no network requests**
- Website uses [Plausible Analytics](https://plausible.io/) - a privacy-respecting, cookie-free analytics tool

Read the full privacy policy at [https://parall.app/privacy](https://parall.app/privacy)

---

## Support

- Website: [https://parall.app](https://parall.app)  
- FAQ: [https://parall.app/faq](https://parall.app/faq)  
- Contact: [https://parall.app/support](https://parall.app/support)  

---

## Credits

Parall is developed by **Ihor July**, the creator of [DockLock Lite and DockLock Plus](https://docklockpro.com).  
Designed with care to make macOS multitasking simple, efficient, and elegant.

---

## License

Copyright © Ihor July.  
All rights reserved.  
Parall is distributed via the Mac App Store.

---

**[→ Get Parall on the Mac App Store](https://apps.apple.com/app/apple-store/id6754065114?pt=127627850&ct=github&mt=8)**
