# Credible-source research synthesis

A Claude skill that turns "what are credible sources saying about X?" into two outputs:

1. **A research archive**: a spreadsheet with one row per article (theme, source, title, date, key takeaways, source type, link).
2. **A synthesis report**: where sources agree and disagree, findings by theme, implications and open questions. Every claim links back to its source.

You choose the topic, the sub-themes and the sources you trust: consultancies, analyst firms, trade press, blogs. The skill finds articles with web search and reads the pages. It doesn't scrape sites, and it doesn't get around paywalls or logins.

## Example

> Run a research synthesis on retail. Themes: demand forecasting, price/promo/assortment, trade investment optimization, merchandising tech, supply chain, and AI. Sources: McKinsey, BCG, Bain, Deloitte, Gartner, Retail Dive, Modern Retail.

On a test run, this produced an archive of 24 articles and a cited report with a cross-firm comparison of agentic-merchandising frameworks.

## Install

**Claude apps (claude.ai, desktop, mobile)**
1. Download this repo and zip the `skills/credible-source-research-synthesis` folder.
2. In Claude, go to your skills settings and upload the zip.
3. Make sure web search is turned on.

**Claude Code**
Copy the skill folder into your skills directory:

```bash
git clone https://github.com/fknott-l/research-synthesis.git
mkdir -p ~/.claude/skills
cp -r research-synthesis/skills/credible-source-research-synthesis ~/.claude/skills/
```

Then ask Claude for a research synthesis, or type `/credible-source-research-synthesis`.

## Output formats

The skill uses whatever format you ask for. Otherwise:
- In environments with native spreadsheet and document types, it uses those.
- Elsewhere, it writes an `.xlsx` (or `.csv`) archive and a Markdown report.

## Recurring runs

Ask for a monthly or weekly run, if your environment supports scheduled tasks. Each run adds only new articles to the archive and updates the report.

## Limitations

- **Paywalls:** paywalled sources (e.g. Gartner, Bloomberg, WSJ) are covered only through public summaries or press coverage. The report labels these.
- **Quality depends on the source list:** results are only as good as the sources you choose. Consultancy research is often based on the firm's own surveys and client work, and the firms sell tools in the areas they write about.
- **Verify before relying on it:** check key figures against the linked originals before using them in decisions or publications.

## License

MIT. See [LICENSE](LICENSE).
