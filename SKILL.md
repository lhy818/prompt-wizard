---
name: prompt-wizard
version: 1.0.0
description: |
  Transform user requirements into effective prompts using best practices from 10 leading Prompt Engineering resources. This skill serves as a comprehensive reference and guide for crafting prompts that follow industry best practices from Anthropic, OpenAI, Hugging Face, and more.
homepage: https://www.promptingguide.ai/
repository: https://github.com/dair-ai/Prompt-Engineering-Guide
metadata:
  {
    "license": "MIT",
    "openclaw":
      {
        "emoji": "🧙",
        "requires": {},
        "install": []
      },
  }
---

# Prompt Wizard - Your Prompt Engineering Expert

**Transform any requirement into an effective, well-structured prompt.**

This skill consolidates knowledge from 10 world-class Prompt Engineering resources into a single, actionable guide. When you need to craft a prompt for any AI model (Claude, GPT, LLaMA, etc.), use this skill to ensure you're following best practices.

## Why This Skill?

| Problem | Solution |
|---------|-----------|
| Unclear requirements | Structured prompt framework |
| Trial and error | Evidence-based techniques |
| Generic prompts | Context-specific templates |
| Ignoring model differences | Model-specific guidance |
| No iteration strategy | Prompt optimization workflow |

## Core Philosophy

> **"Prompt engineering isn't magic. It's structured thinking."**
>
> **Constraints + iteration + testing. Study examples. Break prompts. Rebuild them better.**

### The Three Pillars

1. **Structure** - Clear organization, proper sections
2. **Context** - Relevant examples, constraints, format
3. **Iteration** - Test, refine, improve

---

## Quick Prompt Framework

When crafting any prompt, use this structure:

```
1. [Role/Identity] - Who is the AI?
2. [Task] - What should it do?
3. [Context] - What information does it need?
4. [Constraints] - What should it avoid?
5. [Format] - How should the output look?
6. [Examples] - Show, don't just tell
```

### Example: Code Review Prompt

```
Role: You are a senior software engineer with expertise in [LANGUAGE] and best practices for clean, maintainable code.

Task: Review the provided code snippet and identify:
- Bugs or potential issues
- Performance optimizations
- Code style improvements
- Security concerns

Context: This code will be used in [PRODUCTION/DEVELOPMENT] environment with these requirements: [LIST REQUIREMENTS]

Constraints:
- Do not suggest unnecessary refactoring
- Focus on actionable improvements
- Consider readability and maintainability
- Explain why each change is recommended

Format: Provide feedback in this structure:
1. **Issue**: Clear description
2. **Location**: Line numbers
3. **Severity**: Critical/High/Medium/Low
4. **Suggestion**: Code example
5. **Reason**: Why this matters

Examples:

Input:
[code snippet]

Output:
[example feedback]
```

---

## Best Practices Checklist

### Before Writing a Prompt

- [ ] Define success criteria
- [ ] Identify target model
- [ ] Gather necessary context
- [ ] Prepare examples (if few-shot)

### Writing the Prompt

- [ ] **Be specific**: Avoid ambiguity
- [ ] **Use structure**: Clear sections, XML tags, or delimiters
- [ ] **Set expectations**: Format, length, style
- [ ] **Provide context**: Relevant background, constraints
- [ ] **Use examples**: Show desired outputs
- [ ] **Focus on "what to do"**: Not "what not to do"

### After Writing

- [ ] Test with multiple examples
- [ ] Measure against success criteria
- [ ] Iterate based on failures
- [ ] Document what works

---

## Model-Specific Guidance

### Claude (Anthropic)

**Best for:** Complex reasoning, nuanced writing, safety-conscious tasks

**Key techniques:**
- Use XML tags for structure
- Provide clear role definitions
- Use "think step-by-step" for reasoning
- Leverage few-shot examples
- Be explicit about constraints

**Example structure:**
```xml
<role>
You are a [ROLE] with expertise in [DOMAIN].
</role>

<task>
[Clear description of what to do]
</task>

<context>
[Relevant information, constraints, background]
</context>

<format>
[Desired output format]
</format>

<examples>
[Example inputs and outputs]
</examples>
```

### OpenAI (GPT)

**Best for:** General-purpose, wide range of tasks

**Key techniques:**
- Use message roles (developer/user/assistant)
- Instructions in developer message
- Use chain-of-thought for reasoning
- Provide examples in conversation format
- Be specific about format

**Example structure:**
```python
messages = [
    {
        "role": "developer",
        "content": "You are a [ROLE] that [PURPOSE]. Follow these rules: [RULES]"
    },
    {
        "role": "user",
        "content": "[TASK with context and constraints]"
    },
    # Add examples if needed
]
```

### Open Source (LLaMA, Mistral, etc.)

**Best for:** Custom deployment, privacy, control

**Key techniques:**
- Use few-shot prompting extensively
- Provide clear examples
- Use structured format (templates, delimiters)
- Consider instruction-tuned vs base models
- Test multiple models

---

## Advanced Techniques

### 1. Chain-of-Thought (CoT)

**When to use:** Complex reasoning, multi-step problems

**How:**
```
Let's work through this step-by-step:

1. [First step reasoning]
2. [Second step reasoning]
3. [Third step reasoning]

Final answer: [Conclusion]
```

### 2. Few-Shot Prompting

**When to use:** Specific formats, patterns, or styles

**How:**
```
Example 1:
Input: [Input 1]
Output: [Output 1]

Example 2:
Input: [Input 2]
Output: [Output 2]

Example 3:
Input: [Input 3]
Output: [Output 3]

Now, your turn:
Input: [New input]
Output:
```

### 3. Prompt Chaining

**When to use:** Complex multi-stage tasks

**How:**
1. **Stage 1**: Extract/summarize
2. **Stage 2**: Analyze/categorize
3. **Stage 3**: Generate/present

### 4. Role Prompting

**When to use:** Specific personas, expertise levels

**How:**
```
You are a [EXPERT ROLE] with [NUMBER] years of experience in [DOMAIN].

Your communication style: [FORMAL/CASUAL/TECHNICAL]
Your values: [e.g., clarity, precision, user-friendliness]
Your constraints: [What to avoid]
```

### 5. Retrieval-Augmented Generation (RAG)

**When to use:** Tasks requiring external knowledge

**How:**
1. Retrieve relevant documents
2. Include as context in prompt
3. Ask model to use only provided information
4. Cite sources in output

---

## Common Prompt Patterns

### Code Generation
```
Role: Senior developer in [LANGUAGE]
Task: Write [TYPE] code for [PURPOSE]
Context: [Requirements, libraries, constraints]
Format: Code with comments and explanation
Examples: [Similar code snippets]
```

### Text Summarization
```
Role: Professional summarizer
Task: Summarize the following text
Context: [Purpose, audience, length constraints]
Format: [Bullet points / Paragraph / Executive summary]
Tone: [Neutral / Engaging / Technical]
```

### Content Analysis
```
Role: [Analyst type - e.g., UX researcher, data scientist]
Task: Analyze [CONTENT TYPE] for [GOAL]
Criteria: [Specific metrics or aspects to evaluate]
Format: [Structured output with categories]
Constraints: [Biases to avoid, perspectives to consider]
```

### Question Answering
```
Role: Expert in [DOMAIN]
Task: Answer the question based on [CONTEXT TYPE]
Context: [Reference material, documents]
Constraints:
- Use only provided information
- Cite sources
- Mark uncertainty
Format: [Answer + Confidence + Sources]
```

### Creative Writing
```
Role: [Persona - writer type, style]
Task: Write [TYPE] content about [TOPIC]
Tone: [Style - e.g., witty, serious, educational]
Length: [Word or character count]
Constraints: [Themes to include, avoid, etc.]
Examples: [Similar content examples]
```

---

## Prompt Optimization Workflow

### Step 1: Draft
- Start with a simple, clear prompt
- Use the framework: Role, Task, Context, Constraints, Format, Examples
- Don't overcomplicate initially

### Step 2: Test
- Run with multiple diverse examples
- Check against success criteria
- Identify patterns in failures

### Step 3: Refine
- Add missing context
- Clarify ambiguous instructions
- Adjust constraints
- Improve examples

### Step 4: Iterate
- Repeat steps 2-3 until satisfied
- Document what works
- Save successful prompts for reuse

---

## Troubleshooting Common Issues

### "The model is not following my instructions"

**Solutions:**
- Be more explicit about format
- Use XML tags or delimiters
- Add more examples
- Check for contradictory instructions
- Try different model

### "The output is too generic"

**Solutions:**
- Add more specific constraints
- Provide detailed examples
- Use few-shot prompting
- Adjust the role/persona
- Specify tone and style

### "The model is hallucinating"

**Solutions:**
- Add "Use only provided information" constraint
- Use RAG with cited sources
- Ask for confidence levels
- Break task into smaller steps
- Fact-check outputs

### "The output format is wrong"

**Solutions:**
- Be very specific about format
- Provide multiple examples
- Use XML tags or templates
- Ask model to follow exact structure
- Validate and retry if needed

---

## Use Cases

**When to use this skill:**

1. **User asks for help with AI interaction**
   - "Help me write a prompt for..."
   - "How should I ask ChatGPT to..."

2. **You need to generate a prompt for the user**
   - User describes a task
   - You translate to effective prompt

3. **User's prompt isn't working well**
   - Review and improve existing prompts
   - Debug prompt issues

4. **Training or documentation**
   - Teach best practices
   - Create prompt libraries

**How to use:**

1. **Read the skill** - Load `SKILL.md` to understand the framework
2. **Analyze the requirement** - What does the user need?
3. **Select the pattern** - Which prompt template fits?
4. **Apply the framework** - Role, Task, Context, Constraints, Format, Examples
5. **Generate the prompt** - Create a well-structured prompt
6. **Explain the reasoning** - Tell the user why you structured it this way

---

## Resource Index

This skill consolidates knowledge from:

| Resource | Type | Key Focus |
|----------|------|-----------|
| Anthropic Prompting Guide | Official | Structured prompting, XML tags, safety |
| OpenAI Prompting Guide | Official | Message roles, API patterns |
| GitHub Prompt Engineering Guide | Open Source | Comprehensive techniques, examples |
| OpenAI Cookbook | Code Examples | Practical implementations |
| Hugging Face Guide | Open Source | Few-shot, CoT, fine-tuning |
| Learn Prompting | Course | Systematic learning, red-teaming |
| DeepLearningAI Course | Course | Andrew Ng's best practices |
| Stanford Lecture | Academic | Theoretical depth, research |
| FlowGPT | Templates | Ready-to-use prompts |
| PromptBase | Marketplace | Industry examples, monetization |

---

## Credits

Consolidated and structured from 10 world-class Prompt Engineering resources by the AI agent community.

**Original sources:**
- Anthropic: https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview
- OpenAI: https://developers.openai.com/api/docs/guides/prompt-engineering
- Dair.ai: https://github.com/dair-ai/Prompt-Engineering-Guide
- DeepLearning.AI: https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers
- And more...

*We analyzed 10+ resources and built one unified skill.*
