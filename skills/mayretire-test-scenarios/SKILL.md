---
name: mayretire-test-scenarios
description: Compare, optimize, stress-test, simulate, or backtest an existing MayRetire plan through the remote MCP when the user asks what-if or risk questions.
---

# Test MayRetire scenarios

The remote service needs the complete user-supplied plan on each plan call;
it cannot fetch the user's MayRetire account or browser plan. Explain that
tool calls send the plan through the assistant to MayRetire for calculation.
Preserve the original plan, income and estate requirements, and all excluded
variables. Ask which consequential areas may change when the request leaves
that unclear. Inspect and validate before relying on results.

Read [scenario design](references/scenario-design.md) before edits or search.
Use `compare_plan_payloads` for small independent patches and deterministic
screening. Use `edit_plan_payload` for a selected complete plan or item
operations; show the diff and validate the result. For larger exploration or
optimization, use `start_plan_job` with a bounded request, poll
`status_plan_job`, collect `result_plan_job`, and retrieve only selected
candidate plans with `get_candidate_plan`. Cancel work the user no longer
needs. Search results describe the evaluated candidate space, not every
possible plan.

Read [stress, Monte Carlo, and backtesting](references/stress-and-simulation.md)
before a risk test. Run the requested test rather than substituting a different
metric. Distinguish six-scenario stress pass counts and average spending funded
from Monte Carlo probability. Compare plans with aligned success criteria,
trial count, seed, and engine build. Use only returned metrics and explain
sampling uncertainty. An apparent improvement may come from reduced spending;
show that tradeoff. Do not give personalized financial or tax advice.
