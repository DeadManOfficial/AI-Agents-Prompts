# Gemini Gems Collection

> Specialized AI prompt templates for Google Gemini

## Overview

Gemini Gems are structured system prompts that transform Gemini into domain-expert assistants. The collection includes **21 curated gems** across **8 categories**.

## Categories

### Development
- Code Review Architect
- Codebase Forensics
- Documentation Architect
- Programming Co-Pilot
- System Architect
- README Architect
- GitHub Branch Name Generator

### Education
- Grammar Teacher
- Language Teacher

### Business
- Marketing Strategist
- Professional Email Crafter
- Task Breakdown Manager

### Creative
- Storyteller-Novelist
- GameForge Master
- PromptSmith
- Gem Creator

### Finance
- Personal Finance Navigator

### Wellness
- Wellness Mindfulness Coach

### Lifestyle
- DIY Tinkerer
- Sous Chef

### Utility
- DUA Generator

## Gem Structure

Each gem uses markdown with YAML frontmatter:

```yaml
---
title: "Code Review Architect"
description: "Expert code review assistant"
category: "Development"
icon: "code"
color: "#3b82f6"
features:
  - "Security analysis"
  - "Performance review"
  - "Best practices"
lastUpdated: "2025-01-15"
---

[System prompt content in markdown...]
```

## Technical Stack

- **Frontend**: Astro 5.15.9, TypeScript, Tailwind CSS
- **Validation**: Zod schemas via Astro Content Collections
- **Hosting**: GitHub Pages

## Source

[nirzaf/gemini-gems](https://github.com/nirzaf/gemini-gems)
