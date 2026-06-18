**Core archive size**: 1.47TB (ZStandard)  
**Supplementary archive size**: 259GB (ZStandard)  
update cadence: when new content is released and tested  

*Curated by Eggman.*

Welcome to the mega-mighty **TeknoParrot Collection** — a cleaned, organized, collector-focused RomVault set built around the TeknoParrot ecosystem. This project exists to take arcade game dumps and turn them into something more consistent, more manageable, and a lot less irritating to maintain and utilize.

<img width="1536" height="1024" alt="TeknoParrot Collection1" src="https://github.com/user-attachments/assets/fe8ef080-5b1e-4b05-8ebf-658ac22a265a" />

## Table of Contents

- [What Is TeknoParrot?](#what-is-teknoparrot)
- [Project Overview](#project-overview)
- [What This Collection Is Trying to Do](#what-this-collection-is-trying-to-do)
- [Why There Are Two DATs](#why-there-are-two-dats)
- [Why RomVault Only?](#why-romvault-only)
- [About TPUI's ROM Scanner](#about-tpuis-rom-scanner)
- [How to Store Your Games](#how-to-store-your-games)
- [Rebuilding Tips for Nested ZIPs](#rebuilding-tips-for-nested-zips)
- [Antivirus False Positives](#antivirus-false-positives)
- [Why Other Versions May Be Missing](#why-other-versions-may-be-missing)
- [Game Not Working?](#game-not-working)
- [Intel, AMD, or NVIDIA?](#intel-amd-or-nvidia)
- [BepInEx and Other Modding Frameworks](#bepinex-and-other-modding-frameworks)
- [FPS Frame Limiting](#fps-frame-limiting)
- [Why Some Games Need Admin Mode](#why-some-games-need-admin-mode)
- [Testing and Cleaning Standards](#testing-and-cleaning-standards)
- [File Naming Standard](#file-naming-standard)
- [Additional Resources](#additional-resources)
- [Where to Find Content](#where-to-find-content)
- [Are You a TP Dev?](#are-you-a-tp-dev)
- [I Do This for Fun, Not for Profit](#i-do-this-for-fun-not-for-profit)
- [Licensing](#licensing)
- [Support](#support)

---

<a id="what-is-teknoparrot"></a>

## What Is TeknoParrot?

**TeknoParrot** (also known as **TeknoParrot User Interface** or simply **TPUI**) is a software application that allows users to play original **arcade games** on their personal computers. It provides compatibility for a wide range of arcade hardware, making it possible to run games originally designed for dedicated arcade systems.

TeknoParrot supports many platforms, including major families from:

- **Namco** — ES1, ES3, ES3A, ES3B, ES3X, ES4, N2, BNA1, BNA1 LITE, BNA1-ES4, System 147, 246, 256, 357
- **Sega** — ALLS, Amusements, Europa-R, Lindbergh Red/Red EX/Yellow, Nu, Nu 1.1, RingEdge, RingEdge 2, RingWide, Triforce
- **Taito** — NESICAxLive, NESiCAxLive 2, Type X, Type Zero, Type X+, Type X2, Type X3, Type X4
- **Konami**
- **Global VR**
- **Raw Thrills**
- **Incredible Technologies**

And plenty more besides:

ICE/ICE-RT, Team Play, Triotech, Chicago Gaming Company, Coastal, Covielsa, D-Gate, EXAMU eX-BOARD, Em-Teck, Gaelco, GameWax, Interactive Light, Midway, PAOKAI, Phantom, Ritual Entertainment/Activision, Tsunami, UDC, UNIS, Uniana, WAHLAP, Adrenaline, Cave, Cecropia, and others.

Players can configure game settings, map controls to keyboard, controller, or even force feedback wheels, and in some cases use network play to recreate more of the original arcade experience on PC. It is especially popular with people who enjoy preserving and playing arcade titles that were never properly released for home use.

Quite a few games in TPUI are free to play, but newer games may require an active monthly subscription. That helps fund ongoing development and support. These kinds of devs do not work for free, y'all.

> **Always run the latest TPUI version available.** Before troubleshooting any game, use the hamburger menu in the top-left of TPUI to **Check for Updates**, then **Install Updates** if needed. Update first, retest second, ask for help third.

---

<a id="project-overview"></a>

## Project Overview

This project aims to **clean up, organize, standardize, and maintain arcade game dumps** used with the TeknoParrot loader.

Public game dumps (unpacked drive images) often arrive with all kinds of baggage attached from the underground arcade scene, including:

- operating system or platform leftovers
- older loaders and launcher junk
- mods and other assisting utilities
- temporary files and runtime-generated files
- unrelated scripts and support tools
- orphaned folders from previous repacks

The goal here is to remove the clutter and produce something more useful for collectors:

- cleaner folder structures
- more consistent naming
- more predictable file layouts
- easier integrity checking
- easier long-term maintenance inside RomVault

> This project is still a work in progress and will likely be for a long time. The goal is eventual perfection. The reality is that refinement happens over time, one cleanup pass at a time.

---

<a id="what-this-collection-is-trying-to-do"></a>

## What This Collection Is Trying to Do

This is not just a random pile of TeknoParrot game folders.

The broader aim is to keep one curated collection that is:

- practical for collectors to store and manage
- consistent enough for reliable scanning and rebuilding
- cleaned up enough that you are not dragging around years of junk from old repacks
- named sensibly enough that the files make sense at a glance

Whenever possible, the collection is shaped toward what most people actually want:

- one good main release per supported game
- cleaned folders
- reduced junk
- clear naming
- notes where weirdness matters

It is a collector set, not a museum of every random broken repack that ever floated around the internet.

---

<a id="why-there-are-two-dats"></a>

## Why There Are Two DATs

Earlier in the life of this project, there was one big datfile with everything thrown into it. That worked for a while, but over time it became bloated.

The original idea behind splitting things was simple:

- keep the **main TeknoParrot dat** focused on one primary release per supported game in TPUI
- push everything else into a **supplementary dat**

That supplementary material included things like:

- language translation mods
- supported minor game revisions that are older than the latest version in the core dat
- alternate music variants
- unsupported but useful enhancements
- setup guides to assist users in setting up certain platforms
- landscape hacks for portrait games
- larger compatibility mods needed for modern operating systems

For example, games such as **Gaia Attack 4** and **Haunted Museum II** needed major video conversion work for modern Windows systems because their original proprietary video formats were no longer practical. Those conversions worked, but they massively increased file sizes and were really mods, not original content.

### So what now?

The main philosophy remains the same:

- the core set should stay practical
- extra or non-standard material should be clearly treated as extra material
- one supported, sensible main release per game is still the preferred approach

---

<a id="why-romvault-only"></a>

## Why RomVault Only?

This is a **RomVault-only DAT**.

That is not me being dramatic. It is because many games in this collection contain things that other ROM managers do not handle correctly, especially:

- **zero-byte files**
- **empty folders**
- unusual folder structures
- content layouts that do not behave nicely in other managers

RomVault is the ROM manager this collection was built around for scanning, rebuilding, and general collection management.

Other ROM managers such as:

- ClrMamePro
- Romulus
- RomCenter

are not designed around the way these game folders are structured, so they are not a proper fit here.

If you want to manage this collection correctly, use RomVault.

Also, a small number of games contain **nested ZIP archives** that must remain zipped for the game to function. I cannot change that. It is what it is.

> **Do not ask for RomVault support in the TeknoParrot Discord.** If your question is about RomVault, take it to the RomVault community.

---

<a id="about-tpuis-rom-scanner"></a>

## About TPUI's ROM Scanner

The TeknoParrot developers chose to use this DAT file as a reference point for their internal **ROM Scanner** feature in TPUI.

I added metadata fields needed to make it compatible with their scanner, but I had **no involvement** in:

- how the scanner was coded
- how it behaves
- how reliable it is
- what it does or does not detect
- limitation of only supporting one dat

If the scanner fails to detect your game correctly, that is a **TeknoParrot-side** issue, not a collection-side issue.

If your files and folders match the DAT exactly, the scanner *should* recognize them more reliably, but that still depends on how TPUI itself behaves.

> **Do not post GitHub issues here about getting a specific game to run.** This repository is for the DAT, notes, and related material. For setup or game support, use the official TeknoParrot Discord.

---

<a id="how-to-store-your-games"></a>

## How to Store Your Games

In RomVault, you can store the collection in several archive formats:

- **Zip (TorrentZip)**
- **7z (LZMA)**
- **ZStandard** in ZIP or 7z form

The short version:

- **Use ZStandard** if you want fast extraction and more practical day-to-day use
- **Use TorrentZip** if you want the safest common-denominator choice
- **Avoid 7z/LZMA** unless you enjoy watching your machine age in real time

### Example comparison

One example game in the collection contains **1381 folders** and **4853 files**.

- **Original size:** 1,777,325,102 bytes (1.66 GB)

| Final Size | MB | Compress Speed | Extract Speed | Format |
|---|---:|---|---|---|
| 929,942,678 | 887 MB | normal | slow | Zip-Torrent |
| 805,497,880 | 768 MB | slow | very slow | 7Z-LZMA |
| 631,563,006 | 602 MB | slow | ultra slow | 7Z-LZMA-Solid |
| 868,626,724 | 828 MB | faster | very fast | Zip-ZSTD |
| 867,793,906 | 828 MB | fast | very fast | 7Z-ZSTD |
| 729,269,298 | 695 MB | fast | very fast | 7Z-ZSTD-Solid |

### Practical advice

**TorrentZip** creates deterministic ZIP archives that match between users when packed the same way. That is useful for sharing, comparison, and consistency.

**ZStandard** also gives excellent speed, slightly better compression than TorrentZip in many cases, and much faster extraction than LZMA. It is the better practical choice if your toolchain supports it.

**7z/LZMA** is not recommended for an actively maintained collection. Yes, it compresses well. No, you will not enjoy updating or extracting it later.

If you are not going to read the full write-up and just want the quick answer: **use TorrentZip or ZStandard, and do not fall into the 7z trap**.

### Converting archive formats

If your collection is already stored as TorrentZip and you want to move to ZStandard, RomVault includes **Structured Archive Maker (SAMUI)** in the Help menu.

That tool can convert archives in parallel using multiple worker threads. Doing the same conversion through normal RomVault archive-type changes is much slower because RomVault processes files one at a time.

A few practical notes:

- more worker threads means more I/O pressure
- spinning disks do better with fewer threads
- SSD and NVMe storage can handle more aggression
- long conversion jobs will heat up SSDs and NVMes, so keep cooling in mind

And remember:

> **TeknoParrot only uses games in an uncompressed state.** Archives are for storage, movement, backup, and collection management.

---

<a id="rebuilding-tips-for-nested-zips"></a>

## Rebuilding Tips for Nested ZIPs

Some games contain ZIP files inside the game folder as part of the game’s original structure.

By default, RomVault treats ZIP files as archives and scans the **contents inside** them. In a few cases, what you actually need is for RomVault to treat the ZIP as a normal file.

### Workarounds

- rename the nested archive suffix temporarily, for example from `.zip` to `.zip_`
- or place those ZIPs into a **FileOnly ToSort** location so RomVault rebuilds them as files

That gets around the issue cleanly enough.

RomVault also supports a **Mixed (archive as file)** mode, but that is not a good fit here because it effectively forces the collection into a fully uncompressed workflow, and this set is far too large for that to be a pleasant long-term choice.

---

<a id="antivirus-false-positives"></a>

## Antivirus False Positives

Some TeknoParrot games rely on modified executable files or other patched core files to work around things like:

- copy protection
- resolution handling
- input handling
- compatibility issues
- platform-specific oddities

That means some games may trigger **false positives** in antivirus software.

In plain English: a handful of patched executables look suspicious to AV software, even when the files are there purely to make the game run.

None of the TP games in this curated collection are intended to be malicious, but I also cannot control where you got your files from. Use common sense when handling unknown files from the internet.

**Do not globally disable your antivirus on a machine you care about.**

Instead, set folder exclusions for:

- your TeknoParrot games folder
- your RomVault download folder
- your temp/cache folders
- your ToSort folder

Common executables that may false-positive include:

- *Daytona Championship USA* [Sega PC]
- *Exception* [Taito NESiCAxLive]
- *Luigi's Mansion Arcade* [SEGA Nu 1.1]
- *Raiden III (2005)* [Taito Type X]
- *Raiden IV (2007)* [Taito Type X]

If you do not set proper exclusions, do not be shocked when your antivirus eats game files and wrecks your setup.

---

<a id="why-other-versions-may-be-missing"></a>

## Why Other Versions May Be Missing

A game existing on the internet does **not** automatically make it a supported TeknoParrot game.

Many arcade titles need custom work before they can run in TPUI, such as:

- executable patching
- disassembly and reverse engineering
- DLL hooks
- plugins
- loaders
- other game-specific fixes

If you try to launch an unsupported version, you will often get an **unsupported CRC** error or just a dead launch.

Also, from an arcade operator’s point of view, a newer version does not always mean more content. Many updates are simply:

- hardware bug fixes
- OS-level fixes
- operator-side maintenance revisions
- minor changes with no meaningful player-facing content

The TeknoParrot developers usually support the version that gives the best practical result for users, not necessarily every version ever released.

When a game version becomes officially supported by the TP team, it can be brought into the collection.

---

<a id="game-not-working"></a>

## Game Not Working?

Usually, this is a **you problem** before it is a collection problem.

Common causes include:

- the game was not configured correctly in TPUI
- you are using the wrong resolution
- you are using unsupported GPU hardware
- an old third-party loader or patch is interfering
- required service mode settings were never configured
- TPUI changed and something that used to work no longer behaves the same way

The TP developers do their best to support NVIDIA, AMD, and Intel hardware, but that does not mean every game behaves the same across all GPUs.

Some games are heavily vendor-dependent. A good example is **Incredible Technologies** material, which is only designed to run on NVIDIA GPU hardware.

If you want the best overall compatibility across the collection, **use NVIDIA**.

If a game is officially supported and still gives you trouble after you have:

1. updated TPUI
2. checked your game setup
3. confirmed your GPU is supported
4. removed conflicting junk files

then ask for help in the proper TeknoParrot Discord channel.

---

<a id="intel-amd-or-nvidia"></a>

## Intel, AMD, or NVIDIA GPU?

### Intel
Intel graphics should generally be treated as a last-resort option. Newer Intel GPUs may do better than older ones, but overall compatibility is limited and a good chunk of games simply will not behave.

### AMD
I do not personally test on AMD GPUs, so I am going by user reports here. AMD users usually have more work to do, and some games may never behave properly at all. Some older games may require AMD graphics patches.

### NVIDIA
NVIDIA is the clear winner for TeknoParrot compatibility. If you are serious about getting the widest range of games running with the least pain, use NVIDIA.

### CPU choice
CPU vendor matters much less than GPU vendor. In general, Intel and AMD CPUs are both fine. A few games may dislike specific Intel generations, but that is the exception rather than the rule.

---

<a id="bepinex-and-other-modding-frameworks"></a>

## BepInEx and Other Modding Frameworks

Some Unity-based games in the collection include a **BepInEx** folder.

BepInEx is a patcher and plugin framework for Unity and .NET games. It lets the devs inject custom code and patch assemblies in memory where needed.

When running a BepInEx-based game for the first time, you will often need to **start and restart the game twice** so the framework can finish configuring itself.

Example games in the collection that use BepInEx include:

- *Night Hunter After Dark Chapter II*
- *Wild West Shootout*
- *Chase Chase Joker*
- *Need for Speed Heat TakeDown*
- *Family Guy Bowling*

### Safe reset

You can safely reset BepInEx by deleting:

- `BepInEx\cache`
- `BepInEx\config`

Do **not** delete:

- `BepInEx\core`
- `BepInEx\plugins`
- `.doorstop_version`
- `doorstop_config.ini`
- `winhttp.dll`

### Updating plugins

If you have an updated plugin DLL, place it in:

`BepInEx\plugins`

and replace the previous version.

### Updating BepInEx itself

You can update BepInEx by replacing its files with the latest **stable x64** release.

Rules:

- use the most recent stable **x64** build
- do **not** use beta releases
- do **not** use x86 builds
- to grab the latest release, visit the [Bepinex github](https://github.com/BepInEx/BepInEx)
---

<a id="fps-frame-limiting"></a>

## FPS Frame Limiting

Some games can run too fast or otherwise behave badly if left uncapped.

When that happens, use a frame limiter such as **RivaTuner Statistics Server** and cap the game to **60 FPS**, or use your GPU software if it provides a frame limiting option.

If a game is running like it got into the good cocaine, this is one of the first things to check.

---

<a id="why-some-games-need-admin-mode"></a>

## Why Some Games Need Admin Mode

Some games require TPUI to be run with elevated privileges.

If TPUI complains that it needs administrator rights:

1. close TPUI
2. right-click the TPUI executable
3. choose **Run as administrator**

Nothing mysterious there.

---

<a id="testing-and-cleaning-standards"></a>

## Testing and Cleaning Standards

### Hardware used for testing

- Intel Core i7-13700
- 64 GB RAM
- NVMe local storage
- NVIDIA T1000 8 GB
- Windows 11 Pro

**Every single game has been tested, including subscriber-only games.**

### General testing approach

- game paths are kept short where practical, for example: `D:\TPGames-testing\<game folder>`
- games are tested in fullscreen mode whenever possible
- unnecessary third-party loaders and patches are removed unless TPUI genuinely needs them
- required general fixes may be kept if they are necessary for the game to function
- crosshairs are included where supported
- bezels are generally not supplied unless they are especially useful, such as for portrait games
- service-mode files may be preconfigured if a game needs awkward internal settings to become usable
- testing normally includes reaching attract mode and verifying at least some in-game play

### Cleaning philosophy

Many of these dumps came from the internet and were passed around repeatedly before landing here. That usually means they arrive with years of extra nonsense attached.

I do my best to clean the folders back toward a fresher, more original state. When possible, I compare against fuller drive dumps to make that process more accurate.

It can take multiple iterations of the dat before a newly added game is fully cleaned up.

### Typical cleanup work

- remove orphaned files and folders from previous loader setups
- remove other loaders and their support files
- remove obvious original-hardware system leftovers where safe
- remove random junk files and folders not needed for the game
- remove obvious log files, while leaving required `.log` data files intact
- use ReShade where needed for portrait-to-landscape presentation with bezel support
- include custom crosshairs where the game supports them
- remove files such as:
  - `teknoparrot.ini`
  - `steam_appid.txt`
  - `thumbs.db`
  - macOS junk files

---

<a id="file-naming-standard"></a>

## File Naming Standard

The collection uses the following filename format:

`<game title> (version)(YYYY-MM-DD)(Region)[Platform][TP]`

### Meaning of each part

**`<game title>`**  
Uses the title as listed by the game developer when known. Original casing is preserved where appropriate. If the intended casing is unclear, normal English title case is used.

**`(version)`**  
Included when known. The leading `v` is removed because it is implied.

**`(YYYY-MM-DD)`**  
Used when the full release date is known. If only the year is known, only the year may be used.

**`(Region)`**  
Standard region notation when known. A game being in English does not automatically mean it is a USA release.

**`[Platform]`**  
The game’s arcade system platform.

**`[TP]`**  
Used to visually identify the games came from the TeknoParrot Collection. There are other collections I curate that may also have the same or very similar games/versions with the same type of file naming.  This hopefully avoids accidental crossover when users are extracting games across different loader platforms.

---

<a id="additional-resources"></a>

## Additional Resources

If you are looking for the **Incredible Technologies Super Easy Universal Setup Guide**, it lives here:

- **tp-it-guides** repository on GitHub

---

<a id="where-to-find-content"></a>

## Where to Find Content

There are community-created torrents and archival sources floating around in the usual places.

This README is not intended to be a sourcing manual. Use your own judgment, be careful with unknown files, and do your own homework.

---

<a id="are-you-a-tp-dev"></a>

## Are You a TP Dev?

No.

I am not associated with TeknoParrot, its admins, or its developers. I am just a collector who wanted my own curated TeknoParrot set.

---

<a id="i-do-this-for-fun-not-for-profit"></a>

## I Do This for Fun, Not for Profit

If you paid some back-alley drive seller for this dat or for a set built from it, then congratulations — you got hustled.

This project exists because I enjoy doing the work. Don't be a dick by blatantly paying someone else for my efforts.

---

<a id="licensing"></a>

## Licensing

Original source code, scripts, tooling, and hand-authored documentation and
metadata in this repository are licensed under the MIT License.

Archived game data, binaries, firmware, media assets, and other third-party
materials are **not** covered by the MIT License and remain the property of
their respective copyright holders.

See the `LICENSE` and `NOTICE` files for full details and scope clarification.

---

<a id="support"></a>

## Support

If these tools, dats, notes, or archives save you time, consider supporting the work.

<a href="https://buymeacoffee.com/eggmansworld">
  <img src="https://cdn.buymeacoffee.com/buttons/v2/default-orange.png" height="45" alt="Buy Me a Coffee">
</a>
