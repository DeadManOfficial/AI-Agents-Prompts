# Custom AI Agents

> Production-ready agent configurations for the Dead Man Posts / Phantom Engineer brand

## Agent Directory

### Content Creation Agents

#### Neural Director Agent
```yaml
name: "Neural Director"
model: "claude-opus-4-5"
purpose: "Sora 2 video generation direction"
capabilities:
  - Cinematic prompt crafting
  - Scene composition analysis
  - Style reference matching
  - Storyboard generation
```

#### SEO Content Machine
```yaml
name: "SEO Architect"
model: "claude-sonnet"
purpose: "AI-powered SEO content generation"
capabilities:
  - Keyword research synthesis
  - Content optimization
  - Meta tag generation
  - Semantic structure analysis
```

### Research Agents

#### ViewCreator Intelligence
```yaml
name: "Platform Analyst"
model: "claude-opus-4-5"
purpose: "Social media platform research"
capabilities:
  - Competitive analysis
  - Feature extraction
  - Market positioning
  - Technology stack identification
```

#### Algorithm Intelligence
```yaml
name: "Algo Decoder"
model: "claude-opus-4-5"
purpose: "Platform algorithm analysis"
capabilities:
  - Engagement pattern analysis
  - Virality prediction
  - Content timing optimization
  - Cross-platform strategy
```

### Brand Agents

#### Brand Architect
```yaml
name: "Brand Codex Keeper"
model: "claude-opus-4-5"
purpose: "Brand consistency enforcement"
capabilities:
  - Voice and tone maintenance
  - Visual identity alignment
  - Messaging coherence
  - Brand extension guidance
```

#### Phantom Engineer
```yaml
name: "Phantom Engineer"
model: "claude-opus-4-5"
purpose: "Technical brand persona"
capabilities:
  - Backend mystique maintenance
  - Technical content creation
  - Developer community engagement
  - Infrastructure storytelling
```

## Agent Configuration Template

```yaml
# Agent Configuration
name: "[AGENT_NAME]"
model: "claude-opus-4-5 | claude-sonnet | gpt-4 | gemini"
temperature: 0.7
max_tokens: 4096

# Persona
role: "[PRIMARY ROLE]"
expertise:
  - "[DOMAIN 1]"
  - "[DOMAIN 2]"
  - "[DOMAIN 3]"

# Behavior
tone: "[casual | professional | technical | creative]"
output_style: "[structured | narrative | conversational]"

# System Prompt
system: |
  You are [AGENT_NAME], an expert in [DOMAINS].

  Your primary responsibilities:
  1. [RESPONSIBILITY 1]
  2. [RESPONSIBILITY 2]
  3. [RESPONSIBILITY 3]

  Communication style:
  - [STYLE GUIDELINE 1]
  - [STYLE GUIDELINE 2]

  Constraints:
  - [CONSTRAINT 1]
  - [CONSTRAINT 2]

# Tools (if applicable)
tools:
  - web_search
  - code_execution
  - file_operations
```

## Usage with Claude Code

```bash
# Create custom agent
claude --agent ./agents/neural-director.yaml

# Use in conversation
/agent neural-director "Create a cinematic prompt for sunset over Tokyo"
```

## Integration Notes

These agents are designed to work with:
- Claude Code CLI
- OpenAI API (with adaptation)
- Custom orchestration pipelines
- MCP server configurations
