<img src="logo-400.png" alt="AI Rechtshulp logo" width="96" height="96">

# AI Rechtshulp MCP server

**Search Dutch and EU case law with ECLI sources and verify quotes against the judgment.**

Remote MCP server: `https://app.ai-rechtshulp.nl/mcp` (Streamable HTTP) · Website: [ai-rechtshulp.nl](https://ai-rechtshulp.nl/)

## What it does

AI Rechtshulp searches published Dutch case law (rechtspraak.nl) and EU case law and returns source passages with their ECLI reference. It can check whether a quote really appears in a judgment, which helps against made-up citations. With an account you save sources, build dossiers, write research memos and scan a contract for risky clauses.

A found source or quote is not a legal conclusion. The tools return sources, not legal advice.

## Connect

- **Server URL:** `https://app.ai-rechtshulp.nl/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** OAuth with PKCE (S256), dynamic client registration and client ID metadata documents, so MCP clients connect without manual setup. Without an account the server answers a fixed demo only.

**Claude (claude.ai, Desktop):** Settings → Connectors → Add custom connector → paste the server URL.

**Claude Code:**

```bash
claude mcp add --transport http ai-rechtshulp https://app.ai-rechtshulp.nl/mcp
```

**Cursor, VS Code, Cline, Windsurf and other clients** (`mcp.json` / `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "ai-rechtshulp": {
      "type": "http",
      "url": "https://app.ai-rechtshulp.nl/mcp"
    }
  }
}
```

Cline uses `"type": "streamableHttp"`; see [llms-install.md](llms-install.md).

## Tools

| Tool | What it does |
|---|---|
| `search / fetch` | Search case law; fetch a judgment by ECLI. |
| `check_source` | Verify that a quote appears in a judgment. |
| `save_source / list_saved / make_memo` | Save sources and write a research memo. |
| `scan_contract / stress_test` | Research a supplied text such as a contract or an argument against sources (account, with consent). |
| `list_dossiers / create_dossier / read_dossier / save_research` | Dossiers in your account (paid). |
| `account` | Plan and source budget. |

## Example prompts

- Find Dutch rulings on dismissal during sick leave since 2023.
- Does this quote really appear in ECLI:NL:HR:2019:1734?
- Which court decisions are relevant to this clause in my rental contract?

## Links

- Website: https://ai-rechtshulp.nl/
- Documentation: https://app.ai-rechtshulp.nl/plugin/
- Privacy policy: https://ai-rechtshulp.nl/privacy/
- Terms: https://ai-rechtshulp.nl/voorwaarden/

## Keywords

Dutch case law search, ECLI, legal research AI, EU case law, citation check, contract scan, rechtspraak.

Nederlands: jurisprudentie zoeken, rechtspraak zoeken, ECLI, uitspraken zoeken, juridisch onderzoek, contract controleren, rechtshulp AI.

## More MCP servers by Samautomation

- [Scamchecker.nl](https://scamchecker.nl/): Check a suspicious email, SMS, WhatsApp message or link for scam signals (Netherlands, Belgium). ([listing](https://github.com/smrht/scamchecker-mcp))
- [Klussenbeheer](https://samdesk.nl/klussenbeheer/): Job management for Dutch service companies: jobs, customers, planning, quotes and invoices. ([listing](https://github.com/smrht/klussenbeheer-mcp))
- [Muziek maken met AI](https://muziekmakenmetai.nl/): Make an original song from a prompt or your own lyrics. Two versions per song, MP3 download. ([listing](https://github.com/smrht/muziekmakenmetai-mcp))
- [Beheer je WP](https://beheerjewp.nl/): Manage a WordPress site from your AI assistant: read, search, propose edits, Search Console data. ([listing](https://github.com/smrht/beheerjewp-mcp))
- [UlazAI Media](https://ulazai.com/): Create private AI images with your UlazAI account: pick a model, confirm, generate, download. ([listing](https://github.com/smrht/ulazai-mcp))
- [Backlinkswinkel](https://backlinkswinkel.nl/): Search Dutch websites for backlinks, check metrics and prices, order after confirmation, track. ([listing](https://github.com/smrht/backlinkswinkel-mcp))
- [Backlinksbeheer](https://backlinksbeheer.nl/): Read your stored backlinks, link checks and lost-link alerts per domain. Read-only. ([listing](https://github.com/smrht/backlinksbeheer-mcp))
- [Samautomation Video](https://samautomation.work/): Render an MP4 from your own images, clips, voice-over and timed captions. JSON to video. ([listing](https://github.com/smrht/samautomation-video-mcp))
- [PDF Samenvoegen](https://pdfsamenvoegen.nl/): Merge your own PDFs in a confirmed order and get one downloadable PDF. ([listing](https://github.com/smrht/pdfsamenvoegen-mcp))
- [Diamond Painting Converter](https://diamondpaintingconverter.com/): Find your purchased diamond painting patterns and download the PDF with DMC colour legend. ([listing](https://github.com/smrht/diamondpaintingconverter-mcp))
- [Nummerschilderen.com shop advisor](https://nummerschilderen.com/): Search paint-by-number kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/nummerschilderen-mcp))
- [DiamondPaintingWinkel.nl shop advisor](https://diamondpaintingwinkel.nl/): Search diamond painting kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/diamondpaintingwinkel-mcp))
- [SamDesk Support](https://samdesk.nl/support/plugin/): Read your SamDesk support inbox, find customer agreements and draft replies. Read-only. ([listing](https://github.com/smrht/samdesk-support-mcp))

## Publisher

Samautomation, Wognum, the Netherlands · https://samautomation.work

This repository holds the public listing (README, `server.json`, install notes). The server itself is hosted by the publisher; there is nothing to install or build.
