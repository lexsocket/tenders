# Tenders — LexSocket.ai Plugin for Claude Code

Search, analyze, and monitor European public tenders and EU legislation directly from Claude Code.

## What it does

This plugin connects Claude Code to three LexSocket.ai data sources via MCP:

| Connector | Coverage | Description |
|-----------|----------|-------------|
| **TED** | All EU/EEA | Above-threshold tenders from Tenders Electronic Daily |
| **National Tenders** | 18 countries | Below-threshold tenders from national platforms |
| **EUR-Lex** | EU | Directives, regulations, and case law |

### National Tenders coverage

FR, GB, DE, ES, IT, NL, IE, PT, DK, PL, AT, CH, BE, NO, CZ, HU, RO, HR — sourced from BOAMP, Contracts Finder, oeffentlichevergabe.de, PLACSP, ANAC, TenderNed, eTenders, BASE, udbud.dk, ezamowienia.gov.pl, ausschreibungen.usp.gv.at, simap.ch, e-Procurement, Doffin, NEN, EKR, SEAP, EOJN.

### What you can do

- Search tenders by keyword, CPV code, NUTS region, country, value range, or deadline
- Use hybrid (full-text + semantic) search — works in any language
- Browse upcoming deadlines and find open opportunities
- Find similar tenders to one you already identified
- Search by buyer/contracting authority name
- Look up EU legal documents related to procurement

## Prerequisites

1. **Register** a free account at [lexsocket.ai](https://lexsocket.ai)
2. **Claude Code** version 1.0.33 or later

## Installation

### From a marketplace

```bash
claude plugin install tenders
```

### Local (for development/testing)

```bash
claude --plugin-dir ./lexsocket-plugin
```

## Authentication

After installing the plugin, authenticate with your LexSocket.ai account:

1. Open Claude Code
2. Run `/mcp`
3. Select a LexSocket server and click **Authenticate**
4. Complete the OAuth2 login in your browser

Authentication tokens are stored securely and refreshed automatically.

## Usage

### Get started

```
/tenders:hello
```

### Example queries

```
Find open IT tenders in France above 100,000 EUR
```

```
What green procurement opportunities are available in Spain this month?
```

```
Search for construction tenders near Berlin
```

```
Show me the latest EU directive on public procurement
```

```
Find tenders similar to this one from the Dutch government
```

## Plugin structure

```
lexsocket-plugin/
├── .claude-plugin/
│   └── plugin.json        # Plugin manifest
├── .mcp.json              # MCP server definitions (TED, National Tenders, EUR-Lex)
├── skills/
│   └── hello/
│       └── SKILL.md       # Onboarding skill
└── README.md
```

## Support

- Website: [lexsocket.ai](https://lexsocket.ai)
- Email: support@lexsocket.ai

## License

Proprietary — (c) LexSocket.ai. All rights reserved.
