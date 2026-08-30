<!-- lorewound:standard:start -->
# Playnite Series Cleaner

<div align="center">
  <img src="src/icon.png" alt="Playnite Series Cleaner logo" width="128" />
  <p><strong>Playnite series metadata cleanup extension</strong></p>
  <p>Created by Gazi Enes Sedef · Published by Lorewound</p>

  ![Status](https://img.shields.io/badge/status-active-111827?style=flat-square)
  ![Publisher](https://img.shields.io/badge/publisher-Lorewound-111827?style=flat-square)
</div>

## ◈ Overview

Playnite Series Cleaner is a Windows-focused extension for normalizing and cleaning series metadata inside Playnite libraries. It reduces repetitive library maintenance while remaining compatible with Playnite's extension model.

## ✦ Highlights

- Series metadata normalization
- Playnite library integration
- Windows desktop workflow

## ⬡ Technology

- .NET / WPF

## ▣ Platforms

- Windows with Playnite

## ▶ Getting Started

```text
Review the project-specific detailed documentation below
```

Use the versions recorded in the repository lockfiles and manifests. Secrets belong in ignored local environment files or the deployment platform's secret store; never place credentials in client code or commits.

## ✓ Quality and Maintenance

- Maintenance policy: [MAINTENANCE.md](MAINTENANCE.md)
- Shared legal documentation: [Lorewound Legal Docs](https://github.com/katsopolis/Legal-Docs)
- Repository: [https://github.com/katsopolis/Playnite-SeriesCleaner](https://github.com/katsopolis/Playnite-SeriesCleaner)

## ◇ Ownership and Publishing

| Role | Details |
| --- | --- |
| Creator and producer | Gazi Enes Sedef |
| Publisher | Lorewound |
| Contact | [support@lorewound.com](mailto:support@lorewound.com) |
| Repository owner | [katsopolis](https://github.com/katsopolis) |

## ⚖ License

This project is proprietary and is not open source. No use, execution, copying, modification, distribution, hosting, or commercial exploitation is permitted without prior written permission. See [LICENSE](LICENSE). Third-party components and assets remain subject to their respective licenses.
<!-- lorewound:standard:end -->

---

## ◆ Detailed Project Guide

The maintained project summary above is canonical. The original detailed documentation is preserved below for implementation-specific guidance.

![Series Cleaner Icon](sources/icon.png)

## 🚀 What's this extension?

A simple Playnite extension that cleans your library by removing series metadata from games which are the only entry in their series.

## 🛠️ How does it work?

- It scans your library and identifies series containing only a single game.
- Offers to remove these series entries from the database to declutter your metadata.

## 📥 Installation

1. Download the latest release from the [Releases](https://github.com/katsopolis/Playnite-SeriesCleaner/releases) page.
2. Extract the `SeriesCleaner` folder to: `%AppData%\Playnite\Extensions\SeriesCleaner\`
3. Restart Playnite, and you'll find the extension under `Extensions > Series Cleaner`.

## 🎯 How to Use

- Open `Extensions > Series Cleaner` from the main menu.
- Click `Clean Single-Game Series`.
- Confirm the removal of detected series.

## 🖼️ SS's

![Alt text](images/screenshot1.png?raw=true "From Main Menu")
![Alt text](images/screenshot2.png?raw=true "After Clicking")

## 🔨 Building from Source

1. Clone this repository
2. Open `Playnite-SeriesCleaner.sln` in Visual Studio
3. Build the solution (the output will be in the `sources` folder)
4. Copy the `sources` folder to `%AppData%\Playnite\Extensions\SeriesCleaner\`

## ⚠️ Disclaimer

**Always backup your Playnite database before using.**  
The author is not responsible for accidental loss of metadata.

## ❓ FAQ

**Q:** Some series still appear even though they're single entries?  
**A:** This may occur if multiple series have identical names but different database IDs. You should manually merge them in Playnite by editing each game's Series field.

## 📃 License

This project is proprietary and is not open source. No use, execution, copying, modification, distribution, hosting, or commercial exploitation is permitted without prior written permission. See [LICENSE](LICENSE). Third-party components and assets remain subject to their respective licenses.

## Operational documentation

[Security policy](SECURITY.md)
