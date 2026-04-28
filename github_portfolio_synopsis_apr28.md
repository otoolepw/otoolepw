# GitHub Private Projects

## Portfolio Synopsis

**Paul O'Toole · April 2026**
**17 Projects**

---

## Overview

This document summarises all 17 private GitHub repositories in the portfolio. The projects span desktop GUI applications, full-stack web applications, ETL pipelines, network tooling, document classification, receipt analytics, hardware monitoring, and a commercial SaaS product. The dominant stack remains **Python** — with PySide6, PyQt5, or Tkinter for desktop UIs and **FastAPI** with SQL Server or PostgreSQL for web backends — though April 2026 marks the portfolio's first **C#/.NET** project (SysMon).

Since the March 2026 synopsis, the portfolio has grown by three projects (IndieTrax, SysMon, Nexus included for the first time) and seen major capability jumps in GMARC (17 → 23 dashboard tabs), Veritas (manual evaluation → YouTube transcript evaluator + batch CLI), Metrix (electricity-only → dual-utility with gas), and ClassDoc (early-stage → Phase 2/3 complete with semantic clustering and a web UI).

Natural groupings in the portfolio:
- **Copilot data ownership suite**: cpl-loader + cpl-viewer
- **Personal networking toolkit**: PKTrace + NetStat++
- **Epistemic toolkit**: Calibre + Veritas
- **Homelab utility suite**: GMARC + Metrix + Nexus
- **Commercial SaaS**: Parish Office
- **Standalone utilities**: WordPad++, SQLsnip, SysMon
- **Emerging tools**: ClassDoc, RecTrax, IndieTrax, Syntrax

---

## 🎯 1. Calibre

| Property | Value |
|----------|-------|
| **Language** | Python |
| **Version** | v1.0.0 |
| **Status** | Stable |
| **Updated** | February 2026 |
| **Stack** | Python · Azure OpenAI · SQL Server · Tkinter · pyodbc |

A psychological impact classifier for communicators. Feed it a name or communicator identifier and it uses Azure OpenAI to evaluate whether their style — not their content or politics — is stabilising or destabilising to the listener's nervous system. Returns a three-field deterministic result: category, percentage, and commentary. Results are persisted to SQL Server. The UI is a minimal Tkinter window with clean separation of concerns across config.py, api_client.py, sql_access.py, and ui.py.

**No changes since March 2026.**

**Note:** Natural companion to **Veritas** — together they form a personal epistemic toolkit for evaluating both media and the communicators within it.

---

## 📄 2. ClassDoc

| Property | Value |
|----------|-------|
| **Language** | Python 3.12 |
| **Version** | v0.2.0 |
| **Status** | Phase 2 & 3 complete; OCR in progress |
| **Updated** | April 2026 |
| **Stack** | Python · sentence-transformers · scikit-learn · FastAPI · SQLite · TF-IDF |

A document classification and semantic clustering engine. Extracts text from PDF, DOCX, PPTX, XLSX, RTF and TXT files, creates semantic embeddings using `all-MiniLM-L6-v2`, applies K-means clustering with auto-k selection, generates TF-IDF cluster labels, and builds a hierarchical taxonomy for document organisation. Phase 2 (April 2026) added a FastAPI web UI for browsing, searching and renaming clusters inline. Phase 3 added hierarchical taxonomy. OCR support for scanned documents is the current work-in-progress.

**Significant upgrade since March 2026 — from early-stage to Phase 2/3 complete.**

---

## 🔄 3. cpl-loader

| Property | Value |
|----------|-------|
| **Language** | Python |
| **Status** | Stable |
| **Updated** | February 2026 |
| **Stack** | Python · SQL Server · Tkinter · pyodbc |

A Windows-native ETL pipeline and GUI wrapper for processing Copilot CSV activity history. Features a Tkinter desktop GUI with live status updates, interactive ETL launcher, multi-stage workflow (raw load → parsing → final load), incremental loading to avoid reprocessing, duplicate detection, SQL Server–backed storage with MERGE-based upsert logic, multi-line CSV parsing with CRLF/LF handling, emoji and special character support, automatic CSV archiving with timestamped filenames, and structured logging to both GUI and log file.

