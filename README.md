# NxAddonManager

**NxAddonManager** is a lightweight, non-commercial desktop utility for managing my personal **World of Warcraft** addon installations on **Windows and macOS**.

The project is intended primarily for use on two personal computers. Its goals are to simplify addon maintenance, preserve existing configuration, and keep user-interface settings consistent between devices without requiring a resource-intensive background application.

> **Project status:** Private prototype (v0.3). The application is under development and has not been publicly released. The source code and executable builds are not published in this repository at this stage.

## What it does

The current prototype includes:

- **Separate game installations:** Manage World of Warcraft **Retail** and **Forever** independently.
- **Addon discovery:** Identify locally installed addons using their `.toc` metadata.
- **Backups and rollback:** Back up `Interface/AddOns` and `WTF`, and retain previous addon versions for recovery.
- **Manual ZIP installation:** Install addon packages while validating archive paths and the target game installation.
- **Settings transfer:** Copy addon `SavedVariables` between Windows and macOS through a user-provided synchronized folder.
- **Conflict protection:** Detect conflicting changes and avoid silently overwriting locally modified settings.
- **Lightweight operation:** Use a small local application with a browser-based interface, rather than a continuously running heavy desktop framework.

The synchronization feature transfers configuration data **only when the game is closed**. It does not make live changes to the UI of a running World of Warcraft client. Game-specific settings, display resolution, and local client configuration are kept separate by default.

## CurseForge integration — planned

The primary intended source of addon releases is **CurseForge**. Subject to approval for access to the official CurseForge API and compliance with its terms, the intended update workflow is:

1. Identify the relevant CurseForge project and installed addon version.
2. Check periodically for a newer release compatible with the selected World of Warcraft installation.
3. Download only releases that the API and the relevant project permissions allow.
4. Create a local rollback backup before updating.
5. Replace the installed addon files while preserving their settings in `WTF`.
6. Defer file replacement while World of Warcraft is running.

**Automatic CurseForge downloads are not implemented or enabled in the current prototype.** API access is being requested for this limited, personal-use case. No API key or other credential will be committed to this repository.

## Scope and privacy

NxAddonManager is intended for **private, personal, non-commercial use** on my own computers.

- It is not a public addon repository, redistribution service, or CDN mirror.
- It does not distribute addon packages to other users.
- Settings synchronization uses a folder and synchronization service configured by the user; the project does not operate a remote synchronization server.
- The intended API implementation will respect publisher permissions, applicable rate limits, and CurseForge's API terms.

The project is an independent personal utility and is **not affiliated with, endorsed by, or sponsored by CurseForge, Overwolf, Blizzard Entertainment, or Microsoft**.

## Development status

NxAddonManager is being developed as an experimental personal tool. The current prototype has undergone automated logic tests, but cross-platform behavior on the target Windows and macOS devices still requires practical validation. Features and implementation details may change.

This repository currently serves as a **project information page** for the API access request. Public source-code distribution and releases are not planned at this stage.
