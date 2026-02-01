# Claude Code Skills

Custom Claude Code skills for academic research, presentations, citations, and literature reviews.

## Skills

### `/cite`
Format references in Vancouver or Harvard style from PMIDs, DOIs, or paper details. Generates verified citations with clickable PubMed URLs.

**Usage:**
- `/cite 24590568` - Format a single PMID
- `/cite 10.1093/ageing/afu021` - Format from DOI
- `/cite 24590568, 31479234, 28754812` - Multiple papers
- `/cite from my Zotero library on [topic]` - Search Zotero

### `/lit-review`
Literature review workflow: Search PubMed for papers, save to Zotero, generate summary tables.

**Workflow:**
1. Search PubMed with your terms
2. Select papers to save
3. Save to Zotero (optional: create collection)
4. Generate summary table

### `/frontend-slides`
Create stunning, animation-rich HTML presentations from scratch or by converting PowerPoint files.

**Modes:**
- Create new presentation from scratch
- Convert existing PPT/PPTX to web
- Enhance existing HTML presentation

### `/pptx`
PowerPoint creation, editing, and analysis. Work with .pptx files for creating, modifying, or analyzing presentations.

**Capabilities:**
- Create new presentations (with or without templates)
- Edit existing presentations
- Extract text and images
- Work with layouts and themes

## Installation

Symlink or copy the skills directory to your Claude Code configuration:

```bash
ln -s /path/to/claude-skills ~/.claude/skills
```

## Configuration

Some skills require API credentials. Create a `.env` file or configure in your CLAUDE.md:

- **Zotero**: Set your API key and user ID in the skill files
- **PubMed**: No API key required for basic usage

## Author

Professor Alasdair MacLullich  
University of Edinburgh  
[@delaborators](https://twitter.com/delaborators)
