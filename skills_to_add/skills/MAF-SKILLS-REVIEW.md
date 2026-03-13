# MAF Skills Review Report

Review of 10 Python skills for Microsoft Agent Framework (MAF) against the skill creation documentation:
- **skill-creator** (general skill creation)
- **skill-creator-ms** (Azure/Microsoft-specific patterns)
- **skill-development** (Claude Code plugin best practices)
- **create-skill** (Cursor skill format)

---

## 1. Naming Convention

**Source**: skill-creator-ms, create-skill

| Criterion | Requirement | Status | Notes |
|-----------|------------|--------|-------|
| Format | `<framework>-<feature>-<language>` | **Fixed** | Originally used Title Case with spaces (e.g., "MAF AG-UI Protocol"); updated to lowercase-with-hyphens + `-py` suffix |
| Characters | Lowercase letters, numbers, hyphens only | **Pass** | All names now comply |
| Max length | 64 characters | **Pass** | Longest: `maf-middleware-observability-py` (32 chars) |
| `-py` suffix | Required for Python skills | **Fixed** | Added to all 10 skills |

### Updated Names

| Skill | Old Name | New Name |
|-------|----------|----------|
| maf-ag-ui | `MAF AG-UI Protocol` | `maf-ag-ui-py` |
| maf-agent-types | `MAF Agent Types` | `maf-agent-types-py` |
| maf-declarative-workflows | `MAF Declarative Workflows` | `maf-declarative-workflows-py` |
| maf-getting-started | `MAF Getting Started` | `maf-getting-started-py` |
| maf-hosting-deployment | `MAF Hosting and Deployment` | `maf-hosting-deployment-py` |
| maf-memory-state | `MAF Memory and State` | `maf-memory-state-py` |
| maf-middleware-observability | `MAF Middleware and Observability` | `maf-middleware-observability-py` |
| maf-orchestration-patterns | `MAF Orchestration Patterns` | `maf-orchestration-patterns-py` |
| maf-tools-rag | `MAF Tools and RAG` | `maf-tools-rag-py` |
| maf-workflow-fundamentals | `MAF Workflow Fundamentals` | `maf-workflow-fundamentals-py` |

**Verdict: Fixed (was Major, now Pass)**

---

## 2. Description Quality

**Source**: skill-development, create-skill, skill-creator, skill-creator-ms

### Criteria Evaluation

| Criterion | Requirement | Status |
|-----------|------------|--------|
| Third person | "This skill should be used when..." | **Pass** — All 10 use this format |
| WHAT + WHEN | Includes capabilities AND trigger scenarios | **Pass** — All 10 include both |
| Trigger phrases | Specific phrases in quotes | **Pass** — All 10 have 8–14 quoted trigger phrases |
| Max length | ≤1024 characters | **Pass** — Range: 312–440 chars |
| Python mention | Language-specific skills must mention Python | **Pass** — All 10 mention "Python" |
| Pushiness | Slightly aggressive to prevent under-triggering | **Minor** — See below |

### Per-Skill Description Analysis

