# The Morning Brief

[![Live site](https://img.shields.io/badge/site-live-2ea44f?style=flat-square)](https://saaimsaad.github.io/morning-brief/)
[![Updates](https://img.shields.io/badge/updates-daily%20·%2007%3A00%20IST-1f6feb?style=flat-square)](https://saaimsaad.github.io/morning-brief/)
![Built with Claude Opus 4.8](https://img.shields.io/badge/built%20with-Claude%20Opus%204.8-8A63D2?style=flat-square)
![GitHub last commit](https://img.shields.io/github/last-commit/SaaimSaad/morning-brief?style=flat-square)
[![License: MIT](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)

A self-updating **digital newspaper**. Every morning a scheduled Claude agent researches
the day's news, writes it up as a clean front page, and publishes it here — no human in
the loop.

### 📰 Read it live → **<https://saaimsaad.github.io/morning-brief/>**

`Automated` &nbsp; `Cloud routine` &nbsp; `Web research` &nbsp; `GitHub Pages` &nbsp; `Cron` &nbsp; `Claude Opus 4.8`

The whole thing runs on a Claude subscription: a cloud routine does the research and
writing, GitHub Pages serves the result, and it refreshes on a schedule while my machine
is switched off.

## What it does

Every day at **07:00 IST**, a cloud routine running **Claude Opus 4.8**:

1. **Researches** the last 24–48 hours of news with live web search, across three beats:
   - **AI & LLMs** — model releases, Anthropic/Claude updates, notable research and industry moves.
   - **Automotive & MBD** — OEMs, ADAS/autonomy, Adaptive AUTOSAR, functional safety, AI in embedded software.
   - **India · Cars & Bikes** — India-market tech and vehicle launches.
2. **Writes** a tight front page — 3–5 sourced items per section, facts first, every item linked, rumours flagged as rumours.
3. **Publishes** by rewriting `index.html` (preserving the house template), archiving the previous edition under `archive/`, and pushing the commit.
4. **Notifies** by emailing the day's top story with a link.

If publishing ever fails, it falls back to emailing the full brief with the reason — so an
edition is never silently lost.

## Structure

| Path | What it is |
|---|---|
| `index.html` | The latest edition — what the live site serves |
| `archive/YYYY-MM-DD.html` | Every past edition, kept for the record |

## How it's wired

- **Research + writing + publishing** — a Claude Code *cloud routine* on a cron schedule, running server-side (no local machine needed).
- **Hosting** — GitHub Pages, served from `main`.
- **Delivery** — the live page, plus a short daily email.
- **Design** — one self-contained HTML template with inline CSS and automatic dark mode; no build step.

---

*A personal project. The published page contains only news and source links — it is
compiled automatically each morning by Claude.*