**No changes since March 2026.**

**Note:** The upstream feeder for **cpl-viewer** — these two projects form a complete Copilot data ownership pipeline.

---

## 💻 4. cpl-viewer

| Property | Value |
|----------|-------|
| **Language** | TypeScript / Python |
| **Status** | Production-ready |
| **Updated** | February 2026 |
| **Stack** | FastAPI · SQLAlchemy · React · TypeScript · Vite · Tailwind CSS · SQL Server |

A full-stack web application for browsing and searching Copilot conversation history loaded by cpl-loader. Backend is FastAPI with SQLAlchemy connection pooling; frontend is React + TypeScript + Vite + Tailwind CSS. Features include full-text search, favouriting, a topic cloud (NLP-extracted via daily SQL Agent job), monthly stats dashboard, dark/light mode, and mobile-responsive design. Currently holds 3,624 conversations and 52,612 messages in the live instance.

**No changes since March 2026.**

**Note:** The most architecturally mature project in the portfolio, with proper separation between frontend and backend and a clean RESTful API.

---

## 📧 5. GMARC

| Property | Value |
|----------|-------|
| **Language** | Python 3.12 |
| **Version** | v0.10.1 |
| **Updated** | April 28, 2026 |
| **Stack** | PySide6 (Qt 6) · QWebEngineView · Google Gmail API · SQL Server · pyodbc · matplotlib |

Forensic-grade Gmail archiving desktop application with a **23-tab analytics dashboard** — the most analytically capable project in the portfolio. Uses the Gmail History API for incremental sync, stores raw MIME alongside parsed metadata in SQL Server, and renders HTML emails using QWebEngineView (Chromium). Privacy-first by default — external images blocked, JavaScript disabled, HTML sanitised.

The v0.10.0 release (April 2026) added six new analytics tabs: **Sending Behaviour** (top recipients, peak hours), **Conversation Partners** (two-way thread relationships), **Subscription Audit** (mailing lists via List-Unsubscribe header), **Financial Emails** (receipts and invoices by vendor), **Travel Tracker** (booking confirmations from airlines, hotels and car hire), and **Subject Keywords** (top 50 most frequent subject words). Seven new pre-aggregated SQL tables back these tabs, keeping dashboard load times sub-second. Three new performance indexes were added to the schema. v0.10.1 fixed tab layout width, SP arithmetic overflow, and pyodbc warning handling in the Data Refresh path.

Features a standalone EXE via PyInstaller, background sync threading, SQL Agent job for 6-hour stats refresh, and on-demand Data Refresh button in the dashboard.

**Major upgrade since March 2026 — dashboard grew from 17 to 23 tabs across two releases.**

---

## 🎮 6. IndieTrax *(new)*

| Property | Value |
|----------|-------|
| **Language** | Python |
| **Version** | v0.1.0 |
| **Status** | Scaffolded — database integration in progress |
| **Updated** | April 2026 |
| **Stack** | FastAPI · SQLAlchemy · PostgreSQL · Jinja2 · Bootstrap 5 · Chart.js |

A personal indie game metrics tracker and ideas pipeline. Tracks game ideas through a status funnel (New → Evaluating → Approved → In Development → Shipped), manages a games catalogue with store links and AdMob identifiers, records daily metrics (downloads, revenue, active users), and captures retention snapshots at D1/D7/D30 intervals. Dashboard features 30-day dual-axis Chart.js charts per game for downloads vs. revenue. The architecture mirrors Metrix — async FastAPI + SQLAlchemy, Bootstrap 5 frontend, LXC deployment target.

**Note:** Early-stage scaffolding is complete; the project is queued for database wiring and first data ingestion.

---

## ⚡ 7. Metrix