| Skill | Chars | Trigger Phrases | Verdict |
|-------|-------|----------------|---------|
| maf-ag-ui-py | 348 | 11 (AG-UI, AGUI, frontend agent, FastAPI agent, SSE streaming, AGUIChatClient, state sync, frontend tools, Dojo testing, add_agent_framework_fastapi_endpoint, AgentFrameworkAgent) | Pass |
| maf-agent-types-py | 336 | 9 (configure agent, OpenAI agent, Azure agent, Anthropic agent, Foundry agent, durable agent, custom agent, ChatClient agent, agent type, provider configuration) | Pass |
| maf-declarative-workflows-py | 398 | 11 (declarative workflow, YAML workflow, workflow expressions, workflow actions, declarative agent, GotoAction, RepeatUntil, Foreach, BreakLoop, ContinueLoop, SendActivity) | Pass |
| maf-getting-started-py | 393 | 11 (get started with MAF, create first agent, install agent-framework, set up MAF project, run basic agent, ChatAgent, agent.run, run_stream, AgentThread, agent-framework-core, pip install agent-framework) | Pass |
| maf-hosting-deployment-py | 312 | 8 (deploy agent, host agent, DevUI, protocol adapter, production deployment, test agent locally, agent hosting, FastAPI hosting) | Pass |
| maf-memory-state-py | 375 | 10 (chat history, memory, conversation storage, Redis store, thread serialization, context provider, Mem0, multi-turn conversation, persist conversation, ChatMessageStore) | Pass |
| maf-middleware-observability-py | 367 | 12 (middleware, observability, OpenTelemetry, logging, telemetry, Purview, governance, agent middleware, function middleware, tracing, @agent_middleware, @function_middleware) | Pass |
| maf-orchestration-patterns-py | 440 | 14 (sequential orchestration, concurrent orchestration, group chat, Magentic, handoff, human in the loop, HITL, multi-agent pattern, orchestration, SequentialBuilder, ConcurrentBuilder, GroupChatBuilder, MagenticBuilder, HandoffBuilder) | Pass |
| maf-tools-rag-py | 355 | 10 (add tools to agent, function tool, hosted tool, MCP tool, RAG, agent as tool, code interpreter, web search tool, file search tool, @ai_function) | Pass |
| maf-workflow-fundamentals-py | 373 | 11 (create workflow, workflow builder, executor, edges, workflow events, superstep, shared state, checkpoints, workflow visualization, state isolation, WorkflowBuilder) | Pass |

### Pushiness Assessment (Minor Issue)

Per skill-creator: *"Claude has a tendency to 'undertrigger' skills... make the skill descriptions a little bit 'pushy'"*. The current descriptions are functional but could be made more aggressive. For example, adding phrases like "Make sure to use this skill whenever the user mentions..." or "even if they don't explicitly ask for..." would improve trigger reliability.

**Verdict: Pass with Minor recommendation to increase pushiness**

---

## 3. SKILL.md Structure and Length

**Source**: skill-creator, skill-creator-ms, skill-development, create-skill

### Line Count and Word Count

| Skill | Lines | Body Words | Under 500 Lines | 1500-2000 Words |
|-------|-------|-----------|-----------------|-----------------|
| maf-ag-ui-py | 201 | ~1,450 | **Pass** | **Minor** (slightly below) |
| maf-agent-types-py | 157 | ~1,050 | **Pass** | **Minor** (below range) |
| maf-declarative-workflows-py | 174 | ~1,200 | **Pass** | **Minor** (below range) |
| maf-getting-started-py | 152 | ~900 | **Pass** | **Minor** (below range) |
| maf-hosting-deployment-py | 147 | ~1,050 | **Pass** | **Minor** (below range) |
| maf-memory-state-py | 117 | ~900 | **Pass** | **Minor** (below range) |
| maf-middleware-observability-py | 130 | ~950 | **Pass** | **Minor** (below range) |
| maf-orchestration-patterns-py | 159 | ~1,150 | **Pass** | **Minor** (below range) |
| maf-tools-rag-py | 192 | ~1,200 | **Pass** | **Minor** (below range) |
| maf-workflow-fundamentals-py | 122 | ~1,100 | **Pass** | **Minor** (below range) |

**Analysis**: All SKILL.md files are well under the 500-line limit (Pass). However, body word counts range from ~900 to ~1,450, all falling below the skill-development recommended range of 1,500–2,000 words. This could be acceptable under the skill-creator principle of "concise is key" — the question is whether more content would improve agent performance on real tasks.

### Section Order (skill-creator-ms SDK pattern)

The skill-creator-ms recommends: Title → Installation → Environment Variables → Authentication → Core Workflow → Feature Tables → Best Practices → Reference Links.

