🌍 Language:
[English](README.md) | [Português](README.pt-BR.md) | [Español](README.es.md)

# AI Skills — A Practical Guide
From prompts to systems — learn how to build reusable AI skills.

Skills are one of the core building blocks of modern AI systems. 
They allow you to define reusable, task-specific capabilities that an AI system can automatically apply when relevant — without repeating instructions every time.

⭐ If this project helped you, please consider giving it a star — it helps others discover it and supports the work!

## Table of Contents

- [Skills Quick Guide](#skills-quick-guide)
- [What are Skills](#what-are-skills)
- [How Skills Work](#how-skills-work)
- [Skill Structure](#skill-structure)
- [Where Skills Live](#where-skills-live)
- [Skills vs Other Customizations](#skills-vs-other-customizations)
- [When to Use Skills](#when-to-use-skills)
- [Example Use Cases](#example-use-cases)
- [Creating Your First Skill](#-creating-your-first-skill)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Advanced Concepts](#advanced-concepts)
- [Why Skills Matter](#why-skills-matter)
- [Resources](#resources)
- [Final Thought](#final-thought)
- [Contributing](#-contributing)
- [Connect with me](#-connect-with-me)

## Skills Quick Guide

A quick visual reference to understand how skills work — from structure to activation.

<img src="https://raw.githubusercontent.com/elisaterumi-ai/agent-skills-in-practice/main/img/skills-guide-en.png" width="600"/>

> 💡 Use this as a quick reference while building your own skills.


## What are Skills?

A **skill** is a structured set of instructions that teaches an AI system how to perform a specific task.

In Claude Code, a skill is:

- A directory  
- Containing a `SKILL.md` file  
- With metadata and instructions  

Once defined, the system can discover and use the skill automatically.

> Instead of repeating prompts, you encode behavior once — and reuse it.

## How Skills Work

Skills follow a **semantic matching workflow**:

1. The system loads only skill **names and descriptions**
2. A user request is received
3. The system compares the request with available skill descriptions
4. Matching skills are selected
5. The full skill content is loaded and executed

This means:

- Skills are **loaded on demand**
- They do **not clutter context unnecessarily**
- They activate **only when relevant**


## Skill Structure

Each skill lives inside a directory and must contain a `SKILL.md` file.

### Example:

```yaml
---
name: pr-review
description: Reviews pull requests for code quality. Use when reviewing PRs or checking code changes.
---
```

Below the frontmatter, you define the instructions:

```yaml
When reviewing a PR:

1. Analyze code changes
2. Check for best practices
3. Suggest improvements
4. Format output as structured feedback
```

## Where Skills Live

Skills can be scoped at different levels:

### Personal Skills
- Location: `~/.claude/skills`
- Available across all your projects
- Ideal for personal workflows

### Project Skills
- Location: `.claude/skills` (inside a repository)
- Shared via version control
- Used for team standards

## Skills vs Other Customizations

| Feature           | Behavior                | Use Case                |
|-------------------|------------------------|--------------------------|
| **Skills**        | Load on demand         | Task-specific expertise |
| **CLAUDE.md**     | Always loaded          | Global project rules    |
| **Slash Commands**| Manual invocation      | Explicit actions        |

👉 Skills are **automatic and contextual**

## When to Use Skills

Use a skill when:

- You repeat the same instructions frequently
- You need consistent output formats
- You want reusable workflows
- You want to share knowledge across a team

**Rule of thumb:**
> If you explain the same thing more than once, it should be a skill.

## Example Use Cases

- Code review standards  
- Commit message formatting  
- Documentation templates  
- Debugging checklists  
- Data transformation workflows  
- Clinical text anonymization  

👉 Explore ready-to-use skills: [examples](examples)

> Some examples are inspired by existing open-source skill repositories.


## 🚀 Creating Your First Skill

### Step 1 — Create directory

```bash
mkdir -p ~/.claude/skills/my-skill
```

### Step 2 — Create `SKILL.md` (or use the template)

Create a `SKILL.md` file inside your skill directory, or copy from the [provided template](templates/skill-template.md).

```yaml
---
name: my-skill
description: Describe what the skill does and when to use it.
---
```

### Step 3 — Add instructions

Define:

- Steps
- Rules
- Output format

## Best Practices

- Write **clear and specific descriptions** (this controls activation)
- Keep instructions **structured and explicit**
- Define **expected output formats**
- Avoid overly generic skills
- Keep `SKILL.md` concise (use references if needed)

## Common Mistakes

- Treating skills as simple prompts  
- Writing vague descriptions (skill won’t trigger)  
- Overloading a single skill with multiple responsibilities  
- Not defining output structure  


## Advanced Concepts

### Metadata Fields

- `name` (required)
- `description` (required)
- `allowed-tools` (optional)
- `model` (optional)

### Progressive Disclosure

- Keep core logic in `SKILL.md`
- Move large content to:
  - `references/`
  - `scripts/`
  - `assets/`

## Why Skills Matter

Skills transform how we build with AI:

- From **prompts → reusable systems**
- From **manual instructions → automatic behavior**
- From **experimentation → production-ready workflows**

They are a key building block for:

- AI agents  
- Automation pipelines  
- Scalable AI systems  



## Resources

Curated links, documentation, and example repositories:

👉 [Explore resources](docs/resources.md)

## Final Thought

Skills shift the mindset from:

> “What should I ask the model?”

To:

> “What capability should this system have?”

## 🤝 Contributing

Contributions are welcome!

Ways to contribute:

- Add new skills or use cases
- Improve documentation and examples
- Report issues or suggest improvements

Feel free to open an issue or submit a pull request 🚀

## 🔗 Connect with me

I share practical insights about AI, agents, and real-world applications:

- LinkedIn (Profile): https://www.linkedin.com/in/elisa-terumi  
- LinkedIn (Page): https://www.linkedin.com/company/exploring-artificial-intelligence  
- Newsletter: https://exploringartificialintelligence.substack.com/  
- Medium: https://medium.com/@elisa-terumi

## Star History

<a href="https://www.star-history.com/?repos=elisaterumi-ai%2Fagent-skills-in-practice&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=elisaterumi-ai/agent-skills-in-practice&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=elisaterumi-ai/agent-skills-in-practice&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=elisaterumi-ai/agent-skills-in-practice&type=date&legend=top-left" />
 </picture>
</a>
