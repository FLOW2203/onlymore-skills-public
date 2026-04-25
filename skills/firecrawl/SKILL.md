---
name: firecrawl
description: "Web scraping and crawling using Firecrawl. Use for competitive intelligence, market research, prospect data collection, content extraction from websites, or any task requiring structured web data."
visibility: public
requires_body_cleanup: true
---
# Firecrawl Web Scraping

## Installation
```bash
npx firecrawl setup
# or: npm install -g firecrawl-cli
```

## Core Commands
```bash
# Scrape a single page → clean markdown
npx firecrawl scrape https://example.com

# Crawl a site (respects robots.txt)
npx firecrawl crawl https://example.com --limit 50

# Search the web
npx firecrawl search "carrier billing France TPE PME"

# Batch scrape from URL list
npx firecrawl batch urls.txt --output ./results/

# Extract structured data with schema
npx firecrawl extract https://example.com \
  --schema '{"name": "string", "price": "number"}'
```

# Analyser concurrents COLHYBRI
npx firecrawl scrape https://petitscommerces.fr
npx firecrawl scrape https://shine.fr/pricing
npx firecrawl crawl https://sumeria.fr --limit 20
```

### Prospect Research
```bash
# TPE/PME locales (Nîmes/Occitanie)
npx firecrawl search "boucherie Nîmes site:pagesjaunes.fr" --limit 100
```

### Investor Research
```bash
npx firecrawl scrape https://occitanie-angels.fr
npx firecrawl scrape https://winvesty.com/portfolio
```

### Content Repurposing
```bash
# Extraire article pour réécriture LinkedIn
npx firecrawl scrape https://blog-fintech.fr/article > article.md
```

## Output Formats
- Markdown (default) — best for content analysis
- JSON — best for structured data extraction
- HTML — best for layout analysis

## Rules
- Always respect robots.txt (Firecrawl handles this automatically)
- Rate limit: 1 req/second by default (courteous crawling)
- Results write to files — don't paste large content in context
- For JavaScript-heavy sites: use `--wait 2000` flag (2s delay)
- Never scrape personal/private data (RGPD compliance)
