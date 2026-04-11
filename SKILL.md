# Double-Loop Learning

A cognitive base that shifts reflection from fixing errors to questioning the assumptions that produce them. When something goes wrong, change the mental model — not just the behavior.

Not tied to any domain. Stacks with domain skills without conflict. Core rules are in `cognitive-protocol.md` (~30 lines, always-on). This file is the full reference framework.

---

## 1. Cognitive Shifts

### Shift 1: Fix the behavior → Question the governing variable

Default: When output is wrong, adjust parameters and retry. "The deploy failed, add more retries."
Target: Identify the assumption or mental model that produced the approach. "We assume deploy-everything-together is correct. Is it?"

- Surface correction = single-loop. Model correction = double-loop.
- Name the governing variable explicitly: "I assumed X, which led to approach Y, which produced failure Z."
- If you can't name the governing variable, you haven't reached the second loop yet.

### Shift 2: Reflect on crisis → Reflect as routine

Default: Reflect only when something breaks. Retrospectives are post-mortem events.
Target: Reflect after every task as cognitive hygiene. Daily practice, not emergency protocol.

- Inamori's 六項精進 and Zeng Guofan's 日课十二条: reflection is brushing teeth, not surgery.
- Frequency beats intensity. One sentence of daily reflection outperforms a quarterly offsite.
- Under pressure, do not skip reflection — accelerate it. Boyd's OODA: orientation (model update) is the fastest competitive loop.

### Shift 3: Reflect within your frame → Bracket your presuppositions

Default: Reflect on what went wrong within your existing mental model. The model itself is invisible.
Target: Suspend presuppositions first. Make the invisible frame visible before analyzing what's inside it.

- Husserl's bracketing: temporarily set aside what you "know" to examine what you actually experienced.
- Mao's 自我批评: examine your own assumptions with the same rigor you apply to others'.
- The most valuable assumptions to question are the ones that feel too obvious to question.

### Shift 4: Reflect from your perspective → Cross-perspective reflection

Default: Ask "what did I get wrong?" from your own viewpoint.
Target: Enter a genuinely different cognitive framework. Ask "what would someone with model X see here?"

- Design Thinking empathy: not just suspend your assumptions, but actively inhabit another's.
- Sima Qian's 太史公曰: after examining each case from inside, step outside and extract the governing pattern.
- The test: can you articulate the other view charitably enough that its holder would agree with your description?

### Shift 5: Reflect without consequence → Close the loop

Default: "We did a retrospective." Nothing changes. The reflection is performed but not enacted.
Target: Every reflection must produce a concrete artifact: updated assumption, confirmed assumption with evidence, or new question.

- Confucius 学而不思则罔，思而不学则殆: reflection without action is as dangerous as action without reflection.
- Track the delta. If nothing changed, that finding ("our reflection process is performative") is the most important output.
- Xunzi's 化性起伪: good judgment is not natural — it is manufactured through deliberate practice. Each closed loop is one rep.

---

## 2. The Inamori Multiplier

Inamori's life equation: Result = Ability x Effort x Mindset (-100 to +100).

Mindset (mental model) is not additive — it is multiplicative. A flawed governing assumption doesn't just introduce error in one place; it multiplies error across every action. This is why double-loop matters more than single-loop: fixing behaviors (effort) while holding a wrong model (mindset = negative) produces negative results faster.

**Implication for agents**: When you detect repeated failures in the same category, do not increase effort (more retries, more detail, more steps). Check the multiplier. The model might be negative.

---

## 3. Anti-Pattern Checklist

1. **Single-loop disguise** — Thinks you're questioning assumptions but actually just adjusting parameters more finely. Fix: name the governing variable. If it hasn't changed, you're still in single-loop.

2. **Infinite reflection** — Endlessly questioning assumptions without returning to action. Fix: set a time-box. Reflection that doesn't close within one cycle is procrastination wearing a thinking hat.

3. **Selective reflection** — Only reflecting on safe assumptions, avoiding core beliefs. Fix: name the assumption you'd be most uncomfortable changing. That one needs examination first.

4. **Crisis-only reflection** — Only reflecting when something goes badly wrong, not as daily practice. Fix: attach reflection to task completion, not to failure. It's a routine, not an alarm.

5. **Performative reflection** — "We did a retrospective" but nothing actually changes. Fix: every reflection must produce an artifact — updated assumption, confirmed assumption, or new question. No artifact = no reflection.

---

## 4. Composing with Domain Skills

### Composition principles

1. Double-Loop Learning operates on **reflection quality** (how you update after results). Domain skills operate on **output format** (what you produce). No conflict.
2. When a domain skill produces a failure, Double-Loop Learning examines whether the failure source is the skill's application (single-loop fix) or the governing assumption behind the approach (double-loop fix).
3. Double-Loop Learning never overrides domain-specific safety constraints. Those are governing variables to be examined, not discarded.

### Stacking examples

- **With coding skill**: After a bug fix, ask: "Did I fix the bug, or the design assumption that made this bug class possible?" If the same category of bug keeps recurring, the model needs updating.
- **With design skill**: After user testing reveals confusion, ask: "Is the interface wrong, or is my model of what the user needs wrong?" Surface redesign vs. requirement re-examination.
- **With writing skill**: After feedback says "this doesn't land," ask: "Is the writing weak, or is my assumption about what the audience cares about wrong?"
- **Standalone**: When the user reports recurring problems in any domain, do not offer the Nth tactical fix. Identify the governing variable and propose a model-level change.

### Relationship to First Principles

**Complementary, different timing.** First Principles audits assumptions BEFORE reasoning. Double-Loop Learning audits assumptions AFTER results arrive. First Principles asks "am I building on solid ground?" Double-Loop asks "did the ground shift, and did I notice?"

**Loading order**: Both load as always-on protocols. First Principles fires at task start; Double-Loop Learning fires at task end and during feedback. No conflict.

---

## 5. Intensity Calibration

### Full intensity — Recurring failures, strategy pivots, feedback that challenges your model

Apply the complete bracket-examine-update cycle. Name the governing variable. Cross-perspective check. Produce an artifact. This is for: repeated bugs in the same category, team patterns that persist despite fixes, personal habits that resist change, any situation where "we've tried everything" is being said.

### Medium intensity — Single failures, routine retrospectives

Run the governing-variable check (Shift 1) and close-the-loop check (Shift 5). Skip full bracketing and cross-perspective if the failure is clearly at the parameter level. This is for: one-off bugs, missed deadlines with obvious causes, minor miscommunications.

### Low intensity — Successful tasks, routine work

Run the self-check silently. One question: "What governing variable drove my approach, and is it still the right one?" Only escalate if the answer surprises you. This is for: completed tasks, routine implementations, anything that went well but might be on autopilot.
