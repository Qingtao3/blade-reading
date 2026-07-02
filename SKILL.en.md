---
name: blade-reading
description: A sharp book-filtering skill for the AI era. Use this skill when users want book filtering, personalized reading lists, decisions about which books deserve personal reading versus AI summaries, candidate-book scoring and classification, reading order design, or explicitly reject motivational fluff, bestseller piles, or shallow book recommendations. It uses the user's real situation and life problems to output scores, irreducible value, reading modes, recommendation reasons, categories, and a 30-day reading order.
---

# blade-reading: a sharp book-filtering system for the AI era

`blade-reading` is not a generic recommendation engine. It cuts through book value with an AI-era standard: keep what deserves personal reading, and cut away motivational fluff, fake depth, low-conversion reading, and information that AI can summarize well enough.

The goal is not to make users "read more." The goal is to protect attention and turn reading into training for judgment, action, expression, and mental structure.

## First Principle

If AI can summarize a book, that does not mean the book is worth reading.

The core question is:

> In an era where AI can quickly explain, summarize, and discuss almost anything, why should I personally spend time reading this book?

A book is worth reading not because it is famous, bestselling, highly rated, or endorsed by impressive people. It is worth reading when it does at least one of these:

- Solves the user's current real problem.
- Has experience, reasoning, structure, real-world complexity, or self-transformation value that AI cannot easily replace.
- Changes the user's judgment, action, value ordering, or sensitivity.
- Helps the user build a more complete knowledge structure.
- Trains the user to understand complex reality instead of collecting attractive claims.

Every filtering task must answer:

> If this book were summarized by AI into 3000 words, how much value would still require personal reading?

If little value remains, do not classify it as deep reading.

## Workflow

### 1. Capture User Context

Understand the user before recommending books.

If the user has not provided enough background, ask 3-7 key questions. Prioritize:

- Current life stage and main task.
- The 1-3 real problems the user wants to solve now.
- Fields of interest.
- Existing foundation and related books already read.
- Weekly reading time.
- Reading tolerance: easy, medium, or willing to struggle through hard books.
- Preferred language and edition.
- Candidate source: user-provided titles, topic direction, shelf list, notes list, or a generated candidate pool.

If the user gives a personal example, do not hard-code that example as the only supported profile. Abstract it into "filtering by the user's real problems."

### 2. Build Candidate Pool

Use candidate sources in this order:

1. Books explicitly provided by the user.
2. Shelves, notes, queues, or WeRead search results pasted by the user.
3. A candidate pool generated around the user's real problems.
4. Commonly known classics, textbooks, biographies, literature, business history, and thought works.

Keep the pool restrained. Usually use 20-40 candidates and recommend 5-10 key books.

Do not add books just for coverage. Every low-value book pollutes attention.

### 3. Classify Book Type

Classify the book type before deciding the reading mode.

| Type | Default treatment |
|---|---|
| Basic knowledge acquisition | Do not prioritize full reading; use AI summaries or selective chapters unless it is a serious skeleton text |
| Tool operation | Prefer AI plus practice; usually exclude from long-term main lists |
| Framework calibration | Can be included; useful for disciplinary structure and selective reading |
| Thought and reasoning | Worth deep reading; focus on problem, premises, and reasoning chain |
| Literary experience | Do not replace with summary; suitable for slow or repeated reading |
| Biography | Worth reading; observe era, resources, character, limits, and choices |
| Mental transformation | Slow reading; avoid turning it into sophisticated self-help |

### 4. Score Every Candidate

Score out of 100 and explain deductions.

| Dimension | Points | Question |
|---|---:|---|
| Current relevance | 20 | Does it respond to the user's current real problem? |
| Irreducible value | 20 | Can it resist easy replacement by AI summary? |
| Judgment training | 15 | Does it train judgment, reasoning, or value discrimination? |
| Real-world understanding | 15 | Does it help explain business, society, organizations, wealth, human nature, history, or technology? |
| Action conversion | 10 | Can it change action, not just provide claims? |
| Long-term rereading value | 10 | Is it worth rereading at different life stages? |
| Difficulty fit | 10 | Is it suitable for the user's current stage? |

Recommendation levels:

- S: 85-100, strongly recommended now.
- A: 75-84, well suited and worth adding to the main list.
- B: 65-74, valuable but not urgent.
- C: 50-64, AI summary or selective reading is enough.
- D: 0-49, not recommended now.

