# Paul O'Toole

**Architect · Developer · Engineer**  
potoole@nosignal.ie · Maynooth, Ireland.  
Available remotely across Ireland and the UK

---

Thirty years across enterprise software, CRM platforms, business intelligence and infrastructure. Built and led Dynamics 365 deployments, ETL pipelines and BI portals across the charity and pharmaceutical sectors. Now building actively in Python -- and more recently C#/.NET and Flutter/Dart -- across a portfolio of 21 private tools spanning data ownership, network diagnostics, homelab infrastructure, epistemic tooling, hardware and process monitoring, drive auditing, personal task tracking, a mobile wellbeing app and a commercial SaaS product in active development.

---

## Portfolio

The projects below represent active and completed work across a consistent Python-dominant stack, with one C#/.NET desktop application and one Flutter/Dart mobile application.

### Copilot Data Ownership Suite
**cpl-loader** · **cpl-viewer**

A complete end-to-end pipeline for taking ownership of Microsoft Copilot conversation history. The loader is a Windows-native ETL tool with incremental detection and MERGE-based upsert logic; the viewer is a full-stack web application (FastAPI + React + TypeScript) with full-text search, topic cloud analysis, a monthly stats/KPI dashboard, and a built-in admin panel for schema browsing, live ERD viewing and CSV import. Built for personal data sovereignty -- no third-party services involved.

### Homelab Utility Suite
**GMARC** · **Metrix** · **Nexus**

**GMARC** is a forensic-grade Gmail archiving desktop application with a 23-tab analytics dashboard covering senders, domains, labels, archive growth, activity heatmaps, email champions, financial emails, travel bookings, subscription audit, conversation partners and subject keyword frequency. Privacy-first by design -- external images blocked, JavaScript disabled, HTML sanitised. Packaged as a standalone Windows executable via PyInstaller.

**Metrix** is a household utility tracker deployed live on a homelab LXC container. Parses Electric Ireland and Bord Gáis PDF bills automatically, tracks meter readings and surfaces consumption trends via Chart.js dashboards. Dual-utility architecture with electricity and gas live.

**Nexus** is a self-hosted personal dashboard -- a curated 8×6 tile grid of shortcuts served from a private web server. Features drag-and-drop reorder, right-click tile editing, icon upload, live search and JSON-driven configuration. Mobile is read-only; all edits sync to the server instantly.

### Personal Network & Hardware Toolkit
**PKTrace** · **NetStat++** · **SysMon** · **Spiketrax**

Four complementary tools covering different layers of system visibility. PKTrace operates at the packet level (Wireshark-style capture with Scapy). NetStat++ monitors active TCP/UDP connections at the OS and process level. SysMon is a real-time hardware monitoring dashboard -- the portfolio's only C#/.NET project -- with 60-second rolling sparkline charts for CPU, Memory, Disk and Network, CPU/GPU temperatures via HWiNFO64, an internet speed test, and theme switching. Spiketrax is a generic, real-time CPU-spike monitor for any process by name or PID -- charts it live against a rolling ring buffer, detects sustained spikes via a dip-tolerant hysteresis state machine, captures a symbolicated stack sample of the offending process while it's spiking (macOS), and can optionally terminate it via exact PID/name match, never a substring.

### Epistemic Toolkit
**Calibre** · **Veritas**

Two tools for evaluating information quality. Calibre assesses the psychological impact style of communicators using Azure OpenAI -- stabilising or destabilising, scored and persisted to SQL Server. Veritas is a structured framework for evaluating the belief-worthiness of documentary-style media, combining a Discourse Layer (reasoning quality, evidence presence, speculation and narrative penalties) with a Participant Credence Score 70/30, producing a scored verdict with certainty percentage. Veritas now includes automatic YouTube transcript fetching, a linguistic heuristic analyser across 57 patterns, a batch evaluation CLI for CSV/JSON URL lists, and a local transcript cache.

### Standalone Utilities
**WordPad++** · **SQLsnip** · **Syntrax** · **ClassDoc** · **RecTrax** · **IndieTrax** · **TaskTrax** · **filescan**

