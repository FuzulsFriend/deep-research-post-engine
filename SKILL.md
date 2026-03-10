---
name: deep-research-post-engine
description: >
  Researches topics deeply across multiple sources, then writes data-backed
  LinkedIn posts that match your writing voice. Use when asked to "write a
  LinkedIn post", "create social media content", "help me post about",
  "research and write about", "draft a post on", or "write content for
  LinkedIn". Also triggers on "help me grow on LinkedIn", "LinkedIn content
  strategy", or "write a thought leadership post". Produces research-first
  content with real sources — not generic AI writing.
license: MIT
metadata:
  author: tomer-ezri
  version: "1.0.0"
  category: content-creation
  tags: [linkedin, content, research, social-media, writing]
---

# Deep Research Post Engine

Research topics deeply, then write data-backed LinkedIn posts that sound like you — not like AI.

---

## Onboarding

### First-Time Detection

Ask: **"Have you used Deep Research Post Engine before?"**

If new user, show:

```
Welcome to Deep Research Post Engine!

This skill researches your topic across 5-8 real articles, extracts hard data
and contrarian angles, then writes a LinkedIn post in YOUR voice — not generic
AI writing.

What makes it different:
  - Real research with real sources (not hallucinated stats)
  - Anti-slop filter catches "navigate", "landscape", "game-changer" etc.
  - Your voice profile ensures posts sound like YOU wrote them
  - 3 angle options so you pick the framing

Let's get you set up.
```

### Install Dependencies

```
RECOMMENDED:
  read-website-fast MCP (reads full articles, not just snippets)
    Install: claude mcp add read-website-fast -s user -- npx -y @just-every/mcp-read-website-fast
    Repo:    https://github.com/just-every/mcp-read-website-fast

OPTIONAL:
  Apify MCP (for paywalled articles + social media research)
    Install: claude mcp add apify -e APIFY_TOKEN=your_token -- npx -y @apify/actors-mcp-server
    Repo:    https://github.com/apify/apify-mcp-server

SPEED BOOST:
  Agent Teams mode lets multiple Claude sessions work together — one leads, others research in parallel.
  Enable: export CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1
  Docs:   https://code.claude.com/docs/en/agent-teams
```

### First-Time Setup

1. Ask user for **2-3 of their best-performing LinkedIn posts** (paste full text)
2. Ask for their **niche** (e.g., "AI in healthcare", "B2B SaaS growth")
3. Ask for their **target audience** (e.g., "CTOs at mid-market companies")
4. Ask for their **language preference** (English, Hebrew, bilingual, etc.)
5. Build a voice profile from their posts — save to `references/voice-profile-template.md`
6. Ask (optional): **Do you have an existing content calendar or marketing strategy doc?** If yes, read it and align post topics with the existing plan.

Voice profile captures: sentence length, punctuation habits, emoji usage, vocabulary level, signature phrases, formatting preferences (bullets vs paragraphs, line breaks, bold usage), and tone (direct, conversational, authoritative, vulnerable).

---

## Tool Detection + Fallback Chain

At the start of **every run**, detect available tools and announce them:

### Web Reading (pick first available)
1. **read-website-fast MCP** — Best. Reads full article content, not just snippets.
2. **WebFetch** (built-in) — Adequate. Works for most public articles.
3. **WebSearch** (built-in) — Minimum. Search snippets only, no full article reads.

### Optional Enhancements
- **Apify RAG MCP** — Unlocks paywalled articles and social media post research.
- **Agent Teams** — Enables parallel research (4 agents at once instead of sequential).

### Announce to User

If read-website-fast is available:
```
Tools: read-website-fast (deep article reading), WebSearch. Ready for full research.
```

If only built-in tools:
```
Tools: WebFetch + WebSearch (basic). Install read-website-fast for deeper research:
  claude mcp add read-website-fast -s user -- npx -y @just-every/mcp-read-website-fast
```

---

## Agent Teams Roles

