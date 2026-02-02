# Batch Add Template Zones

Add text zone specifications to multiple templates at once.

## Usage
```
/batch-zones [template-list]
```

## Parameters
- `template-list`: Comma-separated template names, or "top-20", "2-panel", "3-panel", "4-panel"

## Instructions

Read these files:
1. `@ SOCIAL MEDIA HUB/Grand Meme Maker/Unified_Template_Inventory.csv` - All 386 templates
2. `@ SOCIAL MEDIA HUB/Grand Meme Maker/Template_Text_Zone_Specs.json` - Existing 51 specs
3. Template images from `@ SOCIAL MEDIA HUB/Main Meme Templates Folder/` or `SuperMeme Master Templates/`

For each template without specs:

### Step 1: Analyze Template Structure
Look at the template image and determine:
- Panel count and layout (horizontal, vertical, grid)
- Text zone locations (top, bottom, per-panel, labels)
- Character limits based on space available

### Step 2: Generate Zone Specification
Create JSON in this format:

```json
{
  "filename": "Template-Name_template_X-panel.png",
  "name": "Human Readable Name",
  "structure": "two_panel_vertical|three_panel|four_panel|single_reaction|etc",
  "panel_count": X,
  "text_zones": [
    {
      "zone": "zone_id",
      "position": "description of where",
      "max_chars": 50,
      "purpose": "What this zone expresses"
    }
  ],
  "patterns": [1, 2, 3],
  "usage_note": "Special instructions for this template"
}
```

### Step 3: Add to Template_Text_Zone_Specs.json
Append each new spec to the existing JSON file.

## Common Zone Structures

### 2-Panel (Drake style)
- `top`: Reject/dislike option (max 60 chars)
- `bottom`: Accept/prefer option (max 60 chars)

### 2-Panel (Woman Yelling at Cat)
- `woman`: Accusation/complaint (max 80 chars)
- `cat`: Response/reality (max 50 chars)

### 3-Panel (Panik-Kalm-Panik)
- `panel1`: Initial panic (max 40 chars)
- `panel2`: False calm (max 40 chars)
- `panel3`: Return to panic (max 40 chars)

### 4-Panel (Grus Plan)
- `panel1`: Step 1 of plan (max 40 chars)
- `panel2`: Step 2 of plan (max 40 chars)
- `panel3`: Unexpected twist (max 40 chars)
- `panel4`: Realization (repeat panel 3 text)

### 4-Panel (Expanding Brain)
- `level1`: Basic understanding (max 40 chars)
- `level2`: Intermediate (max 40 chars)
- `level3`: Advanced (max 40 chars)
- `level4`: Galaxy brain (max 40 chars)

### 1-Panel Reaction
- `caption`: Main text, usually top or bottom (max 80 chars)
- OR `top` + `bottom` for Impact font style

## Batch Shortcuts

**`/batch-zones top-20`** - Add specs for 20 most-used templates missing zones
**`/batch-zones 2-panel`** - All 2-panel templates without specs
**`/batch-zones 3-panel`** - All 3-panel templates without specs
**`/batch-zones 4-panel`** - All 4-panel templates without specs

## Output

After adding specs, report:
- Templates processed
- New total coverage (was 51/386)
- Any templates that couldn't be processed (explain why)

$ARGUMENTS
