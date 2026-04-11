# Double-Loop Learning | 双环思考

A cognitive base that shifts reflection from fixing errors to questioning the assumptions that produce them. Works with any LLM agent — Claude, GPT, Gemini, or custom frameworks.

让 AI agent 从"修正错误"转向"质疑产生错误的假设"。适用于任何 LLM agent — Claude、GPT、Gemini 或自定义框架。

---

## What it does | 它做什么

Most AI agents operate in single-loop mode: when something fails, they adjust the behavior and try again. Double-Loop Learning adds a meta-reflection layer that examines the mental models, assumptions, and governing variables behind the behavior — and changes those when needed.

大多数 AI agent 运行在单环模式：出错时调整行为再试。双环思考增加了一个元反思层——审视行为背后的心智模型、假设和控制变量，在必要时改变这些根源。

### Before (default agent) | 安装前

> "Our deploys keep failing. How do we fix our CI pipeline?"
>
> "Here are 8 steps to harden your CI pipeline: pin dependency versions, add retry logic, increase timeout buffers, add smoke tests..."

### After (with Double-Loop Learning) | 安装后

> "The question assumes the CI pipeline is the problem. Your deploys fail repeatedly, and each time you patch the symptom. The pattern suggests the governing assumption — 'deploy everything together on a fixed schedule' — is the source. What if you decoupled deploy units and triggered on readiness instead of schedule? That changes the system so the class of failure can't recur."

---

## How it works | 工作原理

**Core cognitive shift**: From "fix the error" to "question the assumption that produced the error."

核心认知转换：从"修正错误"到"质疑产生错误的假设"。

| Default mode | Target mode |
|---|---|
| Correct the behavior 修正行为 | Question the governing variable that drove the behavior 质疑驱动行为的控制变量 |
| Reflect only when things break 出问题才反思 | Reflect as daily cognitive hygiene 反思是日常认知卫生 |
| Suspend reflection when time-pressured 时间紧就跳过反思 | Accelerate reflection under pressure — OODA Orientation 压力下加速反思——OODA 定向 |
| Reflect on safe topics only 只反思安全话题 | Bracket presuppositions — examine what you'd rather not 悬置预设——审视你不愿审视的 |
| "We did a retrospective" 我们做了复盘 | "What actually changed as a result?" 因此到底改变了什么？ |

**Five anti-patterns** that catch fake double-loop reflection:

五个反模式，捕捉伪双环反思：

| Anti-pattern 反模式 | Description 描述 |
|---|---|
| Single-loop disguise 单环伪装 | Thinks you're questioning assumptions but actually just adjusting parameters more finely 以为在质疑假设，实际只是更精细地调参数 |
| Infinite reflection 无限反思 | Endlessly questioning assumptions without returning to action 无止境地质疑假设，不回到行动 |
| Selective reflection 选择性反思 | Only reflecting on safe assumptions, avoiding core beliefs 只反思安全假设，回避核心信念 |
| Crisis-only reflection 危机反思 | Only reflecting when something goes badly wrong, not as daily practice 只在严重出错时反思，而非日常练习 |
| Performative reflection 表演性反思 | "We did a retrospective" but nothing actually changes "我们做了复盘"但实际什么都没变 |

---

## Installation | 安装

### Claude Code
```bash
cp cognitive-protocol.md ~/.claude/double-loop-learning.md
echo '@~/.claude/double-loop-learning.md' >> ~/.claude/CLAUDE.md
```

### Codex
```bash
cat cognitive-protocol.md >> AGENTS.md
```

### Gemini
Paste `cognitive-protocol.md` into `system_instruction`.

将 `cognitive-protocol.md` 内容粘贴到 `system_instruction` 中。

### Cursor
```bash
cat cognitive-protocol.md >> .cursorrules
```

### Any agent | 任何 agent
Inject `cognitive-protocol.md` (~30 lines) into the system prompt. See [`install/generic.md`](install/generic.md) for details.

将 `cognitive-protocol.md`（约 30 行）注入系统提示词。详见 [`install/generic.md`](install/generic.md)。

---

## File structure | 文件结构

```
double-loop-learning/
├── README.md                  ← You are here / 你在这里
├── cognitive-protocol.md      ← Core rules (~30 lines, always-on) / 核心规则（约 30 行，始终激活）
├── SKILL.md                   ← Full framework reference / 完整框架参考
├── anti-patterns.md           ← Detailed anti-pattern guide / 反模式详解
├── examples.md                ← Before/after scenarios / 前后对比示例
└── install/
    ├── claude-code.md         ← Claude Code installation / Claude Code 安装指南
    ├── codex.md               ← Codex installation / Codex 安装指南
    ├── gemini.md              ← Gemini installation / Gemini 安装指南
    └── generic.md             ← Universal guide / 通用安装指南
```

---

## Composability | 可组合性

Double-Loop Learning is a **cognitive base** — it changes how the agent reflects, not what it produces. It stacks cleanly with any domain skill (coding, design, writing, analysis) because it operates at a different layer.

双环思考是一个**认知底座**——它改变 agent 的反思方式，而非产出内容。它与任何领域技能无冲突地叠加，因为它运行在不同的层级。

### Relationship to other cognitive bases | 与其他认知底座的关系

