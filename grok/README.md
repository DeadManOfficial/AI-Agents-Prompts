# Grok System Prompts

> Official xAI Grok prompts from the public repository

## Available Prompts

### Grok 4 Series
| File | Purpose |
|------|---------|
| `grok4_system_turn_prompt_v8.j2` | Main system prompt for Grok 4 chat (grok.com/X) |
| `grok_4_safety_prompt.txt` | Safety prefix for grok-4-0709 API model |
| `grok_4_mini_system_prompt.txt` | Safety prefix for grok-4-fast API |
| `grok_4_code_rc1_safety_prompt.txt` | Safety prefix for grok-code-fast-1 API |

### Grok 4.1 Series
| File | Purpose |
|------|---------|
| `grok4p1_non_thinking_no_tool_system_turn_prompt.j2` | Grok 4.1 (no tools) |
| `grok4p1_non_thinking_system_turn_prompt.j2` | Grok 4.1 with tool support |
| `grok4p1_thinking_system_turn_prompt_v2.j2` | Grok 4.1 thinking variant |

### Legacy & Features
| File | Purpose |
|------|---------|
| `grok3_official0330_p1.j2` | Grok 3 system prompt |
| `grok_analyze_button.j2` | "Grok Explain" feature on X |
| `ask_grok_system_prompt.j2` | @grok bot configuration |

## Repository Details

- **Source**: [xai-org/grok-prompts](https://github.com/xai-org/grok-prompts)
- **License**: AGPL-3.0
- **Stars**: 3.7k+ | **Forks**: 382 | **Watchers**: 118

## Key Features

1. **Jinja2 Templates**: All prompts use `.j2` templating for dynamic content
2. **Multi-Context**: Different prompts for web, API, and X platform
3. **Safety Prefixes**: Dedicated safety prompts for API models
4. **Transparency**: xAI publishes prompts publicly for accountability
