# Planning goals and success

Read this for a broad plan review or when interpreting a success result. Inspect
and validate the supplied plan, then calculate a deterministic baseline. Derive
ages, income, balances, enabled assets, spending, benefit timing, withdrawal
strategy, and estate settings before asking the user to repeat them. Separate
hard constraints from preferences and areas the user permits changing. Ask only
for missing facts material to the requested decision.

Identify the active spending strategy, not merely the stored dollar fields:

- Constant-dollar spending uses one steady annual after-tax household target;
  a stored minimum is inactive.
- Flexible spending uses a desired amount and a minimum acceptable floor. An
  income range is normally a desired upper amount and a lower floor, unless the
  user explicitly requests a range of fixed-spending scenarios.
- Estate-target spending resolves sustainable income while preserving an
  after-tax estate target and minimum spending floor. A positive stored estate
  amount is not enforced unless the estate-target strategy is active.

Clarify whether a requested estate figure is a binding goal or a threshold to
measure under steady or flexible spending. Keep additional temporary spending,
one-time purchases, recurring replacements, and gifts separate from baseline
spending. Confirm amount, first one-based planning year, duration or recurrence,
and whether each is required or reducible. Do not count an addition twice.

Use returned `assumptions` and `successCriteria` to define the result. A call
completing successfully does not mean the plan funds its requirements. Report
whether income and any active estate requirement are met. Do not compare success
rates for plans with different criteria as if they answer the same question.
Estate percentiles do not provide an exact probability at an arbitrary threshold.
MayRetire's current Monte Carlo summary does not return income p10/p50/p90;
do not invent them.

For improvements, test material levers separately before combining them.
Begin with changes that preserve the user's stated lifestyle and investment
risk when scope is unclear. Do not silently lower income, remove an estate
goal, sell property, extend employment, or change investments to make a plan
pass. Explain any changed requirement in ordinary financial terms. Summary and
named-view amounts are generally CAD in plan-start purchasing power; use the
returned field basis if a specific value differs. Planning years are one-based
and are not necessarily calendar years.