| Layer 层级 | What it governs 管辖范围 | Example 示例 |
|---|---|---|
| First Principles 第一性原理 | Input quality — what foundations reasoning is built on 输入质量 | "Audit assumptions before solving" 先审计假设 |
| Double-Loop Learning 双环思考 | Reflection quality — whether you update the model, not just the output 反思质量 | "Question the assumption that produced the error" 质疑产生错误的假设 |
| Systems Thinking 系统思考 | Structure quality — whether you see the whole system 结构质量 | "Trace feedback loops and delays" 追踪反馈环和延迟 |

All load as always-on cognitive protocols. No conflicts. First Principles audits before reasoning; Double-Loop Learning audits after results arrive; Systems Thinking maps the structure throughout.

三者同时加载，始终激活，互不冲突。第一性原理在推理前审计；双环思考在结果到达后审计；系统思考全程映射结构。

---

## Theoretical foundation | 理论基础

Synthesized from nine intellectual traditions:

综合自九个思想传统：

- **Argyris/Schon**: Single-loop (correct behavior) vs double-loop (correct underlying assumptions). The foundational distinction.
- **Boyd's OODA Orientation**: Real-time destruction and reconstruction of mental models in competitive environments. Reflection is not slow — it's the fastest loop.
- **Husserl's phenomenological bracketing**: Suspend all presuppositions to examine experience directly. The method for reaching assumptions you didn't know you had.
- **Mao's 批评与自我批评**: Meta-reflection as institutionalized daily discipline, not crisis response. Reflection works only as habit.
- **Xunzi's 化性起伪**: Default patterns are untrustworthy — good judgment is manufactured through deliberate practice. You are not naturally reflective; you become reflective.
- **Design Thinking empathy**: Not just suspend your own assumptions, but actively enter others' cognitive frameworks. Double-loop across perspectives.
- **Inamori's 六项精进 + Zeng Guofan's 日课十二条**: Daily reflection as cognitive hygiene, like brushing teeth. Frequency over intensity.
- **Inamori's life equation**: Mindset is a multiplier variable from -100 to +100. A wrong mental model doesn't just add error — it multiplies it across everything.
- **Confucius 学而不思则罔，思而不学则殆**: Learning and reflection are permanent oscillation, not sequential phases. Stop one, the other degrades.
- **Sima Qian's 太史公曰**: Cross-case meta-commentary methodology. After examining each case, step back and extract the governing pattern.

The cognitive protocol strips all theory and translates these ideas into executable instructions for any reasoning agent.

认知协议剥离了所有理论，将这些思想转译为任何推理 agent 可执行的指令。

---

## All Cognitive Bases

Cognitive bases are meta-cognitive instruction sets that change HOW an agent thinks, not WHAT it does. Each one targets a different cognitive axis. Mix and match.

| Cognitive Base | What it changes |
|---|---|
| [First Principles](https://github.com/d-wwei/first-principles) | Reason from verified foundations, not inherited conventions |
| [Results-Driven](https://github.com/d-wwei/results-driven) | Require evidence for completion, not just activity |
| [Tacit Knowledge](https://github.com/d-wwei/tacit-knowledge) | Think like an experienced practitioner |
| [Attention Allocation](https://github.com/d-wwei/attention-allocation) | Find and concentrate on the ONE binding constraint |
| [Bayesian Reasoning](https://github.com/d-wwei/bayesian-reasoning) | Calibrated probability thinking, not binary judgments |
| [Constraint as Catalyst](https://github.com/d-wwei/constraint-as-catalyst) | Turn constraints into innovation catalysts |
| [Conviction Override](https://github.com/d-wwei/conviction-override) | Override rational caution when obstacles are convention, not physics |
| [Cross-Domain Connector](https://github.com/d-wwei/cross-domain-connector) | Detect structural isomorphisms across disciplines |
| [Dialectical Thinking](https://github.com/d-wwei/dialectical-thinking) | Synthesize through contradictions (矛盾论) |
| [Frame Auditing](https://github.com/d-wwei/frame-auditing) | Detect and transcend invisible analytical frames |
| [Interactive Cognition](https://github.com/d-wwei/interactive-cognition) | Model others' cognition and manage information flow |
| [Inversion Thinking](https://github.com/d-wwei/inversion-thinking) | Map failure modes first, then avoid them |
| [Motivation Audit](https://github.com/d-wwei/motivation-audit) | Audit motivational drivers before analysis (正心诚意) |
| [Non-Attachment](https://github.com/d-wwei/non-attachment) | Radical cognitive freedom — use frameworks without fusing |
| [Principled Action](https://github.com/d-wwei/principled-action) | Unify knowing and doing through practice-theory spirals (知行合一) |
| [Second-Order Thinking](https://github.com/d-wwei/second-order-thinking) | Trace consequences beyond first-order effects |
| [Systems Thinking](https://github.com/d-wwei/systems-thinking) | Feedback-driven structural analysis, not linear cause-effect |
| [Temporal Wisdom](https://github.com/d-wwei/temporal-wisdom) | Make time your ally — compound effects and phase awareness |
| [Cognitive Base Creator](https://github.com/d-wwei/cognitive-base-creator) | Generate new cognitive bases from any thinking framework |

---

## License

MIT
