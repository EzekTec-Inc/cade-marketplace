---
name: ux-copy
description: Writes or reviews interface copy (buttons, error messages, empty states, confirmation dialogs, tooltips and onboarding text) and returns recommended wording, alternatives and the reasoning.
license: Apache-2.0. Complete terms in LICENSE.txt; modified for CADE AGNTS, changes listed in NOTICE.
metadata:
  version: "1.0.0"
  author: Anthropic, PBC (adapted for CADE AGNTS)
  category: design
  icon: comments
  source: https://github.com/anthropics/knowledge-work-plugins/tree/e91a134584eb798bac7fb0379358006a2b63b965/design/skills/ux-copy
---

# UX Copy

Write or review UX copy for any interface context.

## What I Need From You

- **Context**: What screen, flow, or feature?
- **User state**: What is the user trying to do? How are they feeling?
- **Tone**: Formal, friendly, playful, reassuring?
- **Constraints**: Character limits, platform guidelines?

## Principles

1. **Clear**: Say exactly what you mean. No jargon, no ambiguity.
2. **Concise**: Use the fewest words that convey the full meaning.
3. **Consistent**: Same terms for the same things everywhere.
4. **Useful**: Every word should help the user accomplish their goal.
5. **Human**: Write like a helpful person, not a robot.

## Copy Patterns

### CTAs
- Start with a verb: "Start free trial", "Save changes", "Download report"
- Be specific: "Create account" not "Submit"
- Match the outcome to the label

### Error Messages
Structure: What happened + Why + How to fix
- "Payment declined. Your card was declined by your bank. Try a different card or contact your bank."

### Empty States
Structure: What this is + Why it's empty + How to start
- "No projects yet. Create your first project to start collaborating with your team."

### Confirmation Dialogs
- Make the action clear: "Delete 3 files?" not "Are you sure?"
- Describe consequences: "This can't be undone"
- Label buttons with the action: "Delete files" / "Keep files" not "OK" / "Cancel"

### Tooltips
- Concise, helpful, never obvious

### Loading States
- Set expectations, reduce anxiety

### Onboarding
- Progressive disclosure, one concept at a time

## Voice and Tone

Adapt tone to context:
- **Success**: Celebratory but not over the top
- **Error**: Empathetic and helpful
- **Warning**: Clear and actionable
- **Neutral**: Informative and concise

## Output

```markdown
## UX Copy: [Context]

### Recommended Copy
**[Element]**: [Copy]

### Alternatives
| Option | Copy | Tone | Best For |
|--------|------|------|----------|
| A | [Copy] | [Tone] | [When to use] |
| B | [Copy] | [Tone] | [When to use] |
| C | [Copy] | [Tone] | [When to use] |

### Rationale
[Why this copy works — user context, clarity, action-orientation]

### Localization Notes
[Anything translators should know — idioms to avoid, character expansion, cultural context]
```

## If More Context Is Available

If the user has a brand voice guide, content style guide or glossary (a file in the workspace, or a knowledge base reachable through a connected tool):
- Follow its voice and terminology
- Reuse existing copy patterns instead of inventing new ones

If a screenshot or design file of the screen is available:
- Look at it (analyze_image for a screenshot) to understand the full flow
- Respect the character limits and layout the design implies

## Tips

1. **Be specific about context** — "Error message when payment fails" is better than "error message."
2. **Share your brand voice** — "We're professional but warm" helps me match your tone.
3. **Consider the user's emotional state** — Error messages need empathy. Success messages can celebrate.

---

_Adapted for CADE AGNTS from https://github.com/anthropics/knowledge-work-plugins/tree/e91a134584eb798bac7fb0379358006a2b63b965/design/skills/ux-copy (Apache-2). The changes are listed in NOTICE._
