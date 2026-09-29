# Strategic Opportunity Insight

Four standalone research skills and guided workflows built on the Five Views framework.

[简体中文](README_CN.md) · English

[Interactive guide (Chinese)](https://tea-del.github.io/strategic-opportunity-insight/guide.html)

## What is this?

Strategic Opportunity Insight is a research tool for any industry. Evolved from Huawei's “Five Views” approach to strategic insight and informed by the dual-axis positioning of the BCG matrix, it helps teams start with a broad view of the market, then systematically identify, evaluate, and rank business opportunities. The result is a decision-ready insight report.

**Who it is for:** Teams and organizations choosing a direction—startups selecting a market, companies exploring a new business line, and investors assessing opportunities in a sector.

**What it solves:** Choosing a direction by instinct / being constrained by the current business / seeing a large market but not knowing whether the team can pursue it / having too many opportunities to compare systematically.

## Core design

**Market first** — Keep the first four views fact-based so the team's existing business does not narrow the search.

**Two independent dimensions** — Calculate and present market attractiveness and organizational fit separately:

- **Market attractiveness (100 points):** Market size 30% · Profit potential 25% · Competitive white space 20% · Timing 15% · Manageable risk 10%. Use market evidence only; do not factor in the organization.
- **Organizational fit (100 points):** Technology fit 30% · Resource fit 25% · Channel fit 25% · Strategic alignment 20%. Use organizational evidence only; do not factor in market size.

Never merge the two scores into a single total. Give each criterion a short, evidence-based scoring rationale (50–100 characters in the original Chinese rubric).

**Four quadrants** — Classify opportunities using organizational fit ≥50 and market attractiveness ≥60. Only opportunities in the Star quadrant receive a delivery-feasibility check:

| Quadrant | Meaning | What to do |
| --- | --- | --- |
| Star | High market attractiveness · high organizational fit | Prioritize |
| Question mark | High market attractiveness · low organizational fit | Watch and develop |
| Cash cow | Low market attractiveness · high organizational fit | Optimize existing business |
| Dog | Low on both dimensions | Do not invest for now |

**Feasibility check** — Put Star opportunities through four filters so “attractive” does not get confused with “executable”: Can the team earn its first paid revenue within three months? Does it have execution capacity? Is the startup cost affordable? Can existing channels reach the target customers?

Result: pass → prioritize; conditional pass → state the prerequisites; fail → downgrade or drop.

## Where to start

Use a standalone skill to answer one research question. Choose a guided workflow when you want to continue from existing research or complete the full Five Views process. An individual entry point stops at its own deliverables; it does not automatically expand into an 11-document report.

Every entry point begins with the same **three rounds of 15 questions** on first use: six about the organization, four about product and technology, and five about resources and channels. These define the research scope and constraints. Existing answers are checked and reused; only missing items are asked again.

### Standalone skills (4)

- `strategy-trends` — **Trends:** Industry, technology, policy, market size, and value migration. Delivers an industry trends brief.
- `strategy-customers` — **Customers:** Segments, pain points, willingness to pay, acquisition channels, and buying decisions. Delivers a customer market brief.
- `strategy-competitors` — **Competitors:** Market leaders, peers, alternatives, pricing, and technical approaches. Delivers a competitive landscape brief.
- `strategy-capabilities` — **Your organization:** Team capabilities, resources, products, and technology assets. Delivers an internal capability assessment.

### Guided workflows (4)

- `/four-views` — **Research the four views:** Understand the industry, customers, competitors, and your own organization. Delivers a research plan plus four briefs (5 documents).
- `/find-opportunities` — **Find opportunities:** Use the four views to scan possible business directions. Delivers an opportunity list and eight-dimension deep dives (2 documents); stops before scoring.
- `/compare-opportunities` — **Compare opportunities:** Assess user-specified or previously shortlisted directions. Delivers a two-axis scorecard, strategic matrix, and feasibility report (3 documents); only Star opportunities receive the feasibility check.
- `/strategy-insight` — **Full insight:** Run the Five Views process from intake to final report. Delivers the 5 + 2 + 3 documents above, plus the final Strategic Opportunity Insight report (11 documents total).

Those are each workflow's **target deliverables**. Missing prerequisite research is completed and delivered first; relevant existing material is reused. Running “Find opportunities” or “Compare opportunities” alone does not produce the final report.

For example, if you ask to compare three directions, the workflow fills in any missing Four Views research and eight-dimension deep dives for those three directions, then delivers the scorecard, matrix, and feasibility report. It does not invent a 30–50-item market scan just to compare your three options.

In a Claude plugin, commands are namespaced, for example `/strategic-opportunity-insight:four-views`. In Codex, invoke `$strategy-insight` and name the workflow you want. The fifth installable skill, `strategy-insight`, is the shared entry point for all four workflows.

### Examples

Standalone research:

> Use `$strategy-customers` to study the pain points and willingness to pay of small restaurant operators looking for digital tools.

> Use `$strategy-competitors` to map the main players and alternatives in China's veterinary software market.

Guided workflow in Codex:

> Use `$strategy-insight` to find opportunities in digital services for small restaurants.

> Use `$strategy-insight` to compare these three directions and identify which ones merit validation first.

Guided workflow as a Claude plugin:

> `/strategic-opportunity-insight:four-views China's veterinary care market`

> `/strategic-opportunity-insight:strategy-insight China's veterinary care market`

## Installation

Choose one of two paths. The **Claude Code plugin** installs the full set of skills and slash commands as a managed package. **skills.sh** lets you select skills for Codex, Claude Code, or another agent. If you use the Claude plugin, do not also install the same skills through skills.sh.

### Claude Code: install the full plugin

Add this GitHub repository as a plugin source, then install the plugin:

```bash
claude plugin marketplace add tea-del/strategic-opportunity-insight
claude plugin install strategic-opportunity-insight@strategic-opportunity-insight-marketplace
```

After installation, use a standalone skill or start a guided workflow with a command such as `/strategic-opportunity-insight:four-views`. In Claude Cowork, you can add the same repository from the plugin UI.

### Codex and other agents: choose the skills you need

```bash
npx skills@latest add tea-del/strategic-opportunity-insight
```

The installer asks which skills and agent to use, and whether to install at project or user level. Select one Four Views skill for standalone research, `strategy-insight` for guided workflows, or all five for the full set.

skills.sh installs skill files, not the Claude plugin's slash commands. In Codex, invoke `$strategy-insight` and specify “four-views”, “find-opportunities”, “compare-opportunities”, or “strategy-insight”.

These commands target local agents; they do not install a skill into a standard ChatGPT web conversation.

## Scope

This project covers the Five Views—strategic insight—not the subsequent strategic decisions (control points, goals, and strategy). Research findings should include sources and dates; estimates should not be presented as verified facts. Licensed under [Apache-2.0](LICENSE).