When Agent Teams is enabled, spin up parallel research agents:

| Role | Agent Name | Job |
|------|-----------|-----|
| Orchestrator | main | Coordinates research, assembles final post, talks to user |
| Trend Scanner | research-trends | Searches for latest news and developments on the topic |
| Data Hunter | research-data | Finds statistics, studies, hard numbers with sources |
| Contrarian Finder | research-contrarian | Finds what most people get wrong, opposing viewpoints |
| Audience Connector | research-audience | Connects the topic to the user's specific niche and audience |

**When Agent Teams is NOT available:** Run all 4 research roles sequentially in the main session. Same research depth, just slower.

---

## Research-to-Post Pipeline

### Phase 1: TOPIC RESEARCH (5-10 minutes)

1. User provides topic + optional angle
2. Run **8-12 web searches** across different angles:
   - "[topic] latest news 2026"
   - "[topic] statistics data"
   - "[topic] controversy debate"
   - "[topic] expert opinion"
   - "[topic] [user's niche] impact"
   - "[topic] what most people get wrong"
   - "[topic] case study results"
   - "[topic] future predictions"
3. Read the **top 5-8 articles** fully (use best available reading tool)
4. Extract from each article:
   - Hard data points (numbers, percentages, study results)
   - Direct quotes from named experts
   - Contrarian or surprising findings
   - Connection points to user's niche
5. Compile an internal research brief (do NOT show raw brief to user)

### Phase 2: ANGLE SELECTION

Present **3 angles** to the user:

**Angle 1 — Contrarian:**
"The data says the opposite of what everyone thinks..."
Best when: research uncovered surprising findings that challenge conventional wisdom.

**Angle 2 — Analysis:**
"Here's what [development] means for [your audience]..."
Best when: there is a recent event or trend with non-obvious implications.

**Angle 3 — Personal Experiment:**
"I tested [topic] — here's what happened..."
Best when: user has hands-on experience or the topic lends itself to a "try it yourself" frame.

Include a **recommendation** based on shareability and data strength. User picks an angle or suggests their own.

### Phase 3: POST WRITING

Apply the voice profile from `references/voice-profile-template.md`, then write using this structure optimized for LinkedIn algorithm 2026:

**Hook** (first 2 lines) — Stop the scroll. Use a bold claim, surprising stat, or pattern interrupt. These lines appear before "...see more" so they must earn the click.

**Setup** (2-3 lines) — Frame the problem or context. Why should the reader care right now?

**Meat** (bulk of post) — The insight, data, or story. Embed real data points with attribution. Use short paragraphs (1-2 sentences each) for mobile readability.

**Pivot** (1-2 lines) — Your personal take or lesson. This is where the user's voice matters most.

**CTA** (final line) — A question that invites comments, or "Link in comments" if sharing a resource.

