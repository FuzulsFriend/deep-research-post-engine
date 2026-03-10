# Research Methodology — How to Research a Topic in 5-10 Minutes

Every post in the Deep Research Post Engine must be backed by real data, real sources, and real examples. This document defines the exact process for researching a topic efficiently, evaluating source quality, extracting usable data, and structuring findings for post writing.

---

## Step 1: Query Strategy (8-12 searches per topic)

Run these searches in order. Each query type targets a different angle. Together, they give you a 360-degree view of the topic in under 10 minutes.

### Core Queries (run all of these)

| # | Query Template | What it finds | Example (topic: "AI in hiring") |
|---|---|---|---|
| 1 | `[topic] latest news 2026` | Current events, recent developments | `AI in hiring latest news 2026` |
| 2 | `[topic] statistics data research` | Hard numbers, survey results | `AI in hiring statistics data research` |
| 3 | `[topic] study findings percentage` | Academic or industry research | `AI in hiring study findings percentage` |
| 4 | `[topic] misconception myth wrong` | Contrarian angles, debunked beliefs | `AI in hiring misconception myth wrong` |
| 5 | `[topic] expert opinion criticism` | Nuanced takes, dissenting voices | `AI in hiring expert opinion criticism` |
| 6 | `[topic] case study results` | Real-world implementations | `AI in hiring case study results` |
| 7 | `[topic] [user's niche] impact` | Audience-specific relevance | `AI in hiring software engineering impact` |
| 8 | `[topic] future predictions trends` | Forward-looking angles | `AI in hiring future predictions trends` |

### Supplementary Queries (run if core queries leave gaps)

| # | Query Template | What it finds | Example |
|---|---|---|---|
| 9 | `[topic] vs [alternative]` | Comparison angles, trade-offs | `AI screening vs human screening hiring` |
| 10 | `[topic] cost of not [action]` | Stakes and urgency data | `cost of not using AI in hiring` |
| 11 | `"[topic]" site:hbr.org OR site:mckinsey.com` | Premium source targeting | `"AI hiring" site:hbr.org OR site:mckinsey.com` |
| 12 | `[topic] [current year] report pdf` | Downloadable industry reports | `AI hiring 2026 report pdf` |

### Query execution rules
- Run queries 1-8 first. Skim the top 3-5 results from each.
- Only run queries 9-12 if the first 8 didn't yield enough data points (minimum target: 5 usable stats).
- Open and read the 3-5 most promising articles in full. Don't rely on search snippets alone.
- Stop researching after 10 minutes. Diminishing returns hit fast. If you don't have enough after 10 minutes, the topic may not have enough substance for a data-driven post — consider a story-based or opinion-based angle instead.

---

## Step 2: Source Quality Ranking

Not all sources are equal. Use this hierarchy to evaluate every piece of information you find.

### Tier 1 — Primary Sources (use directly, cite confidently)
- Peer-reviewed research papers (arXiv, PubMed, IEEE, ACM)
- Official government data (Bureau of Labor Statistics, Census, EU statistics)
- Company earnings reports, SEC filings, official announcements
- Published surveys with named methodology and sample size

**How to cite:** "A 2025 Stanford study of 2,400 hiring managers found that..."

### Tier 2 — Industry Reports (strong, name the source)
- McKinsey, BCG, Deloitte, Gartner, Forrester
- Pew Research, Harvard Business Review, MIT Sloan
- Industry-specific bodies (e.g., SHRM for HR, IEEE for tech)

**How to cite:** "According to McKinsey's 2025 State of AI report..."

### Tier 3 — Expert Articles (good, verify the expert)
- Named authors with verifiable credentials
- Published on reputable platforms (not anonymous blogs)
- Author has a track record in the field (check LinkedIn, Google Scholar)

**How to cite:** "As [Expert Name], [Title] at [Company], wrote in [Publication]..."

### Tier 4 — News Coverage (good for current events)
- Reuters, AP, Bloomberg, Wall Street Journal, NYT, Financial Times
- Major tech publications: TechCrunch, The Verge, Ars Technica, Wired

