# Prompt Engineering Guide

> Advanced techniques for effective AI prompting across all major models

## Core Principles

### 1. Clarity Over Cleverness
Be explicit about what you want. Models perform better with clear instructions than with clever tricks.

### 2. Structure Matters
```
[ROLE/PERSONA]
[CONTEXT]
[TASK]
[CONSTRAINTS]
[OUTPUT FORMAT]
[EXAMPLES]
```

### 3. Chain of Thought
For complex reasoning, ask the model to think step-by-step:
```
Think through this step by step:
1. First, identify...
2. Then, analyze...
3. Finally, conclude...
```

## Model-Specific Techniques

### Claude
- Use XML tags for structure: `<context>`, `<task>`, `<output>`
- Leverage Claude's strong reasoning with explicit logic chains
- Use artifacts for code and structured outputs

### GPT-4/ChatGPT
- System message sets persistent behavior
- Temperature controls creativity (0.0-2.0)
- Function calling for structured data extraction

### Gemini
- Multimodal prompts: combine text, images, code
- Use Gems for specialized domain knowledge
- Strong at code generation and analysis

### Grok
- Real-time X/Twitter context awareness
- Less restrictive on certain topics
- Good for current events analysis

## Advanced Patterns

### Few-Shot Learning
```
Example 1:
Input: [example input]
Output: [example output]

Example 2:
Input: [example input]
Output: [example output]

Now process this:
Input: [actual input]
Output:
```

### Role-Based Prompting
```
You are an expert [ROLE] with [X] years of experience in [DOMAIN].
Your task is to [SPECIFIC TASK].
Consider [IMPORTANT FACTORS].
Respond in the style of [STYLE REFERENCE].
```

### Meta-Prompting
```
Before answering, consider:
- What assumptions am I making?
- What information is missing?
- What's the best approach?

Then provide your response.
```

### Constitutional AI Pattern
```
When responding:
1. Be helpful and informative
2. Avoid harmful content
3. Be honest about limitations
4. Respect privacy and safety
```

## Output Formatting

### JSON Output
```
Respond with valid JSON in this format:
{
  "field1": "description",
  "field2": ["array", "items"],
  "field3": {
    "nested": "object"
  }
}
```

### Markdown Tables
```
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Data     | Data     | Data     |
```

### Code Blocks
````
Provide code in this format:
```language
// code here
```
````

## Quality Assurance

### Self-Verification
```
After generating your response:
1. Check for accuracy
2. Verify completeness
3. Ensure clarity
4. Confirm format compliance
```

### Iterative Refinement
```
Initial response: [response]

Now improve this by:
- Adding more detail to [section]
- Clarifying [concept]
- Restructuring for better flow
```

## Resources

- [dair-ai/Prompt-Engineering-Guide](https://github.com/dair-ai/Prompt-Engineering-Guide)
- [langgptai/awesome-gemini-prompts](https://github.com/langgptai/awesome-gemini-prompts)
- [EliFuzz/awesome-system-prompts](https://github.com/EliFuzz/awesome-system-prompts)
