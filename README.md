# DayZ Material Viewer

See your DayZ models the way the game renders them — before you pack a single PBO.

The viewer loads your Object Builder `.p3d`, resolves every `.rvmat` and texture from your P drive, and renders them
with a **pixel-identical rebuild of DayZ's Super shader** and the game's own lighting, measured with RenderDoc in DayZ.

This repository only hosts the **releases** (downloads). The viewer's source code is not public.

## Download

Get the latest `DayZViewer-<version>-win-x64.zip` from **[Releases](../../releases/latest)**.

## Features

- **Super shader rebuilt 1:1** — `_co`, `_nohq`, `_smdi`, `_as`, `_mc`, detail, env, fresnel(N,K) and emissive stages
  exactly as the game's `ps_super` uses them.
- **In-game lighting** — clear day, morning, evening, dusk, overcast, night with and without moon, inventory preview;
  DayZ's tone mapping and bloom, sun shadows, SSAO and anti-aliasing as in the game's settings.
- **Material panel** — edit `ambient`, `diffuse`, `specular`, `specularPower`, `fresnel(N,K)` … live and save them back
  into the rvmat; try other textures per stage (preview only).
- **Proxies** — magazines, optics, stocks: shown in place, each with its own materials.
- **Live link to Substance Painter** — with the [RwG DayZ Texture Exporter](https://github.com/rv103/RwG_DayZ_Painter_Plugin)
  plugin, exported textures and rvmat values appear at once, and material edits go back to Painter.
- **Hot reload** — save a texture or rvmat and the viewer updates.
- English and German UI.

## Requirements

- Windows 10 or 11, 64-bit, a DirectX 11 graphics card.
- Your mod files on the **P drive** (DayZ Tools work drive), set in *Settings → P drive*.
- **Object Builder (MLOD) P3Ds.** Binarized (ODOL) models and proxies are not supported.
- No .NET installation needed — the runtime is included.

## Install

1. Unzip into a folder of your own (for example `D:\Tools\DayZViewer`), **not** into *Program Files* — the viewer
   updates itself and needs write access to its folder.
2. Start `DayZViewer.exe` and open a `.p3d` (or drop it into the window).

The viewer is not code-signed. On the first start Windows SmartScreen may show *"Windows protected your PC"*:
click **More info → Run anyway**. Settings are stored in `%APPDATA%\DayZViewer`, not in the program folder.

## Updates

*Settings → Updates*: the viewer looks for a new release at start (once a day, can be switched off) or when you click
**Check now**. **Install and restart** downloads the zip, verifies its SHA-256 checksum and replaces the program
files. Each release also lists the checksum, so you can check a manual download:

```
Get-FileHash .\DayZViewer-<version>-win-x64.zip -Algorithm SHA256
```

## Feedback

Bugs and ideas: open an [issue](../../issues) or find us on the RwG Discord. Guides and tools: [rwg-addon.com](https://rwg-addon.com/).

## License

Free to use for DayZ modding, personal and commercial projects. Not for sale and not to be redistributed or
re-uploaded elsewhere — link to this page instead. No warranty. © Redwater-Gaming (RwG).
DayZ is a trademark of Bohemia Interactive; this tool is not affiliated with or endorsed by Bohemia Interactive.