**Rules:**
- Embed data points with real, named sources inline
- Optimize for dwell time (readers should slow down and read, not skim)
- Stay under **3,000 characters** (LinkedIn's sweet spot)
- Write a separate **"first comment"** containing links, additional context, or thread continuation
- First comment must include at least 2 source links with titles (not just raw URLs)

### Phase 4: QUALITY CHECK (Anti-Slop Filter)

Run every post through these checks before presenting to user:

1. **AI slop scan** — Flag and remove words/phrases from `references/anti-slop-patterns.md`. Common offenders: "navigate", "landscape", "game-changer", "paradigm shift", "in today's world", "let's dive in", "at the end of the day", "it's important to note".

2. **Source verification** — Every data point must have a real, checkable source. No "studies show" without naming the study. No "experts say" without naming the expert.

3. **Voice match** — Compare sentence length, tone, and vocabulary against the voice profile. Flag any sections that drift toward generic LinkedIn-speak.

4. **Expert test** — Ask: "Would someone with 10 years of experience in this field write this, or would they cringe?" Remove anything that fails this test.

5. **Deliver 2 versions:**
   - **Standard** — Polished, professional, ready to post
   - **Punchier** — Shorter sentences, bolder claims, more personality

6. **Brand guardrails check** — If the voice profile has brand guardrails, verify the post doesn't violate any of them. Check product naming, positioning, and framing against the guardrails list.

### Phase 5: POSTING GUIDE

After the user picks their preferred version, provide:

- **Best time to post** — Based on their audience's likely timezone and LinkedIn engagement data
- **Image/visual suggestion** — What type of visual would increase engagement (chart, photo, carousel, none)
- **Hashtags** — 3-5 relevant hashtags (not spammy, not too broad)
- **First-60-minutes plan** — What to do after posting: reply to every comment, engage on 5 other posts in your niche, share to relevant groups
- **Follow-up post topic** — A natural next post that builds on this one's momentum

### Phase 6: VISUAL REPORT (browser preview)

Generate a self-contained HTML report and open it in the user's browser.

1. Create a JSON object with all post data (see schema below)
2. Read the HTML template from `assets/report-ui.html`
3. Replace `{{REPORT_DATA}}` with the JSON string
4. Save to `./deep-research-report-[topic-slug]-[date].html`
5. Open in browser: `open` (macOS), `xdg-open` (Linux), `start` (Windows)
6. Tell the user: "Visual report saved to [path] and opened in your browser."

JSON schema for the report:
```json
{
  "meta": {
    "topic": "string",
    "niche": "string",
    "audience": "string",
    "date": "YYYY-MM-DD",
    "toolsUsed": ["string"]
  },
  "research": {
    "articlesRead": 0,
    "dataPoints": [
      { "fact": "string", "source": "string", "url": "string" }
    ],
    "searchQueries": ["string"]
  },
  "angles": [
    { "name": "string", "type": "contrarian|analysis|experiment", "description": "string", "recommended": true }
  ],
  "selectedAngle": "string",
  "posts": {
    "standard": { "text": "string", "charCount": 0 },
    "punchier": { "text": "string", "charCount": 0 }
  },
  "firstComment": "string",
  "quality": {
    "slopScore": 0,
    "slopFlags": ["string"],
    "voiceMatch": 0,
    "expertTestPass": true
  },
  "postingGuide": {
    "bestTime": "string",
    "visual": "string",
    "hashtags": ["string"],
    "first60min": "string",
    "followUpTopic": "string"
  }
}
```

---

## Output Format

Final output includes these sections (copy-paste ready):

```
POST
────────────────────────────────────────
[Full post text, ready to paste into LinkedIn]

FIRST COMMENT
────────────────────────────────────────
[Links, sources, additional context]

STATS
────────────────────────────────────────
Characters:    [count] / 3,000
Data points:   [count] (all sourced)
AI slop score: [X/10] (0 = fully human-sounding, 10 = AI-obvious)
Voice match:   [percentage] alignment with your profile

POSTING GUIDE
────────────────────────────────────────
Best time:     [day + time range]
Visual:        [suggestion]
Hashtags:      [3-5 hashtags]
First 60 min:  [engagement plan]
Next post:     [follow-up topic idea]
```

See `assets/post-template.md` for the full template with examples.

---

## Troubleshooting

**"Skill didn't research anything"**
Check if web search tools are available. Run tool detection again. If no web tools work, paste article URLs manually and the skill will work from those.

**"Post sounds generic"**
Voice profile may be missing or outdated. Re-run first-time setup with fresh LinkedIn post examples. The more posts you provide, the better the voice match.

**"No data points found"**
Topic may be too niche or too new for published data. Try broader search terms, or pivot to a "personal experiment" angle that relies on your own experience instead of external data.

**"Post is too long"**
Reduce from 5 key insights to 3. Cut the setup section to 1 line. Remove the weakest data point. Ask the skill to rewrite with a stricter character limit.

**"Sources seem wrong"**
Report which data point looks off. The skill will re-search that specific claim and either find a valid source or remove it. Never publish unverified stats.
