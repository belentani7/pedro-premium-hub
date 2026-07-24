# Audit Report — CLI Coder Skills & Premium Repos

Generated: 2026-07-25

## Part 1: Skill Structure Analysis

### Current State (9 locations, 288+ total skills)

| Location | Skills | Unique | Duplicated | Quality |
|----------|--------|--------|------------|---------|
| `.claude/skills/` | 66 | 66 (canonical) | 0 | Complete |
| `.opencode/skills/` | 68 | 8 | 60 from .claude | Complete |
| `.codex/skills/` | 6 | 6 | 0 | Complete (system only) |
| `.mimocode/skills/` | 22 | 1 | 21 from .claude | Complete |
| `.hermes-venv/skills/` | ~86 | ~86 | 0 | Complete |
| `.iflow/skills/` | 11 | 11 | 0 | Complete |
| `.vibe/skills/` | 11+2 broken | 11 | 11 from .iflow | Broken links |
| `builtin_skills/` | 8 | 8 | 0 | Excellent |
| `compose/` | 14 | 14 | Reimpl of .claude | Complete |

### Problems Found

1. **No sync mechanism** — Skills manually copied between .claude/.opencode/.mimocode with no versioning
2. **Broken links** — .vibe has 2 broken junction links (find-skills, tailored-resume-generator)
3. **Language inconsistency** — Mixed Spanish/English across locations
4. **Drift risk** — compose/ mirrors 14 .claude skills as separate copies
5. **Missing from .codex** — Only 6 system skills, no user skills installed
6. **Missing from .mimocode** — Only 22 of 66 .claude skills copied (44 missing)

### Missing Skill Categories (not covered anywhere)

| Category | Gap | Recommendation |
|----------|-----|----------------|
| **DevOps/Deploy** | No Docker/K8s/CI-CD skill | Create `devops-deploy` skill |
| **Mobile** | react-native-expert exists but no Flutter skill | Create `flutter-expert` skill |
| **Database** | No SQL/NoSQL optimization skill | Create `database-optimizer` skill |
| **API Testing** | No Postman/REST testing skill | Create `api-testing` skill |
| **Monitoring** | No observability/logging skill | Create `observability` skill |
| **Accessibility** | web-design-guidelines exists but no dedicated a11y skill | Create `accessibility-auditor` skill |
| **Performance** | No web performance optimization skill | Create `performance-engineer` skill |

---

## Part 2: Premium Repos Analysis

### Top 20 Repos by Stars (CLI Coding Ecosystem, Jul 2026)