| Property | Value |
|----------|-------|
| **Language** | Python |
| **Version** | v0.5.1 |
| **Status** | Production — dual-utility live |
| **Updated** | April 2026 |
| **Stack** | FastAPI · SQLAlchemy 2 (async) · SQL Server · NGINX · Bootstrap 5 · Chart.js · LXC |

A household utility tracker deployed live at http://192.168.69.208/metrix/ on LXC container 208. Originally electricity-only, v0.5.x completes the gas integration: Bord Gáis PDF bill parsing, gas meter readings with delta calculation, gas billing cycle management, and dual-utility dashboard analytics. The schema was designed from the outset to be utility-agnostic via an `is_active` flag and a `utility_type` discriminator — adding gas required a parser implementation rather than a schema redesign. v0.5.1 (April 2026) fixes the PDF download URL and adds gas reading validation.

Features: Electric Ireland + Bord Gáis PDF parsing, meter readings, billing cycles, KPI cards, 12-month analytics, anomaly detection, usage forecasting, and admin tooling. Deployment automation via sync_to_lxc.ps1, deploy.sh and health_check.sh.

**Significant upgrade since March 2026 — gas integration complete and live.**

---

## 🌐 8. NetStat++

| Property | Value |
|----------|-------|
| **Language** | Python 3.10+ |
| **Version** | v0.1.0 |
| **Status** | Stable |
| **Updated** | February 2026 |
| **Stack** | Python · Tkinter · psutil · pytest |

A real-time network connection monitoring tool — a lightweight, Python-native alternative to the Windows `netstat` command, with a proper GUI. Displays live TCP/UDP connections mapped to PIDs and process names, with colour-coded connection states (ESTABLISHED, LISTEN, TIME_WAIT, etc.). Features multi-column sorting with shift-click secondary sort, a changes-only mode to highlight new and recently closed connections, asynchronous reverse DNS lookups on demand, comprehensive filtering by protocol, state, PID, and port, and a summary panel showing connection counts at a glance.

**No changes since March 2026.**

**Note:** Sits naturally alongside **PKTrace** — PKTrace captures and inspects packets at the wire level, while NetStat++ monitors active connections at the OS/process level.

---

## 🏠 9. Nexus *(first inclusion)*

| Property | Value |
|----------|-------|
| **Language** | JavaScript / HTML / CSS |
| **Version** | v0.2.8 |
| **Status** | Production |
| **Updated** | April 2026 |
| **Stack** | Vanilla JS · Service Worker · PWA · Flask/Apache proxy · LXC |

A self-hosted cross-device dashboard — a personal homepage of curated shortcuts deployed as a Progressive Web App at nexus.nosignal.ie. Presents an 8×6 responsive tile grid of shortcuts, configurable via a JSON data layer. Features drag-and-drop reorder on desktop, icon upload and custom icon serving, offline capability via service worker, and a version label. Recent updates (v0.2.8) fix icon serving reliability and shortcut persistence. Migrated to LXC 203 behind an Apache reverse proxy.

**Note:** While lightweight in stack, Nexus is the most-used application in the homelab day-to-day — it is the entry point to everything else.

---

## ⛪ 10. Parish Office

| Property | Value |
|----------|-------|
| **Language** | Python |
| **Version** | v0.3.0 |
| **Status** | Active development |
| **Updated** | April 2026 |
| **Stack** | FastAPI · PostgreSQL · Alembic · Jinja2 · htmx · Bootstrap 5 · Quill.js · Backblaze B2 · Cloudflare |
| **Domains** | parishoffice.ie · parishoffice.co.uk |

The flagship SaaS project. A parish administration platform targeting approximately 33,000–38,500 Catholic and Protestant parishes across Ireland and the UK. The MVP covers document management, meeting minutes, collections tracking, rota scheduling, safeguarding logs, and a people directory. v0.3.0 (April 2026) added a Quill.js rich-text editor for minutes, a collections tracker, an internal messaging module, a platform admin section, and a territory/billing model supporting both EUR and GBP entities.

