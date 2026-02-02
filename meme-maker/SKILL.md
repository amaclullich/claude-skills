# Meme Maker Skill

Generate medical education memes about delirium using rhetorical pattern matching.

## Trigger
Use this skill when the user wants to:
- Generate memes about delirium or healthcare topics
- Find meme templates for a rhetorical pattern
- Validate meme content for clinical accuracy
- Export memes for Canva or social media

## Quick Commands
- `/quick-meme [fact]` - Generate single meme from a fact
- `/batch-memes [count]` - Generate multiple memes with variety
- `/find-templates [pattern]` - Find templates for pattern 1-30
- `/validate-meme [text]` - Check clinical accuracy
- `/export-canva` - Format for Canva bulk create

## Core Concept
**The Rhetorical Pattern dictates the Template. The Template never dictates the message.**

## The 30 Patterns (Quick Reference)

| # | Pattern | Best For |
|---|---------|----------|
| 1 | Institutional Cynicism | System failures everyone knows |
| 2 | Binary Good vs Easy | Right vs convenient tension |
| 3 | Hidden Complexity | Revealing what's beneath |
| 4 | Confrontation | Direct challenge to wrong thinking |
| 5 | Cognitive Progression | Ignorance to understanding |
| 6 | Intervention/Prevention | Small actions, big impact |
| 7 | Transformation/Duality | Before/after states |
| 8 | Confusion/Absurdity | System contradictions |
| 9 | Dual Emotional State | Conflicting feelings |
| 10 | Single Reaction | Pure emotional response |
| 11 | Escalation | Building intensity |
| 12 | Analogical Equivalence | Two things = same |
| 13 | Expectation-Outcome Gap | Expected vs reality |
| 14 | Double-Bind Dilemma | Bad choice vs bad choice |
| 15 | Stereotype Bundle | Collection of traits |
| 16 | Schematic Classification | Grids/rankings |
| 17 | Status-Hierarchy | Inferior vs superior |
| 18 | Ironic Detachment | Calm acceptance of disaster |
| 19 | Predictable Consequence | Feigned surprise |
| 20 | Missing-Step Logic | Plans missing crucial steps |
| 21 | Unwelcome Truth | Facts people reject |
| 22 | Refusal of False Choice | Rejecting binaries |
| 23 | Turnabout Reversal | Situation inverts |
| 24 | Participatory Prompt | Elicits audience response |
| 25 | Call-and-Response | Layered reaction |
| 26 | Phatic Brainrot | In-group recognition |
| 27 | No-One-Asked Frame | Unprompted information |
| 28 | Temporal Contrast | Two time points |
| 29 | Self-Deprecating | Admitting fault with humor |
| 30 | Affirmation/Praise | Positive recognition |

## 5 Voice Profiles

| Voice | Use When | Tone |
|-------|----------|------|
| **Weary Realism** | Audience knows problem | Tired, dark humor |
| **Passionate Advocacy** | Calling for action | Urgent, righteous |
| **Gentle Education** | Teaching | Patient, supportive |
| **Hopeful Encouragement** | Celebrating progress | Warm, forward-looking |
| **Solidarity & Community** | Validating experience | Empathetic |

## Output Format

```markdown
## Meme: [TEMPLATE NAME]
**Pattern:** [#] - [Name]
**Voice:** [Voice Profile]
**Template:** [filename]

| Zone | Text |
|------|------|
| top | [text] |
| bottom | [text] |

**Caption:** [social media caption]
```

## Constraints (ALWAYS APPLY)
1. Never blame individual staff - blame systems
2. Maintain clinical accuracy - don't exaggerate
3. Preserve patient/family dignity - not punchlines
4. Leave room for hope - better is possible
5. Engagement serves behaviour change, not vice versa

## Key Data Files (Grand Meme Maker folder)
- `Unified_Content_Source_Database.json` - 124 facts/pain points
- `Unified_Template_Inventory.csv` - 386 templates
- `Template_Text_Zone_Specs.json` - 51 text zone definitions
- `Rhetorical_Patterns_to_Meme_Templates_COMPLETE.csv` - 421 pattern mappings
- `meme_generator_prompt.md` - Full workflow guide

## Key Delirium Facts
- Delirium ≠ Dementia (acute vs chronic)
- 8x increased dementia risk after delirium
- 35% dementia risk increase per day of delirium
- 50% of elderly hospital patients develop delirium
- 76% of delirium cases missed by clinicians
- Family input essential but systematically excluded
- 4AT: 2-minute validated screening tool
