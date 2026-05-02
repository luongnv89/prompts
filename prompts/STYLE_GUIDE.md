# Prompt Style Guide

This guide defines the standard format for all prompts in this repository.

## Overview

All prompts should use YAML front matter and follow a consistent structure for clarity, maintainability, and optimal AI performance.

## Front Matter Format

Every prompt file must include YAML front matter at the top:

```yaml
---
summary: "Brief description of what this prompt does (1-2 sentences)"
usage: "How to use this prompt with clear examples"
date: YYYY-MM-DD
tags:
  - tag1
  - tag2
  - tag3
---
```

- **summary**: 1-2 sentence description of the prompt's purpose
- **usage**: Clear instructions on how to use this prompt
- **date**: Creation or last modification date
- **tags**: 3-6 relevant tags (lowercase, hyphenated)

## Format Templates

### 1. Standard Prompt Template

For general-purpose prompts that guide AI behavior:

```yaml
---
summary: "Brief description of what this prompt does"
usage: "How to use this prompt with clear examples"
date: YYYY-MM-DD
tags:
  - tag1
  - tag2
  - tag3
---
# Role
[What role should the AI play]

# Goal
[What is the desired outcome]

# Instructions
[Step-by-step instructions for the AI]

# Output Format
[Specify the exact format required]

# Examples
### Example 1
[Input]: [sample input]
[Output]: [sample output]

# Constraints
[Any limitations or rules]
```

### 2. System Prompt Template

For role-playing and system-level prompts:

```yaml
---
summary: "Brief description"
usage: "How to use this prompt"
date: YYYY-MM-DD
tags:
  - system
  - role
---
# System Prompt
[Direct instruction to AI as a system component]

# Context
[Background information]

# Persona
[Personality traits and characteristics]

# Workflow
[Step-by-step process]

# Output
[Expected output format]
```

### 3. Workflow/Process Template

For step-by-step processes and procedures:

```yaml
---
summary: "Brief description"
usage: "How to use this prompt"
date: YYYY-MM-DD
tags:
  - workflow
  - process
---
# Objective
[Overall goal]

# Steps
1. [First step]
2. [Second step]
3. [Third step]

# Verification
[How to verify correct output]

# Output Format
[Expected format with examples]
```

### 4. Analysis Template

For analytical and diagnostic prompts:

```yaml
---
summary: "Brief description"
usage: "How to use this prompt"
date: YYYY-MM-DD
tags:
  - analysis
  - diagnostic
---
# Analysis Framework
[Model or framework to use]

# Inputs
[List of required inputs]

# Process
1. [First analysis step]
2. [Second analysis step]

# Output Format
[Structured output with sections]

# Constraints
[Any limitations]
```

## General Guidelines

### File Naming
- Use hyphenated lowercase: `category_subcategory_name.md`
- For system prompts, prefix with `system_`

### Content Structure
- Use clear section headers with `#`, `##`, `###`
- Number steps in processes
- Use bullet points for lists
- Include code blocks with appropriate syntax highlighting

### Language
- Be direct and actionable
- Use imperative mood for instructions
- Include specific examples
- Explain reasoning when helpful

### Tags
- Use 3-6 relevant tags
- Lowercase with hyphens: `tag-name`
- Include category, type, and specific tags

## Testing

After modifying prompts, regenerate the data:

```bash
node scripts/generate_prompt_data.js
```

Verify the output in `website/src/data/prompts.json`.
