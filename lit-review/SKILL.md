---
name: lit-review
description: "Literature review workflow: Search PubMed for papers, save to Zotero, generate summary tables. Use when user wants to find papers on a topic, build a reference collection, or create a literature summary."
---

# Literature Review Skill

## Overview

This skill automates the literature review workflow:
1. Search PubMed for relevant papers
2. Save selected papers to Zotero (with optional collection)
3. Generate a summary table of findings

## Zotero Configuration

**Note:** Configure your Zotero credentials in your CLAUDE.md file:
```
Zotero API Key: YOUR_API_KEY
Zotero User ID: YOUR_USER_ID
```

## Workflow

### Step 1: Search PubMed

Use the NCBI E-utilities API to search PubMed:

```bash
# Search for papers (returns PMIDs)
curl -s "https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esearch.fcgi?db=pubmed&term=SEARCH_TERMS&retmax=20&retmode=json&sort=date"

# Get paper details from PMIDs
curl -s "https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esummary.fcgi?db=pubmed&id=PMID1,PMID2,PMID3&retmode=json"
```

### Step 2: Present Results

Display results in a numbered table:
- Number, Title, Authors, Journal, Year, PMID
- Highlight papers most relevant to the search query
- Note any systematic reviews or meta-analyses

### Step 3: Save to Zotero

When user selects papers to save:

1. Fetch full metadata from PubMed (XML format for complete data):
```bash
curl -s "https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=pubmed&id=PMID&retmode=xml"
```

2. Extract and format for Zotero API:
```json
{
  "itemType": "journalArticle",
  "title": "Paper title",
  "creators": [{"creatorType": "author", "firstName": "First", "lastName": "Last"}],
  "abstractNote": "Abstract text",
  "publicationTitle": "Journal Name",
  "volume": "10",
  "issue": "2",
  "pages": "123-130",
  "date": "2025",
  "DOI": "10.1000/example",
  "ISSN": "1234-5678",
  "url": "https://pubmed.ncbi.nlm.nih.gov/PMID/",
  "extra": "PMID: 12345678"
}
```

3. POST to Zotero:
```bash
curl -X POST "https://api.zotero.org/users/USER_ID/items" \
  -H "Zotero-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '[{...item JSON...}]'
```

### Step 4: Add to Collection (Optional)

If user specifies a collection:

1. Check if collection exists:
```bash
curl -s -H "Zotero-API-Key: YOUR_API_KEY" \
  "https://api.zotero.org/users/USER_ID/collections"
```

2. Create collection if needed:
```bash
curl -X POST "https://api.zotero.org/users/USER_ID/collections" \
  -H "Zotero-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '[{"name": "Collection Name"}]'
```

3. Add items to collection by updating each item:
```bash
curl -X PATCH "https://api.zotero.org/users/USER_ID/items/ITEM_KEY" \
  -H "Zotero-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -H "If-Unmodified-Since-Version: VERSION" \
  -d '{"collections": ["COLLECTION_KEY"]}'
```

### Step 5: Generate Summary Table

Create a markdown table summarising the saved papers:

| Authors | Year | Title | Key Findings | PMID |
|---------|------|-------|--------------|------|
| First et al. | 2025 | Paper title | Main result/conclusion | 12345678 |

## Example Usage

User: "Find recent papers on delirium prevention in hip fracture"

Response:
1. Search PubMed with terms: `delirium prevention hip fracture`
2. Display top 15-20 results
3. Ask user which to save
4. Save selected to Zotero
5. Optionally create/use a collection
6. Generate summary table

## Search Tips

- Use MeSH terms for precision: `"Delirium"[Mesh]`
- Combine terms: `4AT AND validation`
- Filter by date: `AND ("2023"[Date - Publication] : "2025"[Date - Publication])`
- Filter by type: `AND systematic review[pt]`