**How to cite:** "As reported by Bloomberg in [month year]..."

### Tier 5 — Blog Posts and Opinion Pieces (use cautiously)
- Personal websites, Medium, Substack
- Cross-reference any factual claims with a Tier 1-3 source
- Use for framing and perspective, not for hard data

**How to cite:** Avoid citing directly. If the insight is good, find the underlying source they reference and cite that instead.

### Tier 6 — Social Media Posts (sentiment only)
- Use for gauging public opinion, trending conversations, community sentiment
- NEVER cite a social media post as a factual source
- Acceptable use: "The developer community on X has been debating whether..."

### Tier 7 — AI-Generated Content (NEVER use as a source)
- ChatGPT outputs, AI summaries, AI-written articles
- These can contain hallucinated facts, outdated information, and fabricated citations
- If an article looks AI-generated (generic, no specific author, no sources cited), skip it entirely

---

## Step 3: Data Extraction Rules

When reading an article, extract information using these specific rules.

### What to extract
- **Specific numbers:** percentages, dollar amounts, timelines, growth rates, sample sizes
- **Named sources:** institution name, author name, year of publication
- **Direct quotes:** from named experts with titles and affiliations
- **Contrarian findings:** anything that contradicts conventional wisdom
- **Real examples:** named companies, specific products, concrete outcomes

### Specificity requirements
Every data point must include:
1. **The number itself** — "73%" not "most"
2. **Who measured it** — "Gartner" not "a study"
3. **When** — "2025" not "recently"
4. **Sample or scope** — "2,400 hiring managers" not "people surveyed"

**Good:** "A 2025 Gartner survey of 1,800 HR leaders found that 63% have adopted at least one AI tool in their hiring pipeline."

**Bad:** "Studies show most HR teams are now using AI."

