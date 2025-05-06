---
title: Markdown Symbols - The key to speaking "LLM-ese"
date: '2025-05-06'
tags:
  - AI
  - prompting
  - markdown
  - LLM
---
## When to Use Markdown in Prompts

Use it when you want to:

- Structure complex information clearly  
- Create reusable templates or step-by-step flows  
- Trigger “thinking mode” (e.g., writing in outline, code, or comparison format)

## Why This Works: Training Exposure

LLMs were trained on massive corpora that include:

- GitHub repos  
- StackOverflow  
- Docs like READMEs and API guides  
- Markdown-based websites like Notion, Reddit, blogs, etc.

So when you use **common Markdown formatting**, you’re speaking the model’s **native visual language**.

## High-Impact Markdown Symbols (Strongly Learned Patterns)

| Symbol                   | Markdown Use    | Why It Matters to LLMs                                                                               |
| ------------------------ | --------------- | ---------------------------------------------------------------------------------------------------- |
| `#`, `##`, `###`         | Headings        | Triggers structured thinking; segments instructions or sections clearly.                             |
| `*`, `-`, `+`            | Bullets         | Recognized as lists — helps the model organize thoughts and outputs.                                 |
| `1.`, `2.`               | Numbered lists  | Supports step-by-step reasoning or procedural thinking.                                              |
| `**bold**` or `__bold__` | Emphasis        | Suggests importance or labels — model often echoes this in output.                                   |
| `_italic_` or `*italic*` | Subtle emphasis | Often used to signal asides, tone, or nuance.                                                        |
| `> blockquote`           | Quoting         | Interpreted as citing another voice or referencing prior text.                                       |
| ```` ``` ````            | Code blocks     | Very strong cue: model switches to structured syntax, preserves formatting, uses technical language. |
| `---`                    | Horizontal rule | Seen as a topic or section break — triggers a shift in focus.                                        |

## Moderate-Impact Symbols

| Symbol               | Use                   | LLM Behavior                                                                                |
| -------------------- | --------------------- | ------------------------------------------------------------------------------------------- |
| `[]()`               | Links                 | Recognized in context (e.g., tutorials), but rarely “clicked” — treated as source metadata. |
| `![alt](image)`      | Image embeds          | Model recognizes this is an image placeholder — it might respond descriptively.             |
| `\` (escape)         | Escape character      | Rarely changes LLM behavior unless in code contexts.                                        |
| HTML inside markdown | Tables, anchors, divs | Sometimes parsed correctly, especially in documentation, but inconsistent in free text.     |

## Low-Impact / Cosmetic Markdown

| Symbol                       | Use                 | LLM Behavior                                                                |
| ---------------------------- | ------------------- | --------------------------------------------------------------------------- |
| `&nbsp;` or raw HTML escapes | Fine-tuning spacing | Typically ignored or stripped in LLM response.                              |
| Line breaks (`\n`)           | Formatting          | Helps readability, but model doesn’t always preserve layout unless told to. |