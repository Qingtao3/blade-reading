# blade-reading

A sharp book-filtering skill for the AI era.

`blade-reading` does not generate generic reading lists, bestseller lists, rating-based lists, or celebrity-endorsed piles of books. It starts from the user's real situation and life problems, then decides which books deserve personal reading, which are enough to summarize with AI, and outputs scores, irreducible value, reading modes, categories, and a 30-day reading order.

Its core question is not "Is this book good?"

It is:

> In an era where AI can quickly explain, summarize, and discuss almost anything, why should I personally spend time reading this book?

## What It Does

- Builds a user problem profile before recommending books.
- Scores candidate books with a 100-point model.
- Separates deep reading, slow reading, selective reading, AI-summary-only, and not-priority books.
- Explains each book's irreducible value.
- Places books into a fixed category system for a personal reading structure.
- Produces a 30-day reading order with at most 3 main books to avoid overload.

## Who It Is For

Good fit:

- People who want to protect attention instead of following "must-read" lists.
- People who want reading to train judgment, action, expression, and mental structure.
- People who dislike motivational fluff, fake depth, short-lived tool tutorials, and books that look impressive but are hard to convert into action.
- People with candidate books, reading queues, shelf screenshots, or topics who need to decide what is truly worth reading.

Not a good fit:

- Users who only want bestseller rankings, rating rankings, or celebrity booklists.
- Users who want to collect as many books as possible.
- Users who expect automatic creation or editing of WeRead booklists.

## Install

### Option 1: Clone into Codex skills

```powershell
git clone https://github.com/Qingtao3/blade-reading.git "$env:USERPROFILE\.codex\skills\blade-reading"
```

Restart Codex after installing.

### Option 2: Manual install

Copy this repository folder to:

```text
C:\Users\<you>\.codex\skills\blade-reading
```

Then restart Codex.

### Option 3: Install from a `.skill` package

If you have a packaged `blade-reading.skill` file, import or unpack it into your Codex skills directory according to your Codex setup. The package should contain `SKILL.md`, `README.md`, `LICENSE`, `evals/`, and `examples/`.

## Quick Start

```text
I am a first-year university student. I want to improve judgment, business understanding, and expression. No motivational fluff and no impressive-looking classic pile. Build me a 30-day blade-reading plan.
```

```text
Here is my reading queue: Shoe Dog, Principles, The Making of the Modern Chinese State, Deep Work, Outliers, To Live, From Third World to First, Automate the Boring Stuff with Python. Which should I read deeply, and which are enough to summarize with AI?
```

```text
I want business books, but not wealth mindset or success formulas. Filter books that help me understand real transactions, cash flow, organizations, risk, and execution.
```

More prompts are in [examples/prompts.en.md](examples/prompts.en.md).

## Output Preview

```markdown
### Shoe Dog -- Phil Knight

- Type: biography / business biography
- Score: 86
- Recommendation level: S
- Reading mode: normal full read
- Main category: Biography: choices in the real world
- Secondary tags: business and wealth; action conversion; real-world complexity
- Why: This is not a slogan book about entrepreneurship. It shows how a person keeps making choices under cash-flow pressure, supply-chain risk, organizational disorder, and personal limitations.
- Irreducible value: AI can summarize Nike's history, but it cannot replace following the author's uncertainty, risk, mistakes, and costs across the journey.
- AI can replace: company timeline, relationship map, event overview.
- Must read personally: early cash-flow pressure, key negotiations, loss of control during growth, and the cost behind success.
```

See [examples/sample-report.en.md](examples/sample-report.en.md) for a longer sample.

## Categories

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

## Boundary

This skill does not:

- Read private data unless the user pastes it into the conversation.
- Require or store any API key.
- Create, modify, or write to WeRead / 微信读书 booklists.
- Claim that famous, high-rated, or bestselling books are automatically worth reading.

If a user pastes a WeRead shelf, notes list, search result, or candidate list, the skill can use that text to generate a report. It still does not operate the account.

## Development

The active skill entrypoint is [SKILL.md](SKILL.md). Test prompts live in [evals/evals.json](evals/evals.json).

Suggested quality checks:

- The skill asks for user context before recommending when the prompt is under-specified.
- It separates "worth reading personally" from "AI summary is enough."
- It gives reasons based on irreducible value, not fame or popularity.
- The 30-day plan contains at most 3 main books.

## License

MIT. See [LICENSE](LICENSE).
