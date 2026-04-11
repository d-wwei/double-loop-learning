# Double-Loop Learning — Before/After Examples

Four scenarios across different domains, demonstrating the cognitive protocol in action.

---

## Example 1: Engineering

**User**: "Why do our deploys keep failing? We've tried adding retries, increasing timeouts, and pinning dependencies."

### Before (default mode)

> Here are some additional steps to stabilize your deploy pipeline:
>
> 1. Add canary deployments to catch issues before full rollout
> 2. Implement blue-green deployment for instant rollback
> 3. Add more comprehensive pre-deploy health checks
> 4. Consider a deployment freeze window during peak traffic
> 5. Add better monitoring and alerting for deploy metrics
> 6. Review your rollback procedure and automate it
>
> These are industry best practices used by companies like Netflix and Google.

**Problems**: Accepts "deploys keep failing" as a pipeline problem (single-loop). Offers more sophisticated versions of the same approach — adding layers to the existing model. Never questions whether the deploy model itself is the source. Classic single-loop disguise: the suggestions are good, but they're all parameter adjustments within the same governing assumption.

### After (cognitive protocol active)

> You've tried retries, timeouts, and pinning — all single-loop fixes. They adjust parameters within the same model. The fact that deploys *keep* failing suggests the model itself is the issue.
>
> The governing assumption: "All changes should be deployed together on a coordinated schedule." Let me question that.
>
> If deployability were a property of each change (independently deployable units), rather than a property of the pipeline (one big deploy), the failure mode changes fundamentally. Individual unit failures are isolated and instantly rollbackable. The "deploy keeps failing" pattern can't recur because there's no coordinated deploy to fail.
>
> This is a model-level change, not a parameter change. It has real costs (requires decoupling, feature flags, independent testing). But it addresses why deploys keep failing, not just how to make the next one succeed.
>
> Which constraint is actually preventing you from decoupling deploy units? That's where the real problem lives.

**Active shifts**: Governing variable identified ("deploy everything together"). Pattern recognition ("keeps failing" signals model problem, not parameter problem). Model-level alternative proposed (independent deployability). Loop closed with a concrete question.

---

## Example 2: Management

**User**: "Why does this team keep missing deadlines? We've tried better estimation, buffer time, and daily standups."

### Before (default mode)

> Missing deadlines consistently suggests estimation and planning issues. Here are some approaches:
>
> 1. Use story points instead of time estimates for better relative sizing
> 2. Track velocity over 3-4 sprints to build a reliable baseline
> 3. Break stories into smaller units — nothing larger than 3 days
> 4. Add a 20-30% buffer for unknown unknowns
> 5. Use planning poker to reduce individual estimation bias
> 6. Identify and address blockers earlier with daily standups
>
> Many teams find that after 4-6 sprints of velocity tracking, their estimates become much more accurate.

**Problems**: Accepts "missing deadlines" as an estimation problem (single-loop). Every suggestion is a more refined way to estimate — adjusting the same model's parameters. Never questions whether estimation-then-execute is the right model. Selective reflection: examines the easy assumption (estimation accuracy) and avoids the hard one (whether the goal-setting structure is producing the problem).

### After (cognitive protocol active)

> You've tried better estimation, buffers, and standups — all refinements within the same model: "predict how long work will take, then execute to the prediction." The team keeps missing deadlines despite these fixes. That's a signal that the model, not the execution, needs examination.
>
> Governing assumption: "We can and should predict task duration, then hold people accountable to that prediction."
>
> Let me bracket that assumption. What if unpredictability isn't a bug in your estimation process, but a fundamental property of the work? Knowledge work has irreducible uncertainty. If that's true, improving estimation is the wrong loop — you're polishing a tool that can't do the job.
>
> Alternative model: Stop estimating duration. Instead, limit work-in-progress (WIP) and measure throughput. Deadlines become forecasts based on observed flow rate, not promises based on predictions. The team stops "missing deadlines" because the framing changes from "predict and commit" to "limit, measure, forecast."
>
> Cross-perspective check: from the team's view, "missing deadlines" might feel like "being set up to fail by impossible estimates." The governing variable might be the accountability model, not the team's performance.
>
> What outcome are the deadlines actually serving? If it's predictability for stakeholders, throughput-based forecasting delivers that better than estimation does.

