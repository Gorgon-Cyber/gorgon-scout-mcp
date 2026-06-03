# Gorgon Scout MCP server

Run AI-driven web-application and API security scans from Claude, or any MCP agent.

**Gorgon Scout** is a Windows application security scanner (DAST). This is its
**Model Context Protocol (MCP) server**, which lets your AI assistant drive the whole
workflow in plain language: ask it to scan a web app or API you are authorised to test,
and it records the target, runs the scan, streams progress and findings, and produces a
Word report with optional AI analysis.

> Works with the **free** plan of Claude Desktop.

## What it does

Point your assistant at a target and say *"scan this."* The connector exposes Scout as
typed MCP tools, so the agent can:

- create and manage **target profiles**
- **AI auto-record** a site (a Chromium window crawls the app and collects the login)
- import an **OpenAPI / Postman / HAR** spec for API testing
- start a scan and **poll progress and findings** as structured results
- run **AI post-scan analysis** for deeper, validated dives

Every scan still requires you to confirm the in-scope hostname. Your account credentials
are never sent to the model.

## Highlights

- **Nothing to configure.** Capture happens at the network layer: no proxy, no PAC files,
  no per-browser certificate ritual.
- **Every HTTP version.** Intercepts HTTP/1.1, HTTP/2, and **HTTP/3 (QUIC)**, which still
  defeats most interception proxies.
- **Signal over noise.** Field-aware probes, gated by parameter type and authorisation
  tier. The probe library is cryptographically signed and refreshes daily against
  OWASP and CVE intelligence.

## Requirements

- **Windows 10 or 11 (x64).** This connector is Windows-only.
- The **Gorgon Scout** desktop app installed. The installer registers this connector with
  Claude Desktop for you. Download: https://gorgoncyber.com/scout-download.html
- A **Gorgon Cyber account**: free 30-day trial (up to 2 targets), then USD 20/month.

This is a **proprietary** connector to a commercial app. It is **not** a standalone
open-source MCP server.

## Install

1. Download and run the Gorgon Scout installer:
   https://gorgoncyber.com/scout-download.html
   Leave the **Claude AI Integration** connector enabled. It is registered automatically.
2. Launch Gorgon Scout once, sign in, and start your free trial.
3. Fully restart Claude Desktop so it loads the connector.
4. Ask Claude to scan a target you are authorised to test.

Advanced: the connector is also published as a `.mcpb` Desktop Extension you can add to
Claude Desktop manually:
https://storage.googleapis.com/gorgon-scout-downloads/gorgon-scout.mcpb
(It still requires the Gorgon Scout app to be installed.)

A step-by-step guide: https://gorgoncyber.com/scout-claude.html

## Tools

22 tools across account/sign-in, profile management, spec import, AI auto-record,
interactive auth handling, scan start/poll/cancel, and AI analysis. See
[`manifest.json`](./manifest.json) for the full list and descriptions.

## Links

- Overview: https://gorgoncyber.com/scout
- Download: https://gorgoncyber.com/scout-download.html
- Run from Claude (guide): https://gorgoncyber.com/scout-claude.html

---

Gorgon Scout and this connector are products of Gorgon Cyber Pty. Ltd., Melbourne,
Australia. Designed for testing applications you own or are explicitly authorised to test.
