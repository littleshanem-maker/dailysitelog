# CLAUDE.md

This file provides guidance for AI assistants working on the **dailysitelog** project.

## Project Overview

**dailysitelog** is a **Tier 3 Construction Daily Site Log App** — a simple, mobile-first data entry tool for construction site teams. Workers and supervisors use it to record daily activity on job sites quickly and with minimal friction.

- **Repository**: `littleshanem-maker/dailysitelog`
- **Current state**: Early development (greenfield)

### Core Product Goals

1. **Simple, mobile-first data entry** — site teams fill out logs on phones in the field
2. **Speed over polish** — users have limited time and small screens; every interaction must be fast
3. **Exportable data** — all data must be stored in a format that can be easily exported to PDF or spreadsheet (CSV/Excel)

## Repository Structure

```
dailysitelog/
├── CLAUDE.md          # AI assistant guidance (this file)
└── README.md          # Project readme
```

No source code, configuration files, tests, or dependencies exist yet. Update this section as the project grows.

## Tech Stack

Not yet determined. When choosing technologies, prefer:
- Lightweight, mobile-friendly frameworks
- Tools with strong offline/low-connectivity support (construction sites often have poor signal)
- Simple data persistence that maps cleanly to tabular export (PDF, CSV, Excel)

## Build & Run

No build system, scripts, or run commands are configured yet. Update this section once tooling is selected.

## Testing

No test framework or test files exist yet. Update this section when testing is set up.

## Development Workflow

### Git

- Commits should have clear, descriptive messages
- There is no CI/CD pipeline configured yet

### Code Style

No linters, formatters, or style guides have been configured yet. Once tooling is added, document the commands here (e.g., lint, format, type-check).

## Design & UI Rules

These rules apply to **every** feature and screen added to this app:

### Mobile-First, High-Contrast UI

- Design for small screens first (phones in direct sunlight on a construction site)
- Use **high-contrast colors** — dark text on light backgrounds, bold accent colors for actions
- Use **large tap targets** — buttons and form fields must be easy to hit with gloved or dirty fingers
- Minimum touch target size: 44x44px (ideally larger)
- Avoid small text; use readable font sizes (16px minimum for body text)

### No Technical Jargon

- All labels, buttons, messages, and instructions must use **plain, non-technical language**
- Write for someone who does not use software regularly
- Examples:
  - "Save" not "Submit form"
  - "Today's Log" not "Daily Log Entry Instance"
  - "Add a Photo" not "Upload attachment"
  - "Something went wrong — try again" not "Error 500: Internal Server Error"

### Speed & Simplicity

- Every feature must work for a user with **limited time and a small screen**
- Minimize the number of taps/steps to complete any action
- Prefer single-screen forms over multi-step wizards when possible
- Auto-fill defaults where possible (today's date, current project, last-used values)
- Support saving partial entries — never lose a user's work

## Data & Export Rules

- **All log data must be stored in a structured, tabular format** (rows and columns)
- Data must be exportable to:
  - **PDF** — formatted daily log reports suitable for printing or emailing to stakeholders
  - **Spreadsheet** (CSV or Excel) — for project managers who track data in spreadsheets
- Field names in storage should be human-readable so exports make sense without a data dictionary
- Dates should use a clear format (e.g., "Feb 5, 2026" or "2026-02-05"), never Unix timestamps in user-facing output
- Photo/attachment references should be included in exports as file names or links

## Key Conventions

- Add a `.gitignore` early to avoid committing build artifacts, secrets, or OS files
- If secrets or env-specific config are needed, use `.env` files and keep them out of version control

## Notes for AI Assistants

- This project is greenfield. Choose simple, well-established tools and avoid over-engineering.
- Always read existing files before modifying them.
- Keep changes focused and minimal — don't add infrastructure or abstractions beyond what is immediately needed.
- **Before adding any feature**, ask: "Can a site worker use this on a phone in under 10 seconds?" If not, simplify.
- **Before choosing a data format**, ask: "Can this be exported to a PDF and a spreadsheet cleanly?" If not, restructure.
- Update this file when significant project structure, tooling, or conventions are established.