**Active shifts**: Governing variable identified ("predict then execute"). Bracketing applied (what if unpredictability is inherent?). Cross-perspective (team's experience). Alternative model proposed (WIP limits + throughput). Closed with a question about the actual need behind deadlines.

---

## Example 3: Personal

**User**: "Why do I keep procrastinating on important work? I've tried Pomodoro, time-blocking, and accountability partners."

### Before (default mode)

> Procrastination is a common challenge. Here are some additional techniques:
>
> 1. Break tasks into 2-minute micro-actions to reduce activation energy
> 2. Use implementation intentions: "When X happens, I will do Y"
> 3. Remove distractions — use app blockers during focus time
> 4. Try body doubling — work alongside someone else
> 5. Reward yourself after completing difficult tasks
> 6. Address perfectionism — "done is better than perfect"
> 7. Consider whether you might have undiagnosed ADHD
>
> The key is finding the technique that works for YOUR brain. Experiment and iterate.

**Problems**: Treats procrastination as a behavior to correct with better techniques (single-loop). Offers six more parameter adjustments within the same model: "procrastination is a discipline/technique problem." Never questions whether the work is actually important, whether the resistance carries information, or whether the goal structure itself is the issue.

### After (cognitive protocol active)

> You've tried Pomodoro, time-blocking, and accountability partners — all techniques to force yourself to do the work. They address the behavior (not working) without examining the assumption behind it.
>
> Governing assumption: "This work is important and I should want to do it. My resistance is a malfunction to be overcome with better tools."
>
> Let me bracket that. What if the resistance IS the information? Three possibilities when you systematically avoid "important" work:
>
> 1. **The work isn't actually important to you.** It's important to someone else, or to a version of yourself you think you should be. The procrastination is honest; the priority label is not.
> 2. **The work is important but the approach is wrong.** You're not avoiding the goal — you're avoiding a specific path to the goal that doesn't fit how you work. The governing variable to change is the approach, not your discipline.
> 3. **The work is important and the approach is fine, but the stakes feel identity-threatening.** Completing it means being judged. Not completing it means you never "really tried." The procrastination is protective.
>
> Each of these has a completely different intervention. (1) requires re-examining your priorities — maybe drop the task. (2) requires redesigning the approach. (3) requires addressing the fear, not the schedule.
>
> Which of these resonates? The technique-shopping (Pomodoro, time-blocking, etc.) only works if the real answer is "none of the above — I genuinely need to do this work this way and I just need more discipline." That's possible, but it's the least likely explanation when three different techniques have already failed.

**Active shifts**: Governing variable identified ("resistance is a malfunction"). Bracketing (what if resistance is information?). Three alternative models proposed, each with a different intervention. Selective reflection caught (easy assumption: "I need better tools"; hard assumption: "this work might not be right for me"). Closed with a diagnostic question.

---

## Example 4: Product Strategy

**User**: "Our feature requests keep piling up and we can't ship fast enough. How do we increase development velocity?"

### Before (default mode)

> Increasing development velocity is about removing bottlenecks and improving throughput:
>
> 1. Adopt CI/CD if you haven't already
> 2. Reduce code review turnaround time — aim for < 4 hours
> 3. Invest in test automation to reduce manual QA time
> 4. Reduce meeting load — protect maker time
> 5. Break features into smaller shippable increments
> 6. Consider hiring more developers
> 7. Evaluate whether your tech debt is slowing you down
>
> Most teams find they can increase velocity 30-50% by focusing on these areas.

**Problems**: Accepts "we need to ship faster" as a given (single-loop). Every suggestion is about producing more output within the same model. Never questions whether the pile of feature requests is the actual problem, or whether shipping faster would actually help.

### After (cognitive protocol active)

> Before optimizing velocity, let me examine the governing assumption: "We have too many feature requests and not enough shipping capacity. The bottleneck is development speed."
>
> But feature requests piling up is a symptom, not a diagnosis. Three different governing assumptions produce this same symptom:
>
> 1. **"Every feature request represents real user need."** If false, you don't have a velocity problem — you have a filtering problem. Saying no to 60% of requests might clear the backlog better than doubling your team.
>
> 2. **"Shipping features creates value."** If partially false — if features are shipping but not moving metrics — you have a strategy problem. You're building efficiently in the wrong direction. Increasing velocity makes this worse faster.
>
> 3. **"The current architecture supports the product's actual trajectory."** If false, you have a platform problem. Speed improvements get eaten by increasing complexity. The right move is to slow down, restructure, then accelerate.
>
> Each diagnosis leads to a fundamentally different intervention. (1) = better prioritization, not more capacity. (2) = better strategy, not more shipping. (3) = deliberate slowdown now for speed later.
>
> Sima Qian's 太史公曰 pattern: across all the teams I've seen asking "how do we ship faster," the actual bottleneck is almost never raw development speed. It's usually one of: unclear priorities (most common), building the wrong things (second), or accumulated complexity (third).
>
> What percentage of your shipped features in the last quarter actually moved a metric you care about?

**Active shifts**: Governing variable identified ("bottleneck is dev speed"). Three alternative models with different interventions. Cross-case pattern (Sima Qian — what's usually true across many instances). Inamori multiplier logic (if the strategy model is wrong, increasing effort makes things worse). Closed with a diagnostic question that tests the assumption.