| Rank | Repo | Stars | Category | Relevance |
|------|------|-------|----------|-----------|
| 1 | [affaan-m/ECC](https://github.com/affaan-m/ECC) | 233k | Claude Code harness | CRITICAL |
| 2 | [multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills) | 196k | Karpathy principles | CRITICAL |
| 3 | [anomalyco/opencode](https://github.com/anomalyco/opencode) | 189k | Open source agent | HIGH |
| 4 | [anthropics/claude-code](https://github.com/anthropics/claude-code) | 139k | Official Claude Code | CRITICAL |
| 5 | [garrytan/gstack](https://github.com/garrytan/gstack) | 124k | CEO setup | HIGH |
| 6 | [farion1231/cc-switch](https://github.com/farion1231/cc-switch) | 121k | Multi-tool manager | HIGH |
| 7 | [openai/codex](https://github.com/openai/codex) | 101k | Official Codex | HIGH |
| 8 | [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify) | 95.2k | Knowledge graph | HIGH |
| 9 | [JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman) | 92.7k | Token optimization | MEDIUM |
| 10 | [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | 89k | Lazy senior dev | MEDIUM |
| 11 | [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) | 88.9k | Official MCP | CRITICAL |
| 12 | [thedotmack/claude-mem](https://github.com/thedotmack/claude-mem) | 88.5k | Persistent memory | HIGH |
| 13 | [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) | 50.9k | Curated resources | HIGH |
| 14 | [Yeachan-Heo/oh-my-claudecode](https://github.com/Yeachan-Heo/oh-my-claudecode) | 38k | Multi-agent | HIGH |
| 15 | [wshobson/agents](https://github.com/wshobson/agents) | 38.2k | Plugin marketplace | HIGH |
| 16 | [anthropics/claude-plugins-official](https://github.com/anthropics/claude-plugins-official) | 32.6k | Official plugins | HIGH |
| 17 | [github/github-mcp-server](https://github.com/github/github-mcp-server) | 31.7k | GitHub MCP | MEDIUM |
| 18 | [iOfficeAI/AionUi](https://github.com/iOfficeAI/AionUi) | 30.8k | 24/7 cowork app | MEDIUM |
| 19 | [manaflow-ai/cmux](https://github.com/manaflow-ai/cmux) | 25.1k | Terminal for agents | MEDIUM |
| 20 | [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | 23.1k | 345 skills | HIGH |

### Repos You Should Clone/Fork

| Priority | Repo | Why |
|----------|------|-----|
| P0 | ECC (233k) | Agent harness optimization — skills, instincts, memory, security |
| P0 | karpathy-skills (196k) | Single CLAUDE.md from Karpathy's observations |
| P0 | claude-code (139k) | Official — plugins, docs, latest features |
| P0 | MCP servers (88.9k) | Official reference servers — Fetch, Filesystem, Git, Memory |
| P1 | gstack (124k) | Garry Tan's 23 opinionated tools |
| P1 | cc-switch (121k) | Manage all CLI tools from one place |
| P1 | claude-mem (88.5k) | Persistent memory across sessions |
| P1 | claude-skills (23.1k) | 345 skills to cherry-pick from |
| P1 | agents (38.2k) | Multi-harness plugin marketplace |
| P2 | graphify (95.2k) | Knowledge graph skill |
| P2 | oh-my-claudecode (38k) | Multi-agent orchestration |
| P2 | claude-plugins-official (32.6k) | Official plugin directory |

---

## Part 3: Recommended Changes

### A. Fix Existing Issues

1. **Fix .vibe broken links** — Remove or fix find-skills and tailored-resume-generator junction links
2. **Sync skill versions** — Create a skill-sync script that propagates changes from .claude to .opencode/.mimocode
3. **Standardize language** — All descriptions should be English (universal)

### B. Add Missing Skills to Unified Repo

| New Skill | Purpose | Source |
|-----------|---------|--------|
| `devops-deploy` | Docker, K8s, CI/CD, Vercel, Render | Create new |
| `database-optimizer` | SQL/NoSQL optimization, indexing, queries | Create new |
| `performance-engineer` | Lighthouse, Core Web Vitals, optimization | Create new |
| `accessibility-auditor` | WCAG 2.2 compliance, screen reader testing | Create new |
| `api-testing` | REST/GraphQL testing, Postman, curl | Create new |
| `observability` | Logging, monitoring, alerting, APM | Create new |

### C. Add Premium Repos to Knowledge Base

Create `knowledge/PREMIUM-REPOS.md` with all 20 repos, clone instructions, and key takeaways.

### D. Upgrade Unified Repo Structure

```
pedro-premium-hub/
├── CLAUDE.md
├── README.md
├── AUDIT-REPORT.md          # This file
├── skills/                  # 26+ curated skills
│   ├── core/                # Development skills
│   ├── ai/                  # AI/ML skills
│   ├── design/              # Design skills
│   ├── security/            # Security skills
│   ├── devops/              # NEW: Deploy/infra skills
│   └── content/             # Writing/content skills
├── projects/                # 17 project repos
├── protocols/               # Reusable workflows
├── research/                # Business analysis
├── knowledge/               # Extracted insights + premium repos
│   ├── EXTRACTED-INSIGHTS.md
│   └── PREMIUM-REPOS.md     # NEW: Top 20 repos
├── agents/                  # AI agent configs
└── templates/               # Reusable project templates
```
