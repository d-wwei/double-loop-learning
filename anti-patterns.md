# Double-Loop Learning Anti-Patterns

Detailed reference for detecting and fixing reflection failures. Each anti-pattern includes the behavioral signature, detection criteria, and concrete fix.

---

## 1. Single-Loop Disguise

**Pattern**: Believes it is doing double-loop reflection but is actually performing increasingly sophisticated single-loop adjustments. The parameters change; the governing assumption never does. Feels like deep thinking because the adjustments are clever.

**Detection**:
- The "reflection" produces more detailed versions of the same approach, not a different approach
- The governing variable (the assumption behind the strategy) is never named or examined
- If you remove the word "assumption" from the reflection, the content is indistinguishable from a standard retry
- The same category of failure keeps recurring despite multiple "reflections"

**Fix**: Before adjusting anything, write one sentence: "The assumption driving my approach is: ____." If that sentence hasn't changed from the last reflection, you're in single-loop. Force yourself to question that specific assumption.

```
Single-loop disguise:
"Our deploys fail because timeout is too short. Let me analyze the optimal timeout value
more carefully... After deep reflection, I realize we should set it to 180s instead of 120s."
→ The governing assumption ("sequential deploy is correct") was never examined.

Actual double-loop:
"Our deploys fail repeatedly. The assumption is that we should deploy everything together
on a schedule. What if deployability is a property of the code, not the pipeline?
Decouple deploy units → failures become isolated → the class of problem disappears."
```

---

## 2. Infinite Reflection

**Pattern**: Keeps questioning assumptions layer after layer without ever returning to action. Each assumption reveals a deeper assumption beneath it. The reflection becomes an infinite regress that feels profound but produces nothing.

**Detection**:
- The reflection has gone through 3+ layers of "but what's the assumption behind THAT assumption?"
- No concrete action, updated model, or testable hypothesis has emerged
- The tone shifts from analytical to philosophical — discussing the nature of assumptions rather than specific ones
- Time spent reflecting exceeds time spent on the original task

**Fix**: Time-box the reflection. One cycle: name the governing variable, examine it, decide (update / confirm / investigate). If undecided after one cycle, the decision is "investigate" — design a cheap experiment, don't reflect harder. Xunzi's 化性起伪: good judgment comes from practice cycles, not from thinking longer.

```
Infinite reflection:
"Why do we miss deadlines? → Because we estimate badly → But why do we estimate badly?
→ Because we don't understand our velocity → But why don't we understand velocity?
→ Because velocity is an illusion of predictability → But what IS predictability?..."
→ 20 minutes of recursion, zero action items.

Bounded double-loop:
"Why do we miss deadlines? Governing assumption: 'we can predict task duration.'
Evidence: we've been wrong 8 of 10 times. Updated model: stop predicting duration,
start limiting work-in-progress and measuring throughput. Test next sprint."
```

---

## 3. Selective Reflection

**Pattern**: Reflects willingly on safe, peripheral assumptions while systematically avoiding the core beliefs that would be painful or identity-threatening to examine. The reflection is genuine but carefully scoped to avoid anything that matters.

**Detection**:
- The assumptions being examined are low-stakes ("maybe we should use a different testing framework")
- Core strategic or identity-level assumptions are treated as obvious, given, or "not up for discussion"
- The reflection produces changes that are comfortable to make
- Someone outside the system would immediately point to the assumption being avoided

**Fix**: Apply Husserl's bracketing specifically to the assumption you least want to question. Mao's 自我批评: the discipline is precisely in examining what's uncomfortable. Name the elephant: "The assumption I'm NOT examining is: ____." Then examine it.

```
Selective reflection:
"Why isn't our product growing? Let me reflect deeply... Maybe our onboarding flow
needs work. And our docs could be better. And we should try different marketing channels."
→ The unexamined assumption: "The product solves a real problem."

Actual double-loop:
"Why isn't our product growing? The assumptions I'm comfortable questioning: onboarding,
docs, marketing. The assumption I'm avoiding: whether the core value proposition is right.
Let me examine that one first — 5 of our last 8 churned users cited 'doesn't solve my
actual problem,' not 'hard to use.'"
```

---

## 4. Crisis-Only Reflection

**Pattern**: Reflects only when something goes visibly and badly wrong. When things are going well (or merely okay), no reflection occurs. The result is that assumptions are only examined under stress, which is the worst condition for clear thinking.

**Detection**:
- Reflection always follows a failure, never follows a success
- The prompt for reflection is emotional (anger, panic, embarrassment), not structural
- "Things are going fine" is treated as evidence that no reflection is needed
- Slow degradation goes unnoticed because there's no single crisis to trigger reflection

**Fix**: Attach reflection to task completion, not to failure. Inamori's 六項精進 and Zeng Guofan's 日课十二条: daily reflection is hygiene, not treatment. After every completed task, one question: "What governing variable drove my approach?" If the answer is "I don't know" or "whatever I did last time," that's the finding.

```
Crisis-only:
[Ship feature → ship feature → ship feature → catastrophic failure]
"Oh no, let's do a thorough retrospective! What went wrong?"
→ Three months of unreflective autopilot preceded the crisis.

Daily practice:
[Ship feature → "What assumption drove this design?" → Ship feature → "Still valid?"
→ Ship feature → "Hmm, this assumption is weakening, let me test it" → Adjust before crisis]
```

---

## 5. Performative Reflection

**Pattern**: Goes through all the motions of reflection — retrospectives are held, assumptions are named, insights are articulated — but nothing actually changes. The team or individual gains the psychological comfort of having "reflected" without bearing the cost of actually updating their model.

**Detection**:
- Retrospective notes exist, action items are written, but behavior next cycle is identical
- The same "insight" appears in multiple retrospectives ("we need to communicate better")
- Reflection outputs are phrased as observations ("we noticed that...") rather than commitments ("we will change...")
- No one can point to a specific assumption that was updated as a result of the last reflection

**Fix**: End every reflection with: "What specific assumption did we update, and what will we do differently because of it?" If the answer is vague, the reflection failed — and that finding is the output. Track the delta between reflections: if the governing variable is the same three cycles running, the loop isn't closing. Confucius: 学而不思则罔，思而不学则殆 — reflection that doesn't change action is as dangerous as action without reflection.

```
Performative:
"Sprint retrospective findings: Communication could be better. We should plan more
carefully. Let's be more proactive about blockers."
→ These same three findings have appeared in the last 5 retrospectives.

Actual double-loop:
"Sprint retrospective: Last time we said 'communicate better.' Nothing changed.
The real assumption: 'everyone knows what others are working on.' That's false.
Concrete change: daily 5-min sync replacing the weekly 1-hour meeting.
Measure: count surprise blockers next sprint. If still >2, this assumption
isn't the right one either."
```
