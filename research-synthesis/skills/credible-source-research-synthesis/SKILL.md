---
name: credible-source-research-synthesis
description: Use when the user wants articles on a topic collected from a trusted list of sources, logged in a research archive spreadsheet, and synthesized into a cited report.
---

# Credible-source research and synthesis

Collect what trusted sources say about a topic. Log every article in an archive spreadsheet, then write a synthesis report where every claim links to its source.

**Requires:** web search and web page fetching tools. The skill searches and reads public pages; it does not scrape sites or get around paywalls or logins.

## 1. Confirm the inputs

From the request, settle three things. Ask only if one is missing and can't reasonably be defaulted.

- **Topic and sub-themes.** Example: retail, covering demand forecasting; price, promo and assortment; trade investment and RGM; tech for merchandising; supply chain; AI.
- **Source list.** Use the user's list if they gave one. Otherwise default to:
  - Consultancies: McKinsey, BCG, Bain, Deloitte, Kearney, Oliver Wyman, L.E.K., Accenture, PwC
  - Research firms: Gartner, IDC
  - Trade press relevant to the topic. For retail: Retail Dive, Supply Chain Dive, Grocery Dive, Modern Retail, Retail TouchPoints, Retail Gazette, Chain Store Age, SupplyChain247
- **Time window.** Default to the last 12 months.

If an archive and a synthesis report already exist from an earlier run, reuse them. Add only new articles and update the synthesis rather than starting over.

## 2. Research

- Run separate searches per theme and per major source. Combined queries give shallow results.
- Use the current year in queries.
- Open (fetch) every primary piece the numbers come from. A search snippet is not a source.
- Prefer the original publication over coverage of it. When only coverage is available (e.g. paywalled analyst research), label it "via <outlet>".
- Flag vendor content, and any statistic that is a secondary citation you couldn't trace to its original.
- Aim for about 20–30 articles across all themes, with at least 3 per theme. Include at least one skeptical or counterpoint source.
- Record per article: theme, source, title, publication date, 2–4 sentences of key takeaways with the figures, source type, and URL.

## 3. Build the archive

Pick the output format in this order:
1. The user's stated format (Excel, Google Sheets, CSV).
2. A native spreadsheet artifact or document type, if your environment offers one.
3. Otherwise, an `.xlsx` file (or `archive.csv` if no spreadsheet library is available).

Layout:
- Sheet name: **Articles**.
- Columns, in order: Theme | Source | Title | Published | Key takeaways | Source type | URL.
- Published is text in ISO form (YYYY-MM-DD, or YYYY-MM / YYYY when that's all that's known) so it sorts correctly.
- Source type values: Consultancy (primary), Research firm (reported), Trade press, Data vendor, Vendor blog.
- Where the format supports it: Theme as a colored dropdown, a styled header row, wrapped Title and Key takeaways columns, and a frozen header.
- Read the result back to check it.

## 4. Write the synthesis report

Pick the format the same way: the user's stated format, then a native document type if available, otherwise a Markdown file (`synthesis.md`).

Sections:
1. **Bottom line.** A lead sentence, then 5–6 bullets across all themes.
2. **Where the sources agree.** A numbered list of consensus points, each with its sources.
3. **One section per theme.** A one-sentence point, then bullets with figures and inline [source](url) links.
   - When several firms offer competing frameworks, use a comparison table (firm | model | claimed impact | where to start).
4. **Where the sources disagree.** Tensions such as speed of adoption, incomparable value estimates, and hype versus reality.
5. **Implications.** A numbered sequence of actions.
6. **Open questions to track.**
7. **Method and sources.** Number of sources, collection date, where the archive is, how secondary and vendor sources were treated, and caveats.

Writing rules:
- Each section opens with its point.
- Sentences under 25 words; specific numbers, names and dates.
- Attribute a firm's self-reported results as its own claim, and note when a firm sells tools in the area it writes about.
- Each number appears once in the report.
- Don't quote more than a short phrase from any source; paraphrase. Never reproduce paragraphs of copyrighted articles.

## 5. Check the work

Before handing over:
- Recheck every figure and attribution in the report and the archive against what was fetched.
- Remove any claim the sources don't support, or any ordering they don't support (e.g. "followed by" when the second number is larger).
- Confirm the source count in Method matches the archive's rows.

## 6. Hand off

Keep the reply short:
- What the two outputs are, and where they are.
- The headline finding in 2–3 sentences.
- Gaps: paywalled sources, untraced figures, source types not yet covered.
- One offer: a recurring run (e.g. monthly) that adds only new articles to the archive and updates the synthesis, if your environment supports scheduled tasks.

For a recurring run, write a self-contained prompt: topic, themes, source list, the archive and report locations, and the instruction to add only articles newer than the latest Published date in the archive.
