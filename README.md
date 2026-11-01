# bastille-apps

GTK4 native apps for Bastille OS. Fetched by the first-boot wizard — not baked into the ISO.

| App | Description |
|---|---|
| Notes | Encrypted local notes |
| Music | Local music player |
| Calendar | Offline calendar |
| Maps | Offline maps viewer |
| Mail | Encrypted mail client |
| Settings | System configuration panel |

## Architecture

Apps are Python + GTK4/libadwaita. The ISO ships only the runtime (`gir1.2-gtk-4.0`, `gir1.2-adw-1`).
The wizard fetches whichever apps the user selects at first boot.

## Adding an app

Each app lives in its own subdirectory with a `manifest.json`:
```json
{
  "id": "com.bastille.notes",
  "name": "Notes",
  "description": "Encrypted local notes",
  "deps": ["python3-gi", "gir1.2-gtk-4.0"]
}
```