Role-based access with 6 permission levels, JWT authentication, GDPR-compliant, designed to be affordable at €10–30/month per parish. Backend is FastAPI with Alembic migrations against PostgreSQL. Frontend is Jinja2 + htmx + Bootstrap 5. Domains registered and Cloudflare DNS configured.

**Meaningful feature additions since March 2026 — now v0.3.0 with minutes editor, collections and messaging.**

**Note:** The only project in the portfolio targeting an external market and the only one on PostgreSQL — a sensible choice given the Render.com SaaS deployment target.

---

## 🔍 11. PKTrace

| Property | Value |
|----------|-------|
| **Language** | Python |
| **Status** | Feature-complete |
| **Updated** | January 2026 |
| **Stack** | Python · PySide6 · Scapy · psutil |

A lightweight Wireshark-style packet capture and inspection tool. Built with PySide6 and Scapy, it provides live capture on any network interface, a Wireshark-style packet table with tri-state multi-column sorting (IP-aware and numeric-aware), a layer-by-layer detail pane with hex and ASCII views, real-time text filtering, and PCAP export. Capture runs on a dedicated background thread to keep the UI fully responsive. Clean architecture with separate core/, services/, and ui/ packages, plus its own icon set.

**No changes since March 2026.**

**Note:** Together with **NetStat++**, provides a solid personal network visibility toolkit covering both packet-level and connection-level monitoring.

---

## 🛒 12. RecTrax

| Property | Value |
|----------|-------|
| **Language** | Python 3.12 |
| **Version** | v0.3.0 |
| **Status** | Phase 1 complete; Phase 2 in progress |
| **Updated** | March 2026 |
| **Stack** | Python · EasyOCR · SQL Server · pytest |

A supermarket receipt ingestion and analytics engine for long-term price tracking, shrinkflation detection, and cross-store comparison. Processes receipts from Lidl, Aldi, Dunnes, Tesco and SuperValu using OCR and store-specific parsers feeding a canonical product catalogue in SQL Server. Phase 1 (code review, architecture and fixes) is complete with 50+ tests passing. Phase 2 covers batch ingestion, duplicate detection and product normalisation. The SuperValu parser added in the latest phase handles franchise format variations and PDF text-layer corruption detection.

**Note:** Five-store parser coverage (Lidl, Aldi, Dunnes, Tesco, SuperValu) — approaching full Irish supermarket coverage.

---

## 💾 13. SQLsnip

| Property | Value |
|----------|-------|
| **Language** | Python |
| **Status** | Stable |
| **Updated** | February 2026 |
| **Stack** | Python · Windows API · Keyboard hooks |

Lightweight SQL snippet injector for SSMS and other SQL editors. Lives in the Windows system tray — type a shortcut keyword in any SQL editor and press Tab; SQLsnip detects the shortcut, retrieves the corresponding snippet, and injects the full SQL text via clipboard paste. Installs a low-level WH_KEYBOARD_LL keyboard hook, verifies SSMS is in the foreground before injecting, and triggers IntelliSense (Ctrl+Space) after snippets ending with a space. Supports `$CURSOR$` caret placement and `$DATE(format)$` token resolution at inject time.

**No changes since March 2026.**

---

## 🖥️ 14. SysMon *(new)*

| Property | Value |
|----------|-------|
| **Language** | C# 12 |
| **Version** | v0.2.0 |
| **Updated** | April 28, 2026 |
| **Stack** | C# 12 · .NET 9 · WPF · LiveChartsCore · HWiNFO64 |

A Windows real-time hardware monitoring dashboard — the portfolio's **only C#/.NET project**. Displays a four-panel dashboard covering CPU, Memory, Disk and Network, each with a 60-second rolling sparkline chart via LiveChartsCore. CPU and GPU temperatures are sourced from HWiNFO64's shared memory interface. Additional features include a Cloudflare-based internet speed test with a dedicated results window, live public IP display, system tray integration with hide-to-tray, theme switching (Dark / Light / Auto following Windows system theme), and persistent settings.

