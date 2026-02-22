# skills/

Script-based agent workflows with shared orchestration framework.

## MANDATORY: Read Before Modifying

**STOP. Before editing ANY Python file in `skills/scripts/`, you MUST read `README.md`.**

The README defines:

- File section ordering (SHARED PROMPTS -> CONFIGURATION -> MESSAGE TEMPLATES -> MESSAGE BUILDERS -> STEP DEFINITIONS -> OUTPUT FORMATTING -> ENTRY POINT)
- Step-delimited prompt organization within MESSAGE TEMPLATES
- Naming conventions for prompt constants (`[PHASE]_[TYPE]`)
- Patterns for dispatch prompts (static templates vs builder functions)
- Anti-patterns to avoid (action factories, forward references)

Failure to follow these patterns creates technical debt and inconsistency across skills. The patterns exist because they solve real problems with prompt readability and maintenance.

**Read `README.md` now if you haven't already.**

## Files

| File        | What                                                      | When to read                    |
| ----------- | --------------------------------------------------------- | ------------------------------- |
| `README.md` | File organization, prompt patterns, naming, anti-patterns | BEFORE modifying any skill code |

## Subdirectories

| Directory             | What                                      | When to read                             |
| --------------------- | ----------------------------------------- | ---------------------------------------- |
| `scripts/`            | Python package root for all skill code    | Executing skills, debugging behavior     |
| `planner/`            | Planning and execution workflows          | Creating implementation plans            |
| `refactor/`           | Refactoring analysis across dimensions    | Technical debt review, code quality      |
| `problem-analysis/`   | Structured problem decomposition          | Understanding complex issues             |
| `decision-critic/`    | Decision stress-testing and critique      | Validating architectural choices         |
| `deepthink/`          | Structured reasoning for open questions   | Analytical questions without frameworks  |
| `codebase-analysis/`  | Systematic codebase exploration           | Repository architecture review           |
| `prompt-engineer/`    | Prompt optimization and engineering       | Improving agent prompts                  |
| `incoherence/`        | Consistency detection                     | Finding spec/implementation mismatches   |
| `doc-sync/`           | Documentation synchronization             | Syncing docs across repos                |
| `leon-writing-style/` | Style-matched content generation          | Writing content matching user's style    |
| `arxiv-to-md/`        | arXiv paper to markdown conversion        | Converting papers for LLM consumption    |
| `cc-history/`         | Claude Code conversation history analysis | Querying past conversations, token usage |

### LangChain Skills (from @siddicky/langchain-skills)

Skills for building, observing, and evaluating agents with LangChain, LangGraph, LangSmith, and Deep Agents.

| Directory                   | What                                                        | When to read                                  |
| --------------------------- | ----------------------------------------------------------- | --------------------------------------------- |
| `framework-selection/`      | Framework comparison (LangChain vs LangGraph vs Deep Agents)| Starting a new agent project                  |
| `langchain-dependencies/`   | Package versions and dependency management (Python + TS)    | Setting up or updating project dependencies   |
| `deep-agents-core/`         | Agent architecture, harness setup, SKILL.md format          | Building Deep Agents applications             |
| `deep-agents-memory/`       | Memory, persistence, filesystem middleware                  | Adding memory or persistence to Deep Agents   |
| `deep-agents-orchestration/`| Subagents, task planning, human-in-the-loop                 | Orchestrating with subagents or HITL          |
| `langchain-fundamentals/`   | Chat models, agents, tools, middleware                      | Writing LangChain agent code                  |
| `langchain-output/`         | Structured output with Pydantic/Zod, HITL middleware        | Needing typed output or human approval        |
| `langchain-rag/`            | RAG pipeline (document loaders, embeddings, vector stores)  | Building retrieval-augmented generation       |
| `langgraph-fundamentals/`   | StateGraph, nodes, edges, state reducers                    | Writing LangGraph code                        |
| `langgraph-persistence/`    | Checkpointers, thread_id, cross-thread memory               | Adding persistence to LangGraph               |
| `langgraph-execution/`      | Workflows, interrupts, streaming modes                      | Advanced LangGraph execution control          |
| `langsmith-trace/`          | Query and export traces (includes helper scripts)           | Debugging or analyzing LangSmith traces       |
| `langsmith-dataset/`        | Generate evaluation datasets from traces (includes scripts) | Creating datasets for evaluation              |
| `langsmith-evaluator/`      | Create custom evaluators (includes helper scripts)          | Building evaluators for LangSmith             |

## Script Invocation

All Python skill scripts are invoked as modules from `scripts/`:

<invoke working-dir=".claude/skills/scripts" cmd="python3 -m skills.<skill_name>.<module> --step 1" />

Example:

<invoke working-dir=".claude/skills/scripts" cmd="python3 -m skills.problem_analysis.analyze --step 1" />
