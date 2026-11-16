# 🛡️ OFAC, UN & EU Sanctions + GLEIF LEI Vendor KYB Gate

[![Marketplace Release](https://img.shields.io/github/v/release/jesleytassili-glitch/ofac-sanctions-kyb-action?color=brightgreen&label=Marketplace%20Release)](https://github.com/jesleytassili-glitch/ofac-sanctions-kyb-action/releases/tag/v1.0.1)
[![Official MCP Registry](https://img.shields.io/badge/Official_MCP_Registry-io.github.jesleytassili--glitch-6366F1)](https://registry.modelcontextprotocol.io/v0/servers?search=io.github.jesleytassili-glitch)
[![RapidAPI Hub](https://img.shields.io/badge/RapidAPI-@b2bquantapis-0055FF)](https://rapidapi.com/b2bquantapis/api/global-sanctions-pep-interpol-watchlist-screener)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)

Automated CI/CD supplier onboarding gate for OFAC SDN, UN, EU sanctions screening and GLEIF LEI corporate ownership KYB.

## 🚀 Quick Start (`.github/workflows/compliance.yml`)

```yaml
name: Automated Compliance Audit
on:
  pull_request:
  schedule:
    - cron: '0 7 * * 1'

jobs:
  audit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run OFAC, UN & EU Sanctions + GLEIF LEI Vendor KYB Gate
        uses: jesleytassili-glitch/ofac-sanctions-kyb-action@v1
        with:
          mode: 'sanctions-screen'
          targets: 'Acme Global Trading Ltd,Siemens AG'
          rapidapi_key: ${{ secrets.RAPIDAPI_KEY }}
```

## 📊 Available Audit Modes

- `sanctions-screen` — OFAC, UN, EU & PEP Watchlist Screening ([RapidAPI](https://rapidapi.com/b2bquantapis/api/global-sanctions-pep-interpol-watchlist-screener) | [Apify](https://apify.com/b2b-quant-apis/global-sanctions-pep-interpol-watchlist-screener))
- `gleif-lei-kyb` — GLEIF LEI Corporate Ownership & Parent KYB ([RapidAPI](https://rapidapi.com/b2bquantapis/api/global-gleif-lei-corporate-ownership-kyb) | [Apify](https://apify.com/b2b-quant-apis/global-gleif-lei-corporate-ownership-kyb))

## 📦 Programmatic SDKs & Local MCP Server

- **Python SDK (PyPI):** `pip install b2b-compliance-sdk`
- **Node.js / Claude / Cursor MCP (`stdio`):** `npx -y b2b-compliance-mcp-cli`

<!-- PSEO_DOCS_PORTAL_V48 -->
## 📚 Live Documentation & API Reference (pSEO Portal v4.8)

Official developer documentation, interactive OpenAPI 3.0.3 specifications, and ready-to-use SDK code samples:

- 🌐 **[Central API Documentation Portal](https://jesleytassili-glitch.github.io/docs/index.html)** — Directory of 31 institutional REST & MCP endpoints.
- 🤖 **[LLM & AI Agent Discovery (`llms.txt`)](https://jesleytassili-glitch.github.io/llms.txt)** — Structured GEO index for Claude Code, Cursor & Autonomous Agents.
- 🚀 **[OFAC SDN, EU/UN Sanctions & PEP Watchdog API](https://jesleytassili-glitch.github.io/docs/global-sanctions-pep-interpol-watchlist-screener.html)** — Interactive Schema & Code Snippets ([Markdown](https://jesleytassili-glitch.github.io/docs/global-sanctions-pep-interpol-watchlist-screener.md))
- 🚀 **[Global GLEIF LEI Corporate Ownership KYB API](https://jesleytassili-glitch.github.io/docs/global-gleif-lei-corporate-ownership-kyb.html)** — Interactive Schema & Code Snippets ([Markdown](https://jesleytassili-glitch.github.io/docs/global-gleif-lei-corporate-ownership-kyb.md))

*High-availability SLA hosted on GitHub Pages with enterprise distribution across RapidAPI, Zyla API Hub, and Apify Store.*
<!-- /PSEO_DOCS_PORTAL_V48 -->
