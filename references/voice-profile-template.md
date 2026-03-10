# Voice Profile Template

## How to Use This Template

Read the user's 2-3 shared LinkedIn posts carefully. For each dimension below, extract the pattern you observe. Do not guess or generalize — cite specific evidence from the posts.

If a dimension is unclear from the available posts, mark it as "Insufficient data — need more posts" rather than fabricating a pattern.

---

## Profile Dimensions to Analyze

### 1. Language
What language(s) does the user write in? Is it consistent or mixed?
- Options: Hebrew only / English only / Hebrew primary with English terms / English primary with Hebrew terms / Code-switching between both

### 2. Tone
How does the user "sound" when you read their posts aloud?
- Options: Formal-professional / Casual-conversational / Educator-teacher / Provocative-contrarian / Vulnerable-personal / Authoritative-expert / Humorous-witty / Inspirational-motivational
- Most people are a blend of two (e.g., "Educator-friend" or "Provocative-casual"). Capture the blend.

### 3. Structure
How are their posts organized? Look at the skeleton, not the content.
- Hook type at the top?
- Numbered list or flowing paragraphs?
- Short sections or long blocks?
- Does the post build to a conclusion or scatter insights?
- Where does the CTA land — end, comments, nowhere?

### 4. Emoji Usage
- None: Zero emojis across all posts
- Minimal-structural: 1-3 emojis used as bullet markers or section dividers
- Moderate: 5-10 emojis reinforcing key points or adding personality
- Heavy: 10+ emojis, decorative, used in nearly every line

### 5. Sentence Length
- Short punchy: Most sentences under 10 words. Staccato rhythm.
- Medium: 10-20 words. Conversational flow.
- Long academic: 20+ words. Complex clauses. Formal cadence.
- Mixed intentionally: Alternates short and long for rhythm and emphasis.

### 6. Hook Style
How does the user open their posts? Look at the first 1-2 lines.
- Question: "Did you know...?" / "What if...?"
- Bold claim: States something surprising or contrarian as fact
- Statistic: Opens with a number or data point
- Story: Opens with a personal anecdote or scene
- Contrarian: Challenges a common belief head-on
- Direct statement: No framing, just starts with the point

### 7. CTA Style
How does the user close their posts or prompt engagement?
- Question to audience: Asks readers to share their experience
- "Link in comments": Directs to a resource in the first comment
- "DM me": Invites private conversation
- Poll: Asks readers to vote or choose
- None: Post ends without asking for anything
- Soft close: Ends with a thought that invites reflection but doesn't explicitly ask

### 8. Personality Traits
Describe the user's voice in 3-5 words. These should capture the human behind the posts, not the topic.
- Examples: "Generous, practical, ahead-of-the-curve, curious, direct"
- Anti-examples: "Professional, knowledgeable, experienced" (too generic — could describe anyone)

### 9. Vocabulary Patterns
**Words they gravitate toward:** List specific words or phrases that appear across multiple posts. These are fingerprint words.
**Words they avoid:** Note conspicuous absences — corporate jargon they skip, buzzwords they seem allergic to, formality they dodge.

### 10. Formatting
How does the post look visually on the page?
- Line break frequency (every sentence? every 2-3 sentences? long paragraphs?)
- Bold text usage (for emphasis? for headers? not at all?)
- Bullet points or numbered lists?
- Spacing between sections?
- Use of separators (dashes, dots, lines)?

---

## Brand Guardrails

If the user promotes a product, company, or personal brand, capture these guardrails to prevent mischaracterization in posts.

### Never Call My Product
List names, framings, or categories that are **wrong** for the product. These are terms that might seem close but misrepresent what it does.
- Example: "bookmark manager", "tab organizer", "link saver", "browser extension"

### Always Position As
A short description of how the product/brand should **always** be framed.
- Example: "Universal Capture workspace — one place for everything you save across 10+ platforms"

### Key Differentiator
What makes this product/brand different from the obvious comparisons?
- Example: "Not about browser bookmarks — about the scattered saving behavior across WhatsApp, Instagram saves, screenshots, notes apps, and email-to-self"

### Avoid These Framings
Broader framing mistakes that aren't just naming issues — these are conceptual mischaracterizations.
- Example: "Don't frame as a productivity tool. Frame as solving information anxiety — the feeling that you saved something important but can't find it."

> **Note:** Brand guardrails are optional. If the user doesn't have a product or brand to protect, skip this section in the voice profile. If they do, these guardrails are checked during Phase 4 quality review — every post is scanned against them before delivery.

---

## Example Completed Profile

```
## Voice Profile: [User Name]

**Language:** Hebrew primary. English for technical terms and product names. Never transliterates English words into Hebrew when the Hebrew term exists.

**Tone:** Educator-friend — generous with knowledge, practical rather than theoretical, genuinely curious rather than performatively curious. Never condescending. Treats the reader as a peer who just hasn't seen this yet.

**Structure:** Hook question or bold claim (1-2 lines) → 3-5 numbered insights with brief explanation each → Personal take or "here's what I did" → CTA as question or "link in first comment"

**Emoji:** Moderate — used for structure (numbering, section markers) not decoration. Never puts emoji mid-sentence. Typical: one emoji per numbered item as a bullet marker.

**Sentences:** Short-medium, punchy. Rarely exceeds 15 words. Avoids subordinate clauses. Reads like spoken language, not written language. Uses sentence fragments intentionally.

**Hooks:** Opens with a surprising stat ("87% of teams still do X") or a bold claim ("Your morning standup is wasting 40 minutes a week"). Never opens with "I" or with a generic question.

**CTA:** Question to audience ("What's your approach?") or "Full breakdown in the first comment." Never uses "DM me" or hard sells.

**Personality:** Generous, practical, ahead-of-the-curve, curious, direct

**Vocabulary:**
- Uses: "let me show you", "here's what actually works", "the real question is", "I tested this"
- Avoids: "leverage", "synergy", "best-in-class", "game-changer", "excited to announce", "thrilled", "humbled"

**Formatting:** Heavy line breaks — almost every sentence gets its own line. Short paragraphs (1-3 sentences max). Numbered lists for main content. Bold for key terms within list items. Extra blank line before CTA section.
```

---

## Storage Note

Save the completed profile to `references/voice-profile.md` at runtime. This file is created per-user and is not shipped with the skill. The template (this file) stays unchanged as a reference for how to build new profiles.

When updating an existing profile, read the current `voice-profile.md` first and note which dimensions are changing and why (new posts may reveal patterns that 2-3 posts couldn't).
