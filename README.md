# Legal Skills Plugin

[![npm version](https://img.shields.io/npm/v/@judicialmind/legal-skills.svg)](https://www.npmjs.com/package/@judicialmind/legal-skills)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A comprehensive legal practice skills library for AI coding assistants, providing expert-level guidance across 30 practice areas, functional domains, and jurisdictions. Compatible with Claude Code, OpenAI Codex, and other LLM-based tools that support skills/plugins.

## Installation

### Claude Code

```json
{
  "plugins": ["@judicialmind/legal-skills"]
}
```

### OpenAI Codex / Other LLMs

```bash
npm install @judicialmind/legal-skills
```

Or clone directly:

```bash
git clone https://github.com/judicialmind/legal-skills.git
```

The skills follow a standard YAML frontmatter + markdown format that can be adapted to any LLM system prompt or plugin architecture.

## Skills Overview

### Practice Verticals (15 Skills)

| Skill | Description | Triggers |
|-------|-------------|----------|
| `corporate-ma` | M&A transactions, due diligence, entity formation | merger, acquisition, shareholder agreement |
| `litigation` | Civil litigation, motions, discovery, trial prep | lawsuit, motion, discovery, deposition |
| `intellectual-property` | Patents, trademarks, copyrights, trade secrets | patent, trademark, copyright, IP |
| `real-estate` | Property transactions, leases, title review | lease, property, closing, zoning |
| `employment-labor` | Workplace compliance, policies, disputes | employment, FMLA, ADA, harassment |
| `tax-law` | Tax compliance, planning, IRS matters | tax, IRS, deduction, 1031 exchange |
| `immigration` | Visas, compliance, applications | visa, H-1B, green card, I-9 |
| `criminal-defense` | Defense representation, motions, appeals | criminal, felony, bail, sentencing |
| `family-law` | Divorce, custody, support, adoption | divorce, custody, child support |
| `bankruptcy` | Chapter 7/11/13, creditor rights | bankruptcy, Chapter 11, discharge |
| `healthcare-law` | HIPAA, compliance, malpractice | HIPAA, healthcare, medical, FDA |
| `environmental-law` | EPA compliance, permits, remediation | environmental, EPA, CERCLA, permit |

### Functional Domains (10 Skills)

| Skill | Description | Triggers |
|-------|-------------|----------|
| `legal-research` | Case law, statutes, citation verification | case law, precedent, Shepardize |
| `contract-lifecycle` | Drafting, review, risk analysis | contract, NDA, redline, clause |
| `e-discovery` | Document review, privilege logs, TAR | e-discovery, ESI, privilege log |
| `due-diligence` | Transaction review, risk assessment | due diligence, data room |
| `compliance-tracking` | Regulatory monitoring, audits | compliance, audit, filing deadline |
| `case-management` | Deadlines, calendaring, workflows | deadline, calendar, statute of limitations |
| `client-intake` | Conflicts, engagement letters | conflict check, engagement letter |
| `legal-analytics` | Outcome prediction, judge analysis | outcome prediction, judge analysis |
| `billing-operations` | Time tracking, LEDES, budgets | billing, LEDES, invoice |
| `document-drafting` | Legal document generation | draft, memo, demand letter |

### Jurisdiction & Specialty Skills (5 Skills)

| Skill | Description | Triggers |
|-------|-------------|----------|
| `us-federal-courts` | Federal jurisdiction and procedure | federal court, FRCP, circuit |
| `india-legal` | Indian courts, IPC, CrPC | India, IPC, High Court, NCLT |
| `uk-commonwealth` | English law, CPR, common law | UK, English law, CPR |
| `international-arbitration` | ICC, LCIA, SIAC, ICSID | arbitration, ICC, LCIA, New York Convention |
| `regulatory-compliance` | Multi-sector compliance programs | regulatory, compliance program |

### Additional Skills

| Skill | Description |
|-------|-------------|
| `court-filings` | ECF procedures, formatting, service |
| `deposition-prep` | Witness preparation, outlines |
| `brief-writing` | Appellate and motion briefs |

## Agent

### Legal Research Agent

Autonomous agent for comprehensive legal research:

- Multi-source case law research
- Statutory and regulatory analysis
- Citation verification
- Research memoranda drafting

## Architecture

```
legal-skills/
├── plugin.json              # Plugin manifest
├── skills/
│   ├── [skill-name]/
│   │   ├── SKILL.md         # Skill definition and guidance
│   │   └── references/      # On-demand reference materials
│   └── ...
└── agents/
    └── legal-research-agent.md
```

### Three-Level Progressive Disclosure

1. **Level 1 (YAML frontmatter)**: ~100 tokens, always in context for skill triggering
2. **Level 2 (SKILL.md body)**: Loaded when skill activates
3. **Level 3 (references/)**: Heavy content loaded on-demand

## Legal Sources

The plugin references 40+ authoritative legal sources including:

**Primary Databases**: Westlaw, LexisNexis, Bloomberg Law

**Free Resources**: Cornell LII, Google Scholar, CourtListener, Justia, Caselaw Access Project

**Court Databases**: PACER, Supreme Court, State Courts

**International**: Indian Kanoon, CanLII, BAILII, WorldLII

**Regulatory**: SEC EDGAR, Federal Register, eCFR, USPTO

## Usage Examples

```
User: "Draft a motion to compel discovery responses"
→ Triggers: litigation skill

User: "Review this NDA for risk issues"
→ Triggers: contract-lifecycle skill

User: "What are the HIPAA breach notification requirements?"
→ Triggers: healthcare-law skill

User: "Calculate the deadline for filing an answer in federal court"
→ Triggers: us-federal-courts, case-management skills
```

## Contributing

Contributions welcome. Please ensure:

1. SKILL.md follows the established format
2. Descriptions include relevant trigger keywords
3. Content is accurate and well-sourced
4. Reference files are appropriately scoped

## License

MIT License - see [LICENSE](LICENSE)

## Disclaimer

This plugin provides general legal information and guidance. It is not a substitute for professional legal advice. Always consult with a qualified attorney for specific legal matters.

---

Built by [JudicialMind](https://github.com/judicialmind)
