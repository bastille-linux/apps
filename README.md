# bastille-apps

GTK4 native apps for Bastille OS. Fetched by the first-boot wizard — not baked into the ISO.

| App | ID | Description |
|-----|----|-------------|
| Browser | `com.bastille.browser` | Tor+Zen hybrid privacy browser |
| Calendar | `com.bastille.calendar` | Offline calendar with Mail/Messages event detection |
| Documents | `com.bastille.documents` | LibreOffice Writer launcher with age decrypt |
| Files | `com.bastille.files` | File manager with age/GPG encryption badges |
| Mail | `com.bastille.mail` | Encrypted mail — Guerrilla Mail disposable + PGP |
| Maps | `com.bastille.maps` | Offline maps viewer |
| Messages | `com.bastille.messages` | Signal / Session / GPG messaging hub |
| Music | `com.bastille.music` | Local music player (GStreamer) |
| Notes | `com.bastille.notes` | Encrypted notes — PIN lock + markdown preview |
| Presentations | `com.bastille.presentations` | LibreOffice Impress launcher |
| Settings | `com.bastille.settings` | System hardening configuration panel |
| Sheets | `com.bastille.sheets` | LibreOffice Calc launcher |
| Terminal | `com.bastille.terminal` | Multi-tab terminal (VTE) |
| Weather | `com.bastille.weather` | Privacy-first weather via wttr.in |

## Architecture

Apps are Python 3 + GTK4/libadwaita. Each app directory contains:
- `main.py` — the app executable
- `manifest.json` — metadata, version, and runtime deps

The ISO ships only the GTK4 runtime. The first-boot wizard fetches whichever apps the user selects and installs them to `/usr/local/bin/bastille-<name>`.

## Design

All apps use the Bastille dark design system — forced `Adw.ColorScheme.FORCE_DARK`, `Adw.NavigationSplitView` layouts, and the shared CSS token palette.