v0.2.0 (April 2026) adds theme switching, the speed test window, and HWiNFO temperature integration. A natural complement to the PKTrace + NetStat++ network toolkit — SysMon covers the hardware layer, those two cover the network layer.

---

## 🎵 15. Syntrax

| Property | Value |
|----------|-------|
| **Language** | Python 3.12 |
| **Version** | v0.1.0 |
| **Status** | Active development — Phase 1 core engine in progress |
| **Updated** | April 2026 |
| **Stack** | Python · PySide6 · SQLite · Mutagen · pytest |

A cross-device music synchronisation engine and desktop application. Strategically reorganised in April 2026 with a clear ROADMAP after earlier development stalled in a PoC state (v0.0.5). Current Phase 1 work: working GUI shell, library scanner, snapshot system, diff engine, and playlist reading via Mutagen. Partial: device detection and sync planner/executor. The sync planner will intelligently determine what to copy, update or remove across devices. A healthy test suite covers device registry, library hierarchy, snapshot diffs and sync planning.

**Note:** Notable for having the most carefully designed algorithmic core in the portfolio — the snapshot diff and sync planner modules reflect careful algorithm design for a hard problem.

---

## 🔎 16. Veritas

| Property | Value |
|----------|-------|
| **Language** | Python |
| **Version** | v0.2.1 |
| **Updated** | April 28, 2026 |
| **Stack** | Python · youtube-transcript-api · argparse (CLI) |

A structured media belief-worthiness evaluation framework, now extended with **YouTube transcript evaluation and batch processing**. The v3 framework evaluates media across two layers — a Discourse Layer (reasoning quality, evidence presence, speculation and narrative penalties) and a Participant Credence Score covering domain expertise, track record, epistemic behaviour, independence and evidence discipline — combined 70/30 to produce a final score with certainty percentage.

v0.2.0 (April 2026) adds: automatic YouTube transcript fetching (no API key required, local cache at `~/.veritas/transcript_cache/`), a linguistic heuristic analyzer scoring discourse from 57 word/phrase patterns across evidence, speculation, narrative framing and logical structure, a `YouTubeEvaluator.evaluate(url)` end-to-end API, a `BatchEvaluator` for processing CSV/JSON URL lists with report/JSON/CSV output, and a full CLI (`evaluate-youtube`, `batch`, `demo` commands). v0.2.1 fixes youtube-transcript-api v1.x compatibility and Windows cp1252 console encoding. 19 tests passing.

**Major capability jump since March 2026 — from a manual scoring framework to an automated YouTube evaluation pipeline.**

**Note:** Companion to **Calibre** — together they constitute a personal epistemic toolkit for evaluating both media content and communicator style.

---

## 📝 17. WordPad++

| Property | Value |
|----------|-------|
| **Language** | Python |
| **Version** | v1.0.3 |
| **Status** | Feature-complete |
| **Updated** | January 2026 |
| **Stack** | Python · PyQt5 · PyInstaller |

A modern, multi-tab rich text editor built as a direct replacement for the WordPad application Microsoft removed from Windows 11. Supports RTF, HTML, plain text and PDF export. Full formatting toolbar covering bold, italic, underline, alignment, indentation, lists, and font and colour selection. Includes clipboard image pasting with save warnings, find and replace, live word and character count in the status bar, persistent recent files menu, and PyInstaller packaging for standalone EXE distribution.

**No changes since March 2026.**

**Note:** A clean, practical utility that fills a genuine gap left by Microsoft's decision to discontinue WordPad.

---

## Technology Summary

### Languages
- **Python**: 14 projects (dominant)
- **C# / .NET**: 1 project (SysMon — new)
- **TypeScript / JavaScript**: 2 projects (cpl-viewer frontend, Nexus)

### Desktop Frameworks
- **PySide6 (Qt 6)**: GMARC, PKTrace, Syntrax
- **WPF (.NET 9)**: SysMon
- **PyQt5**: WordPad++
- **Tkinter**: Calibre, cpl-loader, NetStat++

