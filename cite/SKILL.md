---
name: cite
description: "Format references in Vancouver or Harvard style from PMIDs, DOIs, or paper details. Generates verified citations with clickable PubMed URLs. Use when user needs formatted references or a reference list."
---

# Citation Formatting Skill

## Overview

This skill formats academic references in Vancouver or Harvard style with:
- Verified PubMed URLs (checked before inclusion)
- Proper author formatting
- Clickable links
- In-text citation format + reference list entry

## Supported Input Formats

1. **PMID**: `cite 24590568` or `cite PMID: 24590568`
2. **DOI**: `cite 10.1093/ageing/afu021`
3. **Multiple**: `cite 24590568, 31479234, 28754812`
4. **From Zotero**: `cite from my Zotero library on [topic]`

## Default Style

**Vancouver** unless user specifies Harvard.

## Output Format

### Vancouver Style

**In-text:** Superscript numbers in order of appearance: ¹ ² ³

**Reference list:**
```
1. Bellelli G, Morandi A, Davis DH, et al. Validation of the 4AT, a new instrument for rapid delirium screening: a study in 234 hospitalised older people. Age Ageing. 2014;43(4):496-502. https://pubmed.ncbi.nlm.nih.gov/24590568/
```

### Harvard Style

**In-text:** (Author Year) format: (Bellelli et al. 2014)

**Reference list:**
```
Bellelli, G., Morandi, A., Davis, D.H., et al. (2014) 'Validation of the 4AT, a new instrument for rapid delirium screening: a study in 234 hospitalised older people', Age and Ageing, 43(4), pp. 496-502. Available at: https://pubmed.ncbi.nlm.nih.gov/24590568/
```

## Workflow

### Step 1: Fetch Paper Metadata

From PMID:
```bash
curl -s "https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=pubmed&id=PMID&retmode=xml"
```

From DOI (via CrossRef):
```bash
curl -s "https://api.crossref.org/works/DOI"
```

### Step 2: Verify URL

Always verify the PubMed URL works before including:
```bash
curl -s -o /dev/null -w "%{http_code}" "https://pubmed.ncbi.nlm.nih.gov/PMID/"
```

Only include URL if response is 200.

### Step 3: Format Citation

Extract from XML/JSON:
- Authors (LastName FirstInitials format for Vancouver)
- Title
- Journal name (abbreviated for Vancouver, full for Harvard)
- Year, Volume, Issue, Pages
- DOI
- PMID

### Step 4: Generate Both Formats

Provide:
1. In-text citation format
2. Full reference list entry
3. Verified PubMed URL

## Author Formatting Rules

### Vancouver
- First 6 authors, then "et al."
- Format: `LastName Initials` (no comma, no periods)
- Example: `Bellelli G, Morandi A, Davis DH, et al.`

### Harvard
- First 3 authors, then "et al."
- Format: `LastName, Initials.`
- Example: `Bellelli, G., Morandi, A., Davis, D.H., et al.`

## URL Priority

1. **PubMed URL** (preferred): `https://pubmed.ncbi.nlm.nih.gov/PMID/`
2. **DOI URL** (if no PMID): `https://doi.org/DOI`
3. **PMC URL** (if open access): `https://www.ncbi.nlm.nih.gov/pmc/articles/PMCID/`

## Example Usage

**Input:** `/cite 24590568`

**Output:**

### Vancouver
**In-text:** ¹

**Reference:**
1. Bellelli G, Morandi A, Davis DH, Mazzola P, Turco R, Gentile S, et al. Validation of the 4AT, a new instrument for rapid delirium screening: a study in 234 hospitalised older people. Age Ageing. 2014;43(4):496-502. https://pubmed.ncbi.nlm.nih.gov/24590568/

### Harvard
**In-text:** (Bellelli et al. 2014)

**Reference:**
Bellelli, G., Morandi, A., Davis, D.H., et al. (2014) 'Validation of the 4AT, a new instrument for rapid delirium screening: a study in 234 hospitalised older people', Age and Ageing, 43(4), pp. 496-502. Available at: https://pubmed.ncbi.nlm.nih.gov/24590568/

---

## Batch Citations

For multiple papers, generate a numbered reference list:

**Input:** `/cite 24590568, 31479234, 28754812 vancouver`

**Output:**
1. Bellelli G, Morandi A, Davis DH, et al. Validation of the 4AT... https://pubmed.ncbi.nlm.nih.gov/24590568/
2. Shenkin SD, Fox C, Godfrey M, et al. Delirium detection in older acute medical inpatients... https://pubmed.ncbi.nlm.nih.gov/31479234/
3. MacLullich AMJ, Shenkin SD, et al. The 4 'A's test for detecting delirium... https://pubmed.ncbi.nlm.nih.gov/28754812/

## From Zotero Library

Search user's Zotero library and format citations.

**Note:** Configure your Zotero API key and user ID in your CLAUDE.md file:
```
Zotero API Key: YOUR_API_KEY
Zotero User ID: YOUR_USER_ID
```

## Quality Checks

Before finalising any reference:
- [ ] Verify PubMed URL returns 200
- [ ] Check author count and format
- [ ] Confirm year matches publication
- [ ] Ensure journal name is correct
- [ ] Validate volume/issue/pages format
