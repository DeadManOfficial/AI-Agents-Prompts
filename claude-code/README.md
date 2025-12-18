# Claude Code System Prompts

> Comprehensive documentation of Claude Code's modular prompt architecture (v2.0.71)

## Architecture Overview

Claude Code uses **40+ modular prompt components** rather than a single monolithic system prompt. Components are dynamically loaded based on environment, configs, and user context.

## Prompt Categories

### Core System (3,097 tokens)
Main system prompt defining behavior, tone, and tool usage policies.

### Agent Prompts
| Agent | Tokens | Purpose |
|-------|--------|---------|
| Explore Agent | 516 | Discovery and codebase analysis |
| Plan Mode Enhanced | 633 | Sophisticated implementation planning |
| Task Tool | 294 | Subagent spawning and coordination |

### Creation Assistants
| Assistant | Tokens | Purpose |
|-----------|--------|---------|
| Agent Creation Architect | 1,111 | Design custom agents |
| CLAUDE.md Generator | 384 | Project documentation |
| Status Line Setup | 1,310 | CLI configuration |

### Slash Commands
| Command | Tokens | Purpose |
|---------|--------|---------|
| /security-review | 2,610 | Comprehensive security analysis |
| /review-pr | 243 | Pull request review |
| /pr-comments | 402 | PR comment handling |

### Tool Descriptions (16 builtin tools)
| Tool | Tokens | Purpose |
|------|--------|---------|
| Bash | 1,074 | Shell command execution |
| TodoWrite | 2,167 | Task management |
| Task | 1,193 | Specialized sub-agents |
| EnterPlanMode | 970 | Planning workflows |
| ReadFile | 439 | File reading |
| Write | 159 | File writing |

### Utility Prompts
- Bash output summarization (605 tk)
- Conversation summarization (1,121 tk)
- Session title generation (333 tk)
- WebFetch summarizer (185 tk)
- Learning Mode (1,042 tk)
- Browser Automation (758 tk)

## Key Architecture Notes

1. **Conditional Loading**: Prompts load dynamically based on context
2. **Distributed Design**: No single injection point prevents simple prompt injection
3. **Customizable**: Use `tweakcc` to modify individual components

## Source
[Piebald-AI/claude-code-system-prompts](https://github.com/Piebald-AI/claude-code-system-prompts)
