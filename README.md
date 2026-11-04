# AI-assisted risk register (ISO 27005 style)

A small GRC workflow that uses an AI assistant (a [Claude Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)) to turn a plain-language cybersecurity scenario into a structured **risk register**, following the logic of ISO/IEC 27005: identify threats and vulnerabilities per asset, score likelihood and impact, prioritise, and choose a treatment with a concrete control.

The goal is not to replace a risk assessment, but to speed up the first draft so the analyst can spend time on validation and discussion with stakeholders.

## How it works
1. Describe the organisation and its known weaknesses in plain text (see the [example scenario](examples/novalogistics-scenario.md)).
2. The skill ([`skill/SKILL.md`](skill/SKILL.md), Spanish original in [`SKILL.es.md`](skill/SKILL.es.md)) forces a fixed output:
   - 2-sentence context with the critical assets
   - Risk table: ID · Threat · Vulnerability · Asset · Likelihood (1–5) · Impact (1–5) · Level (L×I) · Treatment · Proposed control
   - Risks sorted by level, top 3 priorities with actions, and explicit assumptions
3. The analyst reviews the output and maps controls to ISO/IEC 27001:2022 Annex A.

## Example
[NovaLogistics B.V.](examples/novalogistics-risk-register.md) – a fictional 120-employee logistics SME: 8 risks identified, ransomware (level 20), missing MFA (16) and invoice fraud (16) as top priorities.

## Design choices
- **Fixed structure:** every run produces the same columns, so registers are comparable and easy to import into a spreadsheet.
- **Explicit assumptions:** missing information is listed instead of silently invented.
- **Human in the loop:** scores and controls are reviewed manually before use.

## Limitations
- Qualitative 1–5 scoring only; no quantitative (e.g. FAIR) analysis.
- Output quality depends on the scenario description; it does not replace interviews, asset inventories or technical testing.

## Usage
Add the `skill/` folder as a skill in Claude (or paste `SKILL.md` as instructions in any assistant), then describe your scenario and ask for a risk register.