### Web Frameworks & Frontends
- **FastAPI**: cpl-viewer, ClassDoc, Metrix, Parish Office, IndieTrax
- **React + TypeScript + Vite**: cpl-viewer
- **Jinja2 + htmx + Bootstrap 5**: Parish Office, Metrix, IndieTrax
- **Vanilla JS / PWA**: Nexus

### Databases
- **SQL Server**: Calibre, cpl-loader, cpl-viewer, GMARC, Metrix, RecTrax, SQLsnip
- **PostgreSQL**: Parish Office, IndieTrax
- **SQLite**: Syntrax, ClassDoc

### Deployment
- **LXC containers (homelab)**: Metrix (208), Nexus (203), IndieTrax (208)
- **Render.com SaaS**: Parish Office
- **Standalone .exe**: GMARC, WordPad++, SQLsnip, SysMon

---

## What's New Since March 2026

| Project | Change |
|---------|--------|
| **GMARC** | v0.8.1 → v0.10.1 — dashboard grew from 17 to 23 tabs; 6 new analytics tabs; 7 new SQL tables; 3 performance indexes; Data Refresh hardened |
| **Veritas** | v0.1.0 → v0.2.1 — YouTube transcript evaluator, linguistic analyzer, batch CLI, 19 tests |
| **Metrix** | Phase 10 → v0.5.1 — gas integration (Bord Gáis) complete and live |
| **ClassDoc** | Early stage → v0.2.0 — semantic clustering, FastAPI web UI, hierarchical taxonomy |
| **Parish Office** | Foundation → v0.3.0 — minutes editor, collections, messaging, dual-entity billing |
| **Syntrax** | Stalled PoC → v0.1.0 — strategic reorganisation with roadmap |
| **SysMon** | — | New project (v0.2.0); first C#/.NET project in portfolio |
| **IndieTrax** | — | New project (v0.1.0); game metrics tracker scaffolded |
| **Nexus** | — | First inclusion in portfolio report (v0.2.8; live at nexus.nosignal.ie) |

---

## Project Groupings

### 🔒 Copilot Data Ownership Suite
**cpl-loader** (ETL ingestion) + **cpl-viewer** (web browsing)

### 🌐 Personal Network Toolkit
**PKTrace** (packet-level) + **NetStat++** (connection-level) + **SysMon** (hardware layer)

### 🧠 Epistemic Toolkit
**Calibre** (communicator impact) + **Veritas** (media belief-worthiness + YouTube evaluation)

### 🏠 Homelab Utility Suite
**GMARC** (Gmail archive) + **Metrix** (utility tracking) + **Nexus** (dashboard)

### 💼 Commercial SaaS
**Parish Office** — B2B SaaS platform targeting religious institutions across Ireland and the UK

### 🛠️ Standalone Utilities
**WordPad++** — RTF text editor  
**SQLsnip** — SQL snippet injector  
**SysMon** — hardware monitoring dashboard

### 🔬 Emerging Tools
**ClassDoc** — semantic document classification  
**RecTrax** — supermarket receipt analytics  
**IndieTrax** — indie game metrics tracker  
**Syntrax** — cross-device music sync engine

---

## Code Quality & Maturity

| Maturity Level | Projects |
|---|---|
| **Production / Feature-complete** | cpl-viewer, GMARC (v0.10.1), Metrix (v0.5.1), NetStat++ (v0.1.0), WordPad++ (v1.0.3), SQLsnip, Calibre (v1.0.0), Veritas (v0.2.1), PKTrace, SysMon (v0.2.0), Nexus (v0.2.8) |
| **Active Development** | Parish Office (v0.3.0), ClassDoc (v0.2.0), RecTrax (v0.3.0), Syntrax (v0.1.0), cpl-loader, IndieTrax (v0.1.0) |

---

**Last Updated:** April 28, 2026
**Portfolio Author:** Paul O'Toole