### Freshness rules
- Data from the current year or previous year: use freely
- Data 18-36 months old: usable, but flag with context ("As of 2024...")
- Data older than 36 months: flag as **[DATED]** — only use if no newer data exists, and acknowledge the age explicitly
- Exception: foundational research (e.g., Kahneman's prospect theory) is timeless — no need to flag age

### Verification rules
- **Single-source claims:** If only one source makes a specific claim, note it: "According to [source]..." (do not present it as established fact)
- **Surprising claims (>2x what you'd expect):** Cross-reference with a second source before including. If no second source exists, include with a hedge: "One study suggests..."
- **Round numbers from non-research sources ("90% of startups fail"):** These are often folk wisdom, not data. Find the original study or drop the claim.
- **Quotes:** Verify the person exists (quick LinkedIn/Google check), verify they actually said it (find the original interview/article). Misattributed quotes destroy credibility.

---

## Step 4: Tool Fallback Chain

Use these tools in order of preference. Each has different strengths and limitations.

### 1. read-website-fast MCP (preferred)
- **Best for:** Reading full article content quickly
- **Strengths:** Fast, reliable, handles most public sites
- **Limitations:** May not work on heavily paywalled sites
- **Use when:** You have a specific URL to read

### 2. WebFetch (built-in)
- **Best for:** Public URLs, API endpoints
- **Strengths:** Works without external dependencies
- **Limitations:** May truncate very long articles, can struggle with JS-heavy sites
- **Use when:** read-website-fast is unavailable or fails

### 3. Apify RAG Web Browser (if available)
- **Best for:** Paywalled content, JavaScript-rendered pages, complex sites
- **Strengths:** Handles sites that block simpler tools
- **Limitations:** Slower, uses API credits
- **Use when:** First two tools fail on a specific URL

### 4. WebSearch (built-in fallback)
- **Best for:** Finding URLs, getting search snippets
- **Strengths:** Always available
- **Limitations:** Returns snippets only — not full article content
- **Use when:** You need to find articles (then read them with tools 1-3), or when no other tool can access the content

### 5. User-provided content (last resort)
- **When:** All automated tools fail to access a specific source
- **Action:** Ask the user: "I couldn't access [URL]. Could you paste the relevant section? I'm looking for [specific data point]."
- **Use sparingly:** This should happen rarely. Most public content is accessible through tools 1-4.

### Handling partial access
If an article can't be fully read (paywall, truncation, JS rendering issue):
- Note it in the research brief: "Source partially accessed — data point verified from search snippet only"
- Use the data point with slightly lower confidence
- Try to find a second source that corroborates the same claim

---

## Step 5: Research Brief Format

After completing research, compile findings into this structured format. This is internal — it is NOT shown to the user. It feeds into the post writing process.

```
TOPIC: [the topic being researched]
SEARCHED: [number of queries run]
ARTICLES READ: [number of articles fully or partially read]
RESEARCH TIME: [approximate minutes spent]

KEY DATA POINTS:
1. [specific stat or finding] — Source: [name], [year], [sample/scope if available]
2. [specific stat or finding] — Source: [name], [year], [sample/scope if available]
3. [specific stat or finding] — Source: [name], [year], [sample/scope if available]
4. [specific stat or finding] — Source: [name], [year], [sample/scope if available]
5. [specific stat or finding] — Source: [name], [year], [sample/scope if available]
[minimum 5, aim for 8-10]

CONTRARIAN ANGLES:
- Common belief: [what most people think]
  Reality: [what the data actually shows]
  Source: [name], [year]
- Common belief: [what most people think]
  Reality: [what the data actually shows]
  Source: [name], [year]

EXPERT QUOTES:
- "[exact quote]" — [Expert Name], [Title at Company], Source: [publication], [year]
- "[exact quote]" — [Expert Name], [Title at Company], Source: [publication], [year]

REAL-WORLD EXAMPLES:
- [Company/person]: [what they did] → [measurable result]
- [Company/person]: [what they did] → [measurable result]

AUDIENCE RELEVANCE:
- [How this topic connects to the user's professional niche]
- [Why their specific audience would care about this]
- [What action their audience could take based on this]

BEST HOOK CANDIDATES:
- Stat hook: [strongest stat that could open the post]
- Contrarian hook: [strongest "conventional wisdom is wrong" angle]
- Story hook: [if a case study is compelling enough to lead with]

GAPS:
- [What we couldn't find data on]
- [Questions that remain unanswered]
- [Areas where only weak/dated sources exist]
```

### Minimum quality thresholds

A research brief is ready for post writing when it has:
- At least **5 specific data points** with named sources
- At least **1 contrarian angle** backed by data
- At least **1 expert quote** from a named, verifiable person
- At least **1 real-world example** with a measurable outcome
- A clear connection to the **user's audience**

If the brief doesn't meet these thresholds after 10 minutes of research:
1. Try 2-3 more targeted queries focused on the weakest areas
2. If still insufficient, tell the user: "Research on [topic] yielded limited data. I found [X data points] but couldn't find [what's missing]. Options: (a) proceed with a more opinion/story-based post, (b) try a related angle like [suggestion], or (c) provide me with specific sources you've seen on this topic."

---

## Common Research Pitfalls

### Pitfall 1: Relying on a single blockbuster stat
One amazing stat is not enough. If the post's entire argument rests on one number and that number turns out to be wrong or miscontextualized, the post collapses. Always have at least 3 supporting data points.

### Pitfall 2: Confusing correlation with causation
"Companies that use AI in hiring see 40% faster time-to-fill" does not mean AI caused the speed improvement. It may mean that companies with better processes overall also happen to adopt AI. Note the difference in how you frame the stat.

### Pitfall 3: Cherry-picking data
If you find one study saying X and three studies saying the opposite, you cannot cite only the one. Either present the nuance ("While one study found X, the majority of research points to Y") or drop the outlier claim.

### Pitfall 4: Using undated or unsourced stats
"80% of employees prefer remote work" — who said this? When? What was the sample? If you can't answer all three, don't use the stat. Vague stats are worse than no stats because they signal laziness to informed readers.

### Pitfall 5: Researching too long
Perfectionism in research leads to never publishing. Set a hard 10-minute timer. Use what you have. A post with 5 solid data points published today beats a post with 15 data points published never.
