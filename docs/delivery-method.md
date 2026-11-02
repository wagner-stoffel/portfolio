# Project delivery method

This is a **working framework** for portfolio projects involving business processes, AI, and automation. It is not a claim that all phases have been executed in every published case study.

## 1. Discover
- Identify business objectives, stakeholders, ownership, pain points, and constraints.
- Map the current (**AS-IS**) process and note available baseline measures (time, cost, quality, satisfaction).
- Avoid presupposing that AI is the right solution.

**Artifacts:** problem statement, stakeholder map, AS-IS diagram, baseline.

## 2. Define
- Describe the target (**TO-BE**) process, scope, exclusions, and success criteria.
- Evaluate process simplification, conventional automation, and AI-assisted alternatives.
- Review expected value, feasibility, security, privacy, cost, and operational risks.

**Artifacts:** requirements, solution options, acceptance criteria, risk log.

## 3. Plan
- Decompose work into prioritized, verifiable deliverables.
- Make dependencies, responsibilities, decisions, and work in progress visible.
- Adapt the delivery approach to the project's size and uncertainty; use Kanban or other appropriate practices.

**Artifacts:** backlog, delivery plan, decision log, definition of done.

## 4. Implement
- Build the smallest useful version of the process, integration, or workflow.
- Document interfaces, data handling, prompts, APIs, and configuration assumptions.
- Keep credentials outside the repository and use minimal privileges.

**Artifacts:** architecture diagram, workflow, configuration notes, sanitized implementation evidence.

## 5. Validate
- Test typical, ambiguous, failure, and missing-data scenarios.
- Record what was **observed** separately from what was **expected**.
- Verify AI outputs against available authoritative or structured sources.
- Compare actual results with the defined acceptance criteria; never invent metrics.

**Artifacts:** test plan, run evidence, limitations, outstanding issues.

## 6. Improve and hand over
- Capture lessons learned, ownership, operational dependencies, monitoring, and recovery paths.
- Prioritize improvements based on observed risks and results.
- Assess whether deployment or expansion is justified.

**Artifacts:** operating notes, improvement backlog, handover checklist.

## Evidence and status

- **Planned:** concept or unbuilt design.
- **Prototype:** an implementation exists, with its demonstrated scope clearly defined.
- **Tested:** specific checks were executed and documented; this does not imply production readiness.
- **Deployed:** operational use is verified.

Current documented example: [Equity EOD AI Agent](../projects/01-equity-eod-ai-agent/README.md) — tested learning prototype.
