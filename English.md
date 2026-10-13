[English](English.md) | [中文](README.md)

![kcu logo](./Kcu_icon.png)
# KcuMigrator

"Better migration is in your hands" ----- Project initiator kongbai9288

This project currently supports FCL, Zalith, Pojav, Amethyst, HMCL-PE, 澪-Ultimate and most other Android Java Edition launchers (working hard on adaptation T_T)

This project uses AI-generated code, with the architecture and implementation methods designed by humans. If you do not agree, you may stop using this project.
* Note: A significant portion of the code implementation uses other projects. If you need it, please pay attention to their relevant policies. This project is not responsible for the behavior of other projects.

## Features
1. Quickly migrate related files and place them in the corresponding locations (Core feature)
2. Supports map editing, world editing, datapack generation, and the server automatically finds and downloads mods with matching names locally (Uploading requires personal confirmation; currently no automatic upload function is provided)
3. Stay tuned for other features

## How to Use

1. Download the <big>official release APK from Releases and install it
2. Open the App
3. Go to the Migration page: select the old version directory (the one containing the `mods` folder), select the new version directory, fill in the target MC version and loader, and click Scan.
4. Check the items you want to migrate and click Start Migration.

## Privacy

No credentials in the code. No account, has a backend (only for GitHub OAuth and CurseForge API, and can be replaced), no analytics, no ads.


- If you are sensitive to network connections, you can go to the Settings page and disable all network permissions (supported as much as possible; if you find any vulnerabilities, feel free to submit an issue).

Uninstalling the App will delete local data (except for the running parts and results you selected, such as the working directory). Full details are in the App: Settings → About → Privacy Statement.

## Third-Party Open Source Licenses and Acknowledgments

This project references and uses the following excellent open-source projects and third-party services during development. We would like to express our gratitude to all the authors!

### Core Dependencies

| Project Name | License | Purpose |
| :--- | :--- | :--- |
| [AndroidX](https://developer.android.com/jetpack/androidx) | Apache 2.0 | Basic UI components, lifecycle management, and core framework support |
| [WorkManager](https://developer.android.com/topic/libraries/architecture/workmanager) | Apache 2.0 | Background periodic update checks and synchronization |
| [Material Components](https://github.com/material-components/material-components-android) | Apache 2.0 | UI controls, themes, dialogs, bottom navigation |
| [OkHttp](https://github.com/square/okhttp) | Apache 2.0 | All network requests, foundation for multi-threaded chunked downloads |
| [Gson](https://github.com/google/gson) | Apache 2.0 | JSON parsing |
| [Jsoup](https://github.com/jhy/jsoup) | MIT | Parsing mod description pages to extract download links |
| [Coil](https://github.com/coil-kt/coil) | Apache 2.0 | Loading mod icons |

### Translation Engine
| Project Name | License | Purpose |
| :--- | :--- | :--- |
| [Google ML Kit Translate](https://developers.google.com/ml-kit/language/translation) | Non-open source (subject to Google APIs Terms of Service) | Offline translation of mod descriptions and web pages (model approx. 30MB, fully offline operation) |

> **Special Note on ML Kit**: The ML Kit SDK and translation models themselves are subject to the Google APIs Terms of Service and are not freely redistributable open-source components. Known restrictions: for use only on phones/tablets/laptops/desktops; use in embedded devices such as cars, TVs, home appliances, and speakers requires prior written permission from Google.

### Data Sources & APIs
| Project Name | Description |
| :--- | :--- |
| [Modrinth](https://modrinth.com) | Reads mod metadata via public HTTP API (platform code is AGPL-3.0; this project only reads data via API, which does not constitute code derivation) |
| [CurseForge](https://www.curseforge.com) | Reads mod metadata via public API and domestic mirror [MCIM](https://www.mcimirror.top) |
| [Pterodactyl](https://pterodactyl.io) | Client calls its Client API (panel server software is MIT licensed) |
| [GitHub REST API](https://docs.github.com/en/rest) | Used to read releases and repository files, subject to GitHub Terms of Service |

### Reference Implementations (For conceptual reference only, no direct code dependency)
| Project Name | License | Reference Points |
| :--- | :--- | :--- |
| [lingochamp/FileDownloader](https://github.com/lingochamp/FileDownloader) | Apache 2.0 | Multi-task concurrency, resume from breakpoint, chunked download scheduling concepts (this project implemented it independently using OkHttp with the same approach) |
| [jackfengji/android-download-manager](https://github.com/jackfengji/android-download-manager) | MIT | HTTP Range chunked downloads, concurrent task count control |
| [SirLYC/YC-Downloader](https://github.com/SirLYC/YC-Downloader) | MIT | Multi-task queue, speed limits, progress callback throttling |
| [Blocktopograph](https://github.com/MithrilMania/Blocktopograph) | GPL-3.0 | Referenced its usage logic |

### NBT Read/Write & Datapack Generators
| Project Name | License | Purpose |
| :--- | :--- | :--- |
| [ViaNBT](https://github.com/ViaVersion/ViaNBT) | MIT | Read/write `level.dat` and other NBT format files |
| [misode.github.io](https://github.com/misode/misode.github.io) | MIT | Datapack and resource pack generator (137 built-in generators, offline available) |
| [misode-vianbt-android](https://github.com/kongbai9288/misode-vianbt-android) | MIT | Android adaptation of the above projects (replaces fastutil dependency, mobile layout, offline packaging) |

### System Components
- **Android Download Manager** (`android.app.DownloadManager`): Used for app update downloads; resume from breakpoint and installation triggering are provided by the system.
- **AndroidX Core / FileProvider** (Apache 2.0): Used to share crash logs to other apps via the system share sheet.
- **Material Icons** ([fonts.google.com/icons](https://fonts.google.com/icons)) (Apache 2.0): All icon resources in this project.

---

**Notes:**
- This project's own code does not use any copyleft (GPL/AGPL/LGPL) components.
- If you find that this project uses third-party code not listed here, or believe there is a license conflict, please submit an Issue.
- This list is updated with versions; the latest version in the app shall prevail..

## Beta Version

[KCU Beta Version](https://github.com/kongbai9288/mc-mod-migrator)
- ⚠️Note: This may cause serious errors in your operation. Non-testers please do not use this version (if you use this version, you are responsible for any mistakes caused).

## Friendly Links

### Launchers

- [PojavLauncher](https://github.com/PojavLauncherTeam/PojavLauncher) — The earliest and most well-known Android/iOS Java Edition launcher, based on Boardwalk.
- [ZalithLauncher2](https://github.com/ZalithLauncher/ZalithLauncher2) — A modern launcher redesigned based on PojavLauncher and Jetpack Compose.
- [FoldCraftLauncher (FCL)](https://github.com/FCL-Team/FoldCraftLauncher) — A feature-rich and actively updated Android Java Edition launcher with mod management support.
- [Amethyst-Android](https://github.com/AngelAuraMC/Amethyst-Android) — The official successor project of PojavLauncher.
- [HMCL-PE](https://github.com/HMCL-dev/HMCL-PE) — Android port of Hello Minecraft! Launcher (discontinued).
- [MojoLauncher](https://github.com/MojoLauncher/MojoLauncher) — A launcher based on PojavLauncher.
- [MCinaBox](https://github.com/AOF-Dev/MCinaBox) — An earlier Android Java Edition launcher, encapsulating BoatApp.
- [BoatApp](https://github.com/AOF-Dev/BoatApp) — A lightweight Android Java Edition runtime environment.
- [ShardLauncher](https://github.com/ShardLauncher/ShardLauncher) — A mobile launcher based on Jetpack Compose.