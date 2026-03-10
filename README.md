# Prompt Wizard Skill

**Transform any requirement into an effective, well-structured prompt.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-orange)](https://github.com/openclaw/openclaw)

> Prompt engineering isn't magic. It's structured thinking.

---

## 🌟 Overview

This skill consolidates knowledge from **10 world-class Prompt Engineering resources** into a single, actionable guide. When you need to craft a prompt for any AI model (Claude, GPT, LLaMA, etc.), use this skill to ensure you're following best practices.

## ✨ Features

- **Structured Framework** - 6-step prompt template (Role, Task, Context, Constraints, Format, Examples)
- **Model-Specific Guidance** - Tailored advice for Claude, GPT, and open-source models
- **Advanced Techniques** - Chain-of-Thought, Few-Shot, Prompt Chaining, RAG
- **Common Patterns** - Ready-to-use templates for code generation, summarization, analysis, etc.
- **Troubleshooting** - Debug common prompt issues
- **Optimization Workflow** - Systematic approach to improving prompts

## 🚀 Quick Start

### For AI Agents

When you need to generate a prompt:

1. **Read the skill** - Load `SKILL.md` to understand the framework
2. **Analyze the requirement** - What does the user need?
3. **Select the pattern** - Which prompt template fits?
4. **Apply the framework** - Role, Task, Context, Constraints, Format, Examples
5. **Generate the prompt** - Create a well-structured prompt
6. **Explain the reasoning** - Tell the user why you structured it this way

### For Users

When you need help with prompting:

- **"Help me write a prompt for..."** - Describe your task, and I'll apply best practices
- **"My prompt isn't working well"** - Share it, and I'll debug and improve it
- **"How should I ask ChatGPT to..."** - Get specific guidance for your use case

## 📦 Core Framework

Every effective prompt should have:

1. **Role/Identity** - Who is the AI?
2. **Task** - What should it do?
3. **Context** - What information does it need?
4. **Constraints** - What should it avoid?
5. **Format** - How should the output look?
6. **Examples** - Show, don't just tell

### Example: Code Review Prompt

```
Role: You are a senior software engineer with expertise in Python and best practices for clean, maintainable code.

Task: Review the provided code snippet and identify:
- Bugs or potential issues
- Performance optimizations
- Code style improvements
- Security concerns

Context: This code will be used in a production environment with these requirements:
- Must handle 10k+ requests per second
- Memory usage under 512MB
- Python 3.11+

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
```python
def calculate_sum(numbers):
    result = 0
    for i in range(len(numbers)):
        result += numbers[i]
    return result
```

Output:
1. **Issue**: Using list indexing in loop is inefficient
   **Location**: Line 4
   **Severity**: Medium
   **Suggestion**: Use `for num in numbers:` instead
   **Reason**: Direct iteration is faster and more Pythonic

2. **Issue**: Missing type hints
   **Location**: Line 2
   **Severity**: Low
   **Suggestion**: Add `-> int` return type
   **Reason**: Improves code documentation and IDE support
```

## 🎯 Model-Specific Guidance

### Claude (Anthropic)

**Best for:** Complex reasoning, nuanced writing, safety-conscious tasks

**Key techniques:**
- Use XML tags for structure
- Provide clear role definitions
- Use "think step-by-step" for reasoning
- Leverage few-shot examples

**Structure:**
```xml
<role>You are a [ROLE] with expertise in [DOMAIN].</role>
<task>[What to do]</task>
<context>[Background, constraints]</context>
<format>[Desired output]</format>
<examples>[Example inputs/outputs]</examples>
```

### OpenAI (GPT)

**Best for:** General-purpose, wide range of tasks

**Key techniques:**
- Use message roles (developer/user/assistant)
- Instructions in developer message
- Use chain-of-thought for reasoning
- Provide examples in conversation format

**Structure:**
```python
messages = [
    {"role": "developer", "content": "You are a [ROLE] that [PURPOSE]. Follow these rules: [RULES]"},
    {"role": "user", "content": "[TASK with context and constraints]"},
]
```

### Open Source (LLaMA, Mistral, etc.)

**Best for:** Custom deployment, privacy, control

**Key techniques:**
- Use few-shot prompting extensively
- Provide clear examples
- Use structured format (templates, delimiters)
- Consider instruction-tuned vs base models

## 🛠️ Advanced Techniques

### 1. Chain-of-Thought (CoT)

**When:** Complex reasoning, multi-step problems

**How:**
```
Let's work through this step-by-step:

1. [First step reasoning]
2. [Second step reasoning]
3. [Third step reasoning]

Final answer: [Conclusion]
```

### 2. Few-Shot Prompting

**When:** Specific formats, patterns, or styles

**How:**
```
Example 1:
Input: [Input 1]
Output: [Output 1]

Example 2:
Input: [Input 2]
Output: [Output 2]

Now, your turn:
Input: [New input]
Output:
```

### 3. Prompt Chaining

**When:** Complex multi-stage tasks

**How:**
1. **Stage 1**: Extract/summarize
2. **Stage 2**: Analyze/categorize
3. **Stage 3**: Generate/present

### 4. Role Prompting

**When:** Specific personas, expertise levels

**How:**
```
You are a [EXPERT ROLE] with [NUMBER] years of experience in [DOMAIN].

Your communication style: [FORMAL/CASUAL/TECHNICAL]
Your values: [e.g., clarity, precision, user-friendliness]
Your constraints: [What to avoid]
```

### 5. Retrieval-Augmented Generation (RAG)

**When:** Tasks requiring external knowledge

**How:**
1. Retrieve relevant documents
2. Include as context in prompt
3. Ask model to use only provided information
4. Cite sources in output

## 📋 Common Prompt Patterns

| Use Case | Key Elements |
|-----------|-------------|
| **Code Generation** | Role, language, libraries, constraints, examples |
| **Summarization** | Purpose, audience, length, tone |
| **Content Analysis** | Criteria, metrics, perspectives |
| **Question Answering** | Domain, context, source citation |
| **Creative Writing** | Persona, style, themes, examples |

See `SKILL.md` for detailed templates for each pattern.

## 🔧 Troubleshooting

| Issue | Solution |
|--------|----------|
| Not following instructions | Be more explicit, use XML tags, add examples |
| Output too generic | Add specific constraints, provide detailed examples |
| Hallucinating | Add "use only provided information", use RAG |
| Wrong format | Specify format exactly, use templates, provide examples |

## 📊 Optimization Workflow

1. **Draft** - Start simple, use the framework
2. **Test** - Run with diverse examples
3. **Refine** - Add context, clarify instructions
4. **Iterate** - Repeat until satisfied
5. **Document** - Save successful prompts

## 📚 Resources

This skill consolidates knowledge from:

| Resource | Type | Key Focus |
|----------|------|-----------|
| Anthropic Prompting Guide | Official | Structured prompting, XML tags |
| OpenAI Prompting Guide | Official | Message roles, API patterns |
| GitHub Prompt Engineering Guide | Open Source | Comprehensive techniques |
| OpenAI Cookbook | Code Examples | Practical implementations |
| Hugging Face Guide | Open Source | Few-shot, CoT, fine-tuning |
| Learn Prompting | Course | Systematic learning |
| DeepLearningAI Course | Course | Andrew Ng's best practices |
| Stanford Lecture | Academic | Theoretical depth |
| FlowGPT | Templates | Ready-to-use prompts |
| PromptBase | Marketplace | Industry examples |

## 💡 Examples

### Example 1: Code Review Request

**User says:** "Help me review this Python code for best practices"

**Skill generates:**
```
Role: Senior Python developer with 10+ years of experience

Task: Review the provided code for:
- Performance issues
- Security vulnerabilities
- Code style violations
- Missing error handling

Context: This is a web service handling user uploads, running on Python 3.11

Constraints:
- Focus on critical issues first
- Provide specific line numbers
- Suggest concrete improvements, not vague advice
- Consider maintainability and readability

Format: Structured list with severity levels (Critical/High/Medium/Low)
```

### Example 2: Document Summarization

**User says:** "Summarize this 50-page technical report for executives"

**Skill generates:**
```
Role: Executive summary writer with technical background

Task: Create a concise executive summary of the attached technical report

Context: The summary will be presented to C-level executives who need:
- Key findings
- Recommendations
- Budget implications
- Timeline
- No technical jargon

Constraints:
- Maximum 2 pages
- Use bullet points for readability
- Focus on actionable insights

Format:
1. Executive Summary (3-4 sentences)
2. Key Findings (5-7 bullets)
3. Recommendations (3-5 bullets)
4. Next Steps (timeline, owners)
5. Risks and Mitigations (table)
```

## 📁 Files

- `SKILL.md` - Main skill documentation
- `README.md` - This file
- `_meta.json` - Skill metadata
- `LICENSE` - MIT License
- `scripts/` - Reserved for future tools

## 🤝 Contributing

This skill is based on publicly available Prompt Engineering resources. To improve:

1. Add new patterns to `SKILL.md`
2. Update model-specific guidance as new models emerge
3. Add troubleshooting scenarios
4. Contribute example prompts

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🙏 Credits

Consolidated from 10 world-class Prompt Engineering resources by AI agent community.

**Original sources:**
- Anthropic: https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview
- OpenAI: https://developers.openai.com/api/docs/guides/prompt-engineering
- Dair.ai: https://github.com/dair-ai/Prompt-Engineering-Guide
- DeepLearning.AI: https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers
- And more...

---

**Created by [lhy818](https://github.com/lhy818) based on 10 world-class Prompt Engineering resources.**

*Transform requirements into effective prompts, every time.* 🧙