These MAF skills are not traditional Azure SDK skills (they're framework documentation skills), so the SDK section order does not directly apply. However, the skills do follow a consistent internal pattern:

**Observed common pattern across all 10 skills:**
1. Title (H1)
2. Introductory paragraph
3. Feature overview / taxonomy table
4. Quick-start code example(s)
5. Key concepts / detailed sections
6. Summary tables
7. Additional Resources (reference file links)

This is a reasonable alternative structure that fits the framework-documentation nature of these skills.

**Verdict: Pass (line count), Minor (word count below ideal range)**

---

## 4. Writing Style

**Source**: skill-development, skill-creator

### SKILL.md Files

| Criterion | Requirement | Status |
|-----------|------------|--------|
| Imperative form | Verb-first instructions | **Pass** — Overwhelmingly imperative/instructional |
| No second person | No "You should/need/can..." | **Minor** — 1 violation found |
| Objective language | "To accomplish X, do Y" | **Pass** |
| Explain the "why" | Theory of mind over rigid MUSTs | **Pass** — Good explanatory style |

#### Second-Person Violations in SKILL.md Files

Only one violation found in instructional text:

**`maf-hosting-deployment/SKILL.md` line 38:**
> "Use DevUI when you need to:"

This should be rephrased to imperative form: "Use DevUI to:" or "DevUI is useful for:"

All other "you" occurrences in SKILL.md files are inside code strings (e.g., `instructions="You are a helpful assistant."`) which is acceptable — those are agent instructions, not skill instructions.

### Reference Files

Reference files have a few more second-person instances (10 total across all 30 files), mostly in:
- `custom-and-advanced.md`: "the features you need"
- `workflow-agents.md`: "when you need to control..."
- `sequential-concurrent.md`: "when you need more control..."

These are Minor — the documentation guidelines primarily focus on SKILL.md body writing style, and reference files are loaded only as needed.

**Verdict: Minor (1 second-person violation in SKILL.md, ~10 in reference files)**

---

## 5. Progressive Disclosure

**Source**: skill-creator, skill-development, create-skill

### SKILL.md Lean Check

| Criterion | Status |
|-----------|--------|
| SKILL.md contains core essentials | **Pass** — All 10 are lean with pointers to references |
| Details moved to references/ | **Pass** — Consistent pattern across all skills |
| References one level deep | **Pass** — No nested references found |
| Reference files linked from SKILL.md | **Pass** — All skills have "Additional Resources" section with linked refs |
| Links include descriptions of when to read | **Pass** — Each ref link includes a description of contents |

### Table of Contents for Large Reference Files (>300 lines)

Per skill-creator: *"For large reference files (>300 lines), include a table of contents."*

**17 reference files exceed 300 lines. NONE have a table of contents.**

| File | Lines | Has TOC |
|------|-------|---------|
| `maf-ag-ui/references/tools-hitl-state.md` | 420 | No |
| `maf-agent-types/references/openai-providers.md` | 392 | No |
| `maf-agent-types/references/custom-and-advanced.md` | 381 | No |
| `maf-agent-types/references/azure-providers.md` | 441 | No |
| `maf-declarative-workflows/references/expressions-variables.md` | 301 | No |
| `maf-declarative-workflows/references/advanced-patterns.md` | 444 | No |
| `maf-declarative-workflows/references/actions-reference.md` | 397 | No |
| `maf-hosting-deployment/references/devui.md` | 378 | No |
| `maf-middleware-observability/references/observability-setup.md` | 335 | No |
| `maf-middleware-observability/references/middleware-patterns.md` | 357 | No |
| `maf-tools-rag/references/rag-and-composition.md` | 335 | No |
| `maf-tools-rag/references/hosted-and-mcp-tools.md` | 302 | No |
| `maf-memory-state/references/chat-history-storage.md` | 348 | No |
| `maf-orchestration-patterns/references/handoff-hitl.md` | 338 | No |
| `maf-orchestration-patterns/references/group-chat-magentic.md` | 302 | No |
| `maf-workflow-fundamentals/references/workflow-agents.md` | 270 | No (under 300, included for reference) |
| `maf-workflow-fundamentals/references/state-and-checkpoints.md` | 249 | No (under 300) |

**Verdict: Major — 17 reference files over 300 lines lack a TOC**

---

## 6. Code Examples

**Source**: skill-creator-ms, create-skill

### Python Code Examples

| Criterion | Status | Notes |
|-----------|--------|-------|
| Python examples present | **Pass** | All 10 SKILL.md files and all 30 reference files contain Python code |
| Install commands | **Pass** | Most skills include `pip install` commands |
| Environment variables | **Pass** | Documented in maf-agent-types, maf-middleware-observability, maf-getting-started |
| Authentication patterns | **Pass** | `AzureCliCredential` and `DefaultAzureCredential` both used appropriately |
| Cleanup/delete in examples | **Minor** | Not all examples show cleanup; some Foundry examples do |

### Authentication Pattern

The skill-creator-ms mandates `DefaultAzureCredential`. The MAF skills use a mix:
- `AzureCliCredential` — used in maf-ag-ui quick start and several examples (simpler for dev)
- `DefaultAzureCredential` — mentioned in maf-agent-types, used in reference files

This is acceptable because MAF documentation itself uses `AzureCliCredential` for development examples while `DefaultAzureCredential` is mentioned as the production pattern. The maf-agent-types skill explicitly notes: "Use `AzureCliCredential` or `DefaultAzureCredential` for Azure-hosted providers."

### Code Example Language Markers

All code blocks use proper language markers (```python, ```bash, ```yaml).

**Verdict: Pass (Minor: some examples lack cleanup code)**

---

## 7. Reference File Quality

**Source**: skill-development, skill-creator

### Organization

| Criterion | Status |
|-----------|--------|
| Organized by feature | **Pass** — Each reference focuses on a specific feature area |
| Focused on specific topic | **Pass** — Clear single-topic references |
| Size: 2,000–5,000 words ideal | **Pass** — Range: ~1,100 to ~3,000 words |
| Cross-references where appropriate | **Pass** — Skills cross-reference each other (e.g., maf-hosting-deployment → maf-ag-ui) |

### Reference File Distribution

| Skill | Ref Files | Total Ref Lines | Avg Lines/File |
|-------|-----------|----------------|----------------|
| maf-ag-ui-py | 4 | 1,259 | 315 |
| maf-agent-types-py | 4 | 1,438 | 360 |
| maf-declarative-workflows-py | 3 | 1,142 | 381 |
| maf-getting-started-py | 3 | 607 | 202 |
| maf-hosting-deployment-py | 2 | 553 | 277 |
| maf-memory-state-py | 2 | 630 | 315 |
| maf-middleware-observability-py | 3 | 934 | 311 |
| maf-orchestration-patterns-py | 3 | 894 | 298 |
| maf-tools-rag-py | 3 | 840 | 280 |
| maf-workflow-fundamentals-py | 3 | 756 | 252 |

**Verdict: Pass**

---

## 8. Anti-Patterns Check

**Source**: create-skill, skill-creator-ms

### Windows-Style Paths

**Pass** — Zero backslash path separators found across all 40 files.

### Time-Sensitive Information

**Major** — Multiple instances of time-sensitive language that will become outdated:

| File | Line | Content | Severity |
|------|------|---------|----------|
| `maf-memory-state/SKILL.md` | 104 | "Python support is coming soon. Continuation tokens and stream resumption are not yet available in the Python SDK." | Major |
| `maf-hosting-deployment/SKILL.md` | 13 | "Understand what is available today vs. coming soon." | Major |
| `maf-hosting-deployment/SKILL.md` | 26 | "**Coming soon in Python:**" (entire section) | Major |
| `maf-declarative-workflows/SKILL.md` | 26 | "Python 3.14 not yet supported due to PowerFx compatibility" | Minor |
| `maf-hosting-deployment/references/deployment-landscape.md` | 9-14 | "Coming soon", "In the works" (multiple lines) | Major |
| `maf-hosting-deployment/references/deployment-landscape.md` | 127 | "Python Hosting Roadmap" (entire section) | Major |
| `maf-hosting-deployment/references/devui.md` | 14 | "C# documentation for DevUI is coming soon" | Minor |
| `maf-memory-state/references/context-providers.md` | 3, 268 | "Python support coming soon" (2 instances) | Major |
| `maf-agent-types/references/anthropic-provider.md` | 19, 199, 233, 253 | Version-specific dates: "skills-2025-10-02", "files-api-2025-04-14", "claude-sonnet-4-5-20250929" | Minor (API model IDs are inherently versioned) |

**Recommendation**: Replace "coming soon" / "not yet available" with a versioned statement or move to a "Current Limitations" section as per create-skill anti-pattern guidance.

### Inconsistent Terminology

**Pass** — Terminology is generally consistent across all skills. Key terms used uniformly:
- "Agent Framework" (not "MAF" interchangeably in prose — though "MAF" is used in skill names and descriptions)
- "chat client" (consistent)
- "thread" (consistent for conversation state)
- "executor" (consistent for workflow nodes)

### Vague Descriptions

**Pass** — No vague descriptions found.

### Too Many Options Without Defaults

**Pass** — Skills provide clear defaults and recommendations (e.g., "Use DevUI for testing, AG-UI + FastAPI for production").

### Missing Authentication Sections

**Pass** — Authentication is covered in maf-agent-types and maf-ag-ui, with cross-references from other skills.

### Deeply Nested References

**Pass** — All references are one level deep from SKILL.md.

**Verdict: Major (time-sensitive content), otherwise Pass**

---

## 9. Missing Elements

**Source**: skill-creator-ms

### Acceptance Criteria

**Major** — No `references/acceptance-criteria.md` file exists for any of the 10 skills. The skill-creator-ms guide requires:

> "Every skill MUST have acceptance criteria and test scenarios."
> Location: `.github/skills/<skill-name>/references/acceptance-criteria.md`

With correct/incorrect code patterns documenting:
- Import paths
- Authentication patterns
- Client initialization
- Async variants
- Common anti-patterns

### Test Scenarios

**Major** — No `tests/scenarios/<skill-name>/scenarios.yaml` files exist. The skill-creator-ms guide requires:
- Each scenario tests ONE specific pattern
- `expected_patterns` — patterns that MUST appear
- `forbidden_patterns` — common mistakes
- `mock_response` — complete working code

### Symlinks for Categorization

**Major** — No symlinks exist in a `skills/<language>/<category>/` structure. The skill-creator-ms guide requires:

```
skills/python/<category>/<short-name> -> ../../../.github/skills/<full-skill-name>
```

**Note**: This may not apply since these skills are stored in a flat `skills/` directory rather than `.github/skills/`, suggesting they follow a different organizational convention. This should be evaluated against the actual project structure intent.

### Scripts Directory

**Pass (N/A)** — No scripts are needed for these documentation-style skills. They don't involve deterministic operations or repeated code patterns.

### Version Field

**Pass** — All 10 skills include `version: 0.1.0` in frontmatter (this is good practice though not required by all guides).

**Verdict: Major (missing acceptance criteria and test scenarios)**

---

## 10. Per-Skill Scorecard Summary

| Dimension | ag-ui | agent-types | decl-wf | getting-started | hosting | memory | middleware | orchestration | tools-rag | wf-fund |
|-----------|-------|-------------|---------|-----------------|---------|--------|------------|---------------|-----------|---------|
| 1. Naming | Fixed | Fixed | Fixed | Fixed | Fixed | Fixed | Fixed | Fixed | Fixed | Fixed |
| 2. Description | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass |
| 3. Structure | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass |
| 4. Writing Style | Pass | Pass | Pass | Pass | Minor | Pass | Pass | Pass | Pass | Pass |
| 5. Progressive Disclosure | Major | Major | Major | Pass | Major | Major | Major | Major | Major | Pass |
| 6. Code Examples | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass |
| 7. Reference Quality | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass | Pass |
| 8. Anti-Patterns | Pass | Minor | Pass | Pass | Major | Major | Pass | Pass | Pass | Pass |
| 9. Missing Elements | Major | Major | Major | Major | Major | Major | Major | Major | Major | Major |

### Rating Key
- **Pass** — Meets documentation standards
- **Minor** — Small deviations, easy fixes
- **Major** — Significant gaps requiring attention
- **Fixed** — Was non-compliant, now corrected

---

## 11. Cross-Cutting Analysis

### Shared Strengths

1. **Consistent structure**: All 10 skills follow the same internal pattern (frontmatter → intro → overview → code → concepts → resources). This makes the skill set predictable and learnable.

2. **Good progressive disclosure**: Core content in SKILL.md is lean (109–201 lines), with detailed content properly delegated to reference files. No duplication observed between SKILL.md and references.

3. **Strong description quality**: All descriptions use correct third-person format, include multiple quoted trigger phrases (8–14 each), mention Python explicitly, and include both WHAT and WHEN.

4. **Clean code examples**: All Python code is properly formatted, uses appropriate language markers, includes realistic imports and patterns, and demonstrates the actual MAF API correctly.

5. **No anti-pattern violations**: Zero Windows paths, consistent terminology, no deeply nested references, clear defaults provided.

6. **Good cross-referencing**: Skills reference each other where relevant (e.g., maf-hosting-deployment → maf-ag-ui, maf-getting-started → all other skills via "What to Learn Next" table).

### Shared Weaknesses

1. **Missing TOC in large reference files** (affects 8/10 skills, 17 files): This is the most widespread structural gap. Adding a table of contents to all reference files over 300 lines would improve navigability.

2. **Time-sensitive content** (affects 3/10 skills): "Coming soon", "not yet available", "in the works" will become outdated. These should be replaced with versioned limitation statements.

3. **No acceptance criteria or test scenarios** (affects all 10 skills): The skill-creator-ms guide mandates these for validation. This is the largest gap from the documentation standards.

4. **Word count below ideal range** (affects all 10 skills): All SKILL.md bodies are under 1,500 words (range: 900–1,450). While conciseness is valued, some skills may benefit from slightly more content — particularly around common pitfalls, best practices, or decision guidance.

5. **Description pushiness** (affects all 10 skills): Descriptions are functional but could be more aggressive to prevent under-triggering. Adding "even if" or "Make sure to use this skill whenever..." clauses would help.

### Skills That Deviate Most

| Rank | Skill | Issues |
|------|-------|--------|
| 1 | maf-hosting-deployment-py | Time-sensitive content (entire "Coming soon" section), second-person writing, large refs without TOC |
| 2 | maf-memory-state-py | Time-sensitive content ("coming soon" in SKILL.md and reference), large refs without TOC |
| 3 | maf-agent-types-py | Anthropic reference has version-specific dates, large refs without TOC |

### Priority Fixes (High Impact, Low Effort)

1. **Add TOC to 17 reference files >300 lines** — Mechanical change, high impact on navigation
2. **Replace time-sensitive language** in 3 skills — Small text edits, prevents outdated content
3. **Fix one second-person instance** in maf-hosting-deployment — Single line edit
4. **Increase description pushiness** across all 10 — Add "even if" / "whenever" clauses to descriptions

### Lower Priority (Higher Effort)

5. **Create acceptance criteria** for all 10 skills — Requires documenting correct/incorrect patterns for each
6. **Create test scenarios** for all 10 skills — Requires defining expected/forbidden patterns
7. **Consider expanding SKILL.md body** to 1,500+ words where beneficial — May not be needed if current content is sufficient

---

## 12. Applicability of skill-creator-ms Azure SDK Patterns

The skill-creator-ms guide was designed for Azure SDK skills (e.g., `azure-ai-agents-py`, `azure-cosmos-db-py`). The MAF skills are framework documentation skills rather than SDK API reference skills. Key differences:

| Pattern | SDK Skills | MAF Skills | Applicability |
|---------|-----------|-----------|---------------|
| Section order (Install → Auth → Core → Tables → Best Practices) | Required | Not directly applicable | These are multi-concept framework guides, not single-SDK references |
| `DefaultAzureCredential` always | Required | Mix of AzureCliCredential and DefaultAzureCredential | Acceptable — MAF docs use both |
| Naming: `azure-<service>-<subservice>-<lang>` | Required | `maf-<feature>-py` | Adapted appropriately for framework skills |
| Symlinks in `skills/<language>/<category>/` | Required | Not implemented | May not apply to this repo's structure |
| Acceptance criteria + test scenarios | Required | Not implemented | Should be created |
| README.md catalog update | Required | Not applicable | Different repo structure |

**Conclusion**: The acceptance criteria and test scenarios requirements from skill-creator-ms should be adopted. The SDK-specific section order and symlink patterns are not directly applicable to framework documentation skills but the spirit of organized, testable content applies.

