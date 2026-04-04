# Zineb Nadak — Developer Handbook
> My personal engineering process — how I plan, build, and document projects.

---

## Table of Contents
1. [Project Selection](#1-project-selection)
2. [Choosing a Project Format](#2-choosing-a-project-format)
3. [Choosing a Development Process](#3-choosing-a-development-process)
4. [Project Phases & Timeline](#4-project-phases--timeline)
5. [After MVP — What Comes Next](#5-after-mvp--what-comes-next)
6. [When Is a Project "Done"?](#6-when-is-a-project-done)
7. [Documentation Standards](#7-documentation-standards)
8. [GitHub Repo Structure](#8-github-repo-structure)
9. [Tech Stack](#9-tech-stack)
10. [Build Principles](#10-build-principles)

---

## 1. Project Selection

**Goal:** Solve a real problem for real people.

Before I commit to a project, I answer these questions:

- Is the problem specific and observable?
- Do users already rely on a workaround (Other socials, spreadsheet, pen & paper)?
- Can I build a working MVP in 1–2 weeks?
- Is there at least one real person who will use it?

> A project I build for a real user beats a perfect project built for nobody.

---

## 2. Choosing a Project Format

I´ll pick the **simplest format** that solves the problem, and gets to a working product fastest with the least complexity.


| Format | When to use | Examples |
|---|---|---|
| **Web app** | Users need UI across devices | Attendance tracker, booking tool |
| **Mobile-first web app** | Primary usage is on phone | Prayer coordinator, field tools |
| **REST API / Backend** | Other apps need your data | Public data API, internal service |
| **Bot** | Users are already on a messaging platform | Telegram reminder bot, Discord helper |
| **Automation / workflow** | Repetitive tasks need to run on schedule | n8n flows, Python scripts |
| **CLI tool** | Developer-facing, terminal-based | File processor, code generator |
| **Dashboard / internal tool** | Display + interact with data | Admin panel, analytics view |
| **Scraper + pipeline** | Data needs to be collected and structured | Price tracker, news aggregator |



---

## 3. Development Process

As a solo developer I still work with formal processes — but the lightweight ones. I work highly-iterative, "Agile-lite" methodologies, emphasizing Minimun Viable Products (MVPs).

### My Approach: Lean Agile + Kanban

**Agile** (mindset) -  Ship early, iterate based on real feedback 
**Kanban** (execution) -  Visual board: To Do → In Progress → Done 

- Tasks managed on a Kanban board (GitHub Projects or Notion)
- Commits are small and meaningful — never in single big dumps
- Scope is defined before writing a single line of code

> Every project README states the process used — so it is visible to anyone reviewing the repo.

---
---
---
---
---
---
---
---

## 4. Project Phases & Timeline

Every project I build follows this sequence. Timelines are for a standard 1–2 week MVP.

---

### Phase 0 — Discovery `Day 1`

**Goal:** Understand the problem before solving it.

- [ ] Write down the problem in one sentence
- [ ] Identify the users
- [ ] List what they currently do instead (the workaround)
- [ ] Define the single core outcome the MVP must achieve

**Output:** `PROJECT_BRIEF.md`

**Tools I use:** Notion, plain text, or markdown

---

### Phase 1 — Scope `Day 1–2`

**Goal:** Decide exactly what to build and what to leave out.

- [ ] List 3–4 must-have features (MVP)
- [ ] Write an explicit "NOT building" list
- [ ] Choose the project format (see section 2)
- [ ] Choose the tech stack (see section 9)

**Output:** Scope section added to `PROJECT_BRIEF.md`

---

### Phase 2 — Design `Day 2–3`

**Goal:** Visualise before building.

- [ ] Sketch wireframes for every screen (Figma or Excalidraw — both free)
- [ ] Draw an ER diagram (database structure)
- [ ] Map the user flow (how a user moves through the app)
- [ ] Draw a use case diagram (who does what)

**Output:** `/docs` folder with exported images

**Tools I use:** Figma, Excalidraw, draw.io, Astah (for UML diagrams)

---

### Phase 3 — Setup `Day 3`

**Goal:** Get the foundation running before touching features.

- [ ] Create GitHub repo with correct structure (see section 8)
- [ ] Write a first draft `README.md`
- [ ] Set up the tech stack locally
- [ ] Deploy a blank version (confirm deployment works before building)
- [ ] Set up Kanban board with tasks

**Output:** Live (empty) deployment + repo visible on GitHub

**Tools I use:** GitHub, Vercel / Netlify, Supabase

---

### Phase 4 — Build MVP `Day 3–10`

**Goal:** Build only what is in scope. Nothing more.

- [ ] Build one feature at a time
- [ ] Commit after every meaningful change with clear messages:
  - `feat: display today's meeting times`
  - `fix: attendance count not updating`
  - `chore: connect supabase client`
- [ ] Do not optimise here — get it working first
- [ ] Test on real device throughout (not just desktop browser)

**Output:** Working MVP on a live URL
**Tools I use:** VS Code, Next.js, Supabase, Vercel

---

### Phase 5 — Real User Testing `Day 7–12`

**Goal:** Let real people use it without you explaining anything.

- [ ] Share the link with actual users
- [ ] Watch them use it (if possible) — do not guide them
- [ ] Note what confuses them, what breaks, what is missing
- [ ] Collect feedback (even informally via WhatsApp)

**Output:** Feedback list, bug list

---

### Phase 6 — Ship & Polish `Day 10–14`

**Goal:** Make it reliable and presentable.

- [ ] Fix critical bugs from testing
- [ ] Polish mobile UI
- [ ] Update README with screenshots and live link
- [ ] Final deployment

**Output:** Portfolio-ready project

---

## 5. After MVP — What Comes Next

MVP is the beginning, not the end. Here is what typically follows:

### Week 1-2 — Stabilise
- Fix bugs discovered by real users
- Improve UX based on feedback
- Refine the most-used features

**Time estimate:** 3–5 days

---

### Week 2–4 — Improve
- Add 1–2 high-impact features from feedback
- Improve performance if needed
- Add error handling and edge case coverage

**Time estimate:** 1 week

---

### Week 4+ — Expand (Optional)
- Add integrations (notifications, third-party APIs, bots)
- Add authentication if needed
- Consider scaling only if real usage demands it

**Time estimate:** Ongoing, feature by feature

---

## 6. When Is a Project "Done"?

A project is done when:

- ✅ It solves the original problem reliably
- ✅ Real users are using it without your help
- ✅ No critical bugs remain
- ✅ The README is complete with a live demo link
- ✅ The repo is clean and documented

It is NOT done when it is perfect. Perfect is not a real destination.

---

## 7. Documentation Standards

Every project must have the following before it counts as portfolio-ready.

### README.md (required)

```
# Project Name
One sentence description.

## Problem
What problem does this solve?

## Solution
How does it solve it?

## Live Demo
[link]

## Screenshots
[images]

## Tech Stack
- Frontend:
- Backend:
- Database:
- Deployment:

## How to Run Locally
Step by step instructions.

## Development Process
Process used (e.g. Lean Agile + Kanban)

## What I Learned
Honest reflection — what was hard, what surprised you.

## Roadmap
What comes next.
```

### /docs folder (required)

| File | Description |
|---|---|
| `wireframes.png` | UI sketches for each screen |
| `er-diagram.png` | Database structure |
| `user-flow.png` | How a user moves through the app |
| `use-case-diagram.png` | Who does what |

### Git commit hygiene (required)

Use the prefix convention:
- `feat:` new feature
- `fix:` bug fix
- `chore:` setup, config, refactor
- `docs:` documentation update
- `style:` UI/CSS changes only

Never commit everything at once. Commit history is part of the portfolio.

---

## 8. GitHub Repo Structure

```
project-name/
├── README.md                  ← first thing anyone sees
├── PROJECT_BRIEF.md           ← problem, scope, decisions
├── docs/
│   ├── wireframes.png
│   ├── er-diagram.png
│   ├── user-flow.png
│   └── use-case-diagram.png
├── src/                       ← application code
│   ├── app/                   ← Next.js app router pages
│   ├── components/            ← reusable UI components
│   └── lib/                   ← utilities, API clients
├── .env.example               ← environment variable template (never commit .env)
└── .gitignore
```

---

## 9. Tech Stack

This is what I currently work with. Updated as I add tools.

| Layer | Tool | Notes |
|---|---|---|
| Frontend | Next.js | React framework, mobile-first |
| Styling | Tailwind CSS | Utility-first CSS |
| Backend | Supabase | PostgreSQL + realtime + auth |
| Database | PostgreSQL | Via Supabase |
| Deployment | Vercel | Auto-deploys from GitHub |
| Automation | n8n | No-code workflow automation |
| Scripting | Python | Data tasks, CLI tools |
| Design | Figma / Excalidraw | Wireframes and flows |
| Diagrams | draw.io / Astah | ER diagrams, UML |
| Task board | GitHub Projects | Kanban board per project |

---

## 10. Build Principles

These apply to every project, every time.

- **Ship fast.** A working product in 1 week.
- **Solve real problems.** If no one asked for it, reconsider building it.
- **Keep it simple.** Complexity is a cost. Every added feature must earn its place.
- **Manual first, automate later.** Understand the problem before automating the solution.
- **Commit often.** Small, meaningful commits. Not one massive push at the end.
- **Build for the user, not the portfolio.** My goal is always to genuinely helps someone.
- **Document as I go.** You´ll always find a README written by me at the end

---

*This handbook is a living document. It grows as I build more projects and learn what actually works.*
