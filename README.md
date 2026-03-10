# Deep Research Post Engine

> A Claude Code skill that researches topics across 5–8 real sources, then writes data-backed LinkedIn posts that sound like **you** — not like AI.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blue)](https://code.claude.com)
[![SKILL.md](https://img.shields.io/badge/SKILL.md-open%20standard-purple)](SKILL.md)

---

## What it does

Most AI-written posts are obvious. Same structure. Same phrases. Same hollow "thought leadership."

This skill does it differently:

1. **Researches first** — 8–12 web searches across different angles, reads the top 5–8 articles in full
2. **Extracts hard data** — real numbers, real sources, real expert quotes (no hallucinated stats)
3. **Finds contrarian angles** — what does the data say that surprises people?
4. **Writes in your voice** — builds a voice profile from your best posts, matches sentence length, tone, vocabulary
5. **Anti-slop filter** — 59 AI writing patterns detected and removed before you see the post
6. **Visual report** — opens a browser report with post preview, evidence wall, quality scorecard, and posting guide

---

## Install

```bash
npx skills add FuzulsFriend/deep-research-post-engine
```

Or manually: copy `SKILL.md` into your `.claude/skills/` directory.

**Recommended MCP (for deeper research):**
```bash
claude mcp add read-website-fast -s user -- npx -y @just-every/mcp-read-website-fast
```

---

## Usage

Just ask Claude:

```
Write a LinkedIn post about the ROI of AI coding tools
```

```
Research and write about why most AI startups fail
```

```
Help me post about the GPT-5 announcement for my SaaS audience
```

---

## What you get

```
POST
────────────────────────────────────────
[Full post, ready to paste into LinkedIn]

FIRST COMMENT
────────────────────────────────────────
[2+ source links with titles]

STATS
────────────────────────────────────────
Characters:    1,847 / 3,000
Data points:   8 (all sourced)
AI slop score: 0/10
Voice match:   94%

POSTING GUIDE
────────────────────────────────────────
Best time:     Tuesday 8–9am (your audience's timezone)
Hashtags:      #AITools #SaaS #Productivity
First 60 min:  [engagement plan]
Next post:     [follow-up topic]
```

Plus: a full browser-based visual report with LinkedIn-style post preview, research evidence wall, and quality scorecard.

---

## What's included

```
deep-research-post-engine/
├── SKILL.md                          # Main skill instructions
├── assets/
│   ├── post-template.md              # Output format template
│   └── report-ui.html                # Visual browser report template
└── references/
    ├── voice-profile-template.md     # Voice profiling system + brand guardrails
    ├── anti-slop-patterns.md         # 59 AI writing patterns to remove
    ├── linkedin-algorithm-2026.md    # Current algorithm behavior
    ├── post-structures.md            # Proven post frameworks
    ├── hook-formulas.md              # Hook writing formulas
    ├── engagement-playbook.md        # Post-publish engagement tactics
    └── research-methodology.md      # Research pipeline guidelines
```

---

## Works with

- **Agent Teams mode** — parallel research agents (4x faster)
- **read-website-fast MCP** — full article content, not snippets
- **Apify MCP** — paywalled articles + social media research

Enable Agent Teams:
```bash
export CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1
```

---

## License

MIT — use it, fork it, improve it, share it.

---

*Built with the [SKILL.md open standard](https://github.com/FuzulsFriend/deep-research-post-engine/blob/main/SKILL.md) — works across Claude Code, Codex CLI, Gemini CLI, and 15+ other AI coding assistants.*