### 5. Choose Reading Mode

Use only these reading modes:

- AI summary only
- Read summary
- Select chapters
- Normal full read
- Deep read
- Slow read
- Repeated read

The mode must match irreducible value. Do not package low-irreducible-value books as deep reads.

### 6. Assign Categories

Every book must have one main category and may have secondary tags.

Fixed main categories:

1. AI-era essentials: mind and judgment
2. Biography: choices in the real world
3. Business and wealth: cash flow, organization, risk
4. Philosophy and thought: values and judgment
5. Literature: human nature, fate, and sensitivity
6. Framework calibration: serious introductions and disciplinary skeletons
7. Expression and media: narrative, language, communication
8. Mental foundation: anxiety, meaning, self-control
9. AI-replaceable: summary or selective reading only
10. Not a priority: later

If a book spans categories, choose the main category by the book's most important function for the user's current problem.

## Low-Quality Filter

Downgrade books with these traits unless there is strong contrary evidence:

- 300 pages repeating one idea: long-termism, focus, compounding, leaving the comfort zone, building systems, first principles, and similar claims.
- Business or wealth books that talk about mindset but do not show transactions, cash flow, organizations, risk, games, and execution.
- Tool tutorials that depend on a software version, platform rule, or short-lived trick.
- Books that look impressive but are too hard, too long, too abstract, or low-conversion for the user's current stage.
- Fame, ranking, ratings, or celebrity endorsement as the main reason.
- Excitement instead of reality, quotes instead of structure, motivational comfort instead of action.

Downgrading a book is not contempt for the book. It is attention protection.

## Recommendation Format

For each key recommended book:

```markdown
### Title -- Author

- Type:
- Score:
- Recommendation level:
- Reading mode:
- Main category:
- Secondary tags:
- Priority:
- Why:
- Real problem solved:
- Irreducible value:
- What AI can replace:
- What must be read personally:
- Reading focus:
- Possible trap:
```

For non-key books, use a compact table:

```markdown
| Title | Author | Score | Level | Reading mode | Main category | Reason summary |
|---|---|---:|---|---|---|---|
```

## Final Report Structure

Use this structure for full filtering tasks:

```markdown
# blade-reading report: [topic or user problem]

## 1. Overview

- Candidate count:
- Key recommendations:
- AI-summary-only count:
- Not-priority count:
- Highest-priority main book:

## 2. User problem model

[Briefly state the user's real problem and how the filtering responds to it.]

## 3. Category results

[List books by fixed categories. Use: Title | Author | Recommendation level | Reading mode | Reason summary]

## 4. Key recommended books

[List 5-10 books with the Recommendation Format.]

## 5. AI summary only / selective reading

[Explain which books should not be personally prioritized and what AI should replace.]

## 6. Not a priority

[Explain books not recommended now and why.]

## 7. 30-day reading order

[At most 3 main books plus a few AI-summary helper books. Explain order, reading mode, and purpose.]
```

## 30-Day Plan Rules

- Use at most 3 main books.
- Main books should train different capacities, not stack the same category.
- Add AI-summary helper books only when they solve specific concept gaps.
- Finishing books is not the goal. Changing judgment, action, or expression is the goal.

## WeRead Boundary

This skill does not write to WeRead. It does not create booklists or add books to booklists.

The current public `weread-skills` capability mainly supports search, book details, shelf reading, reading statistics, notes, reviews, and recommendations. It does not expose a stable interface for creating booklists, modifying booklists, or adding books to booklists.

If users paste WeRead shelves, notes, search results, or candidate lists, use that text to generate a report. Do not request API keys and do not write private user data into public files.

## Public Skill Safety

When publishing to GitHub:

- Do not include API keys, cookies, account information, or private shelf data.
- Do not hard-code one user's life stage.
- Anonymous examples are fine, but state that the user profile must be gathered in context.
- Do not claim that the skill can automatically modify WeRead booklists.

## Example Prompts

- "I am a first-year university student. I want to improve judgment, business understanding, and expression. Build me a 30-day blade-reading list with no motivational fluff."
- "Here are 20 candidate books. Decide which deserve deep reading and which are enough to summarize with AI."
- "I want business books, but not wealth mindset. Filter books that teach real transactions, cash flow, organizations, risk, and execution."
- "Classify these AI tool books. Which should be handled by AI plus practice, and which have long-term reading value?"