A set of practical tools filling genuine gaps. WordPad++ is a modern multi-tab rich text editor replacing the application Microsoft removed from Windows 11. SQLsnip is a system-tray SQL snippet injector for SSMS with low-level keyboard hooks. Syntrax is an in-development cross-device music synchronisation engine, with a working library scanner, snapshot system and diff engine; the sync planner and device integration are still being built out. ClassDoc is a semantic document classification system using sentence-transformer embeddings, K-means clustering and a FastAPI web UI. RecTrax is a supermarket receipt ingestion engine for long-term price tracking, shrinkflation detection and cross-store comparison, with OCR ingestion and store-specific parsers covering Lidl, Aldi, Dunnes, Tesco and SuperValu (an analytics engine is planned for a later phase). IndieTrax is a personal indie game metrics tracker with an ideas pipeline, daily metrics ingestion and retention snapshots. TaskTrax is a single-file task board -- no build step, no database, no account -- for tracking open threads across every other project in this portfolio, syncing across devices via WebDAV to a self-hosted Nextcloud instance, with JSON bulk import and automatic open/close timestamping. filescan is a personal drive-auditing tool with no third-party dependencies, crawling drives into a SQLite database and producing quick stats or full intelligence reports covering media detection, duplicate files and housekeeping recommendations.

### Mobile

**Anchor** is an autism-first executive-function and regulation companion for iOS and Android, helping autistic adults manage energy, plan their day and regulate without decision overload. Built in Flutter with Riverpod state management and a Drift/SQLite persistence layer, following a phase-strict roadmap with full CI (static analysis, tests, coverage ratchet).

### Commercial SaaS

A B2B SaaS product in active commercial development targeting the faith sector across Ireland and the UK, now live in production. FastAPI backend with Alembic migrations against PostgreSQL (EU-hosted for GDPR data residency), Jinja2 + Bootstrap 5 frontend. Live features include meeting minutes with a rich-text editor, collections tracking, internal messaging, platform administration, and a dual-entity billing model supporting EUR and GBP; document management, rota scheduling, safeguarding logs and a people directory are scaffolded and planned. Role-based access across 6 permission levels with JWT authentication.

---

## Stack

| Category | Technologies |
|:---|:---|
| **Languages** | Python · C# · Dart · T-SQL · PowerShell · Bash · TypeScript |
| **Python** | FastAPI · SQLAlchemy · Alembic · PySide6 · PyQt5 · Tkinter · EasyOCR · Scapy · pyodbc · psutil · pyqtgraph |
| **C# / .NET** | .NET 9 · WPF · LiveChartsCore |
| **Mobile** | Flutter · Riverpod · Drift (SQLite) · go_router · Material 3 |
| **Frontend** | React · Vite · Tailwind CSS · Bootstrap 5 · Chart.js · Mermaid.js |
| **Cloud & Platforms** | Azure · Render.com · Cloudflare · Backblaze B2 · Dynamics 365 |
| **Databases** | SQL Server · PostgreSQL · SQLite |
| **Servers & OS** | Windows Server · Debian / Ubuntu · Proxmox LXC · VMware |
| **Networking** | pfSense · NGINX · Apache · OpenVPN · Zabbix |
| **BI & Reporting** | Power BI · SSRS · SSIS · IBM Cognos |
| **Tools** | Git · GitHub · SSMS · Redgate · PyInstaller |
| **AI & Tooling** | Claude · Claude Code · Azure OpenAI · Ollama |
| **Certifications** | CompTIA Network+ · Security+ · Linux+ · Microsoft certifications |

---

## Background

Early career in Visual Basic and SQL Server through the 1990s and 2000s, progressing through ASP.NET, C# and .NET. Deep T-SQL and ETL expertise developed across eleven years at a large national charity, leading CRM, BI, and integration platforms. More recently: Dynamics 365 architecture, VMware virtualisation, Proxmox homelab, and a full return to active app development across Python and C#.

---
