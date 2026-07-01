# blade-reading / 刃读

AI 时代的狠筛书 skill。

“刃读”不做普通书单推荐，也不按畅销榜、评分、名人推荐堆书。它根据使用者真实处境和人生问题，判断哪些书值得亲自读，哪些只需 AI 总结，并输出评分、不可压缩价值、阅读方式、分类和 30 天阅读顺序。

它的核心问题不是“这本书好不好”，而是：

> 在 AI 已经可以快速解释、总结、陪我讨论的时代，我为什么还要亲自花时间读这本书？

## What It Does

- 建立使用者问题画像，而不是直接泛泛推荐。
- 给候选书按 100 分模型打分。
- 区分精读、慢读、选读、AI 总结即可、暂不优先。
- 解释每本书的不可压缩价值。
- 把书放入固定分类体系，方便形成个人阅读系统。
- 输出最多 3 本主书的 30 天阅读顺序，避免阅读过载。

## Who It Is For

适合这些人：

- 想保护注意力，不想被“必读书单”牵着走。
- 想把阅读变成判断力、行动力、表达力和精神结构训练。
- 不想读鸡汤、伪深度、短期工具教程和“看起来高级但现阶段转化率低”的书。
- 有候选书、待读清单、书架截图或主题方向，需要判断哪些书真值得亲自读。

不适合这些需求：

- 只想要畅销榜、豆瓣高分榜、名人推荐榜。
- 只想越多越好地囤书。
- 希望自动创建或修改微信读书书单。

## Install

### Option 1: Clone into Codex skills

Clone this repository into your Codex skills directory:

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

Try prompts like:

```text
我是大一学生，想提升判断力、商业理解和表达能力。不要鸡汤，不要堆名著，帮我做一份 30 天刃读计划。
```

```text
下面是我的待读清单：活着、原则、置身事内、深度工作、认知觉醒、鞋狗、乡土中国、Python 编程快速上手。帮我判断哪些精读，哪些 AI 总结即可。
```

```text
我想读商业书，但不想看财富心法。帮我筛几本能理解真实交易、现金流、组织、风险和执行的书。
```

More prompts are in [examples/prompts.md](examples/prompts.md).

## Output Preview

```markdown
### 《鞋狗》——菲尔·奈特

- 类型分类：人物传记类 / 商业传记
- 总分：86
- 推荐等级：S
- 阅读方式：普通通读
- 主分类：传记：真实世界中的选择
- 副标签：商业与财富；行动转化；现实复杂性
- 推荐理由：它不是讲“创业精神”的口号书，而是展示一个人如何在现金流压力、供应链风险、组织失控和个人性格限制中持续做选择。
- 不可压缩价值：AI 可以总结耐克发展史，但很难替代你跟随作者经历犹豫、冒险、失误和代价的过程。
- AI 可以替代的部分：公司时间线、人物关系、关键事件概览。
- 必须亲自读的部分：早期现金流压力、关键谈判、组织扩张后的失控感，以及成功背后的代价。
```

See [examples/sample-report.md](examples/sample-report.md) for a longer sample.

## Categories

`blade-reading` uses these fixed main categories:

1. AI 时代必读：心智与判断力
2. 传记：真实世界中的选择
3. 商业与财富：现金流、组织、风险
4. 哲学与思想：价值观与判断力
5. 文学：人性、命运与感受力
6. 框架校准：严肃入门与学科骨架
7. 表达与自媒体：叙事、语言、传播
8. 精神底盘：焦虑、意义、自我控制
9. AI 可替代：只需摘要或选读
10. 暂不优先：以后再说

## Boundary

This skill does not:

- Read private data unless the user pastes it into the conversation.
- Require or store any API key.
- Create, modify, or write to WeRead / 微信读书 booklists.
- Claim that famous, high-rated, or bestselling books are automatically worth reading.

If a user pastes a WeRead shelf, notes list, search result, or candidate list, the skill can use that text to generate a report. It still does not operate the account.

## Development

The core skill is [SKILL.md](SKILL.md). Test prompts live in [evals/evals.json](evals/evals.json).

Suggested quality checks:

- The skill asks for user context before recommending when the prompt is under-specified.
- It separates “worth reading personally” from “AI summary is enough.”
- It gives reasons based on不可压缩价值, not fame or popularity.
- The 30-day plan contains at most 3 main books.

## License

MIT. See [LICENSE](LICENSE).
