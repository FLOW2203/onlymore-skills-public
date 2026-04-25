---
name: claude-seo
description: "Comprehensive SEO skill covering technical SEO, E-E-A-T, schema markup, GEO/AEO optimization, and strategic planning. Use for any SEO audit, content optimization, keyword research, meta tag generation, structured data, sitemap analysis, or search visibility improvement."
visibility: public
requires_body_cleanup: true
---
# SEO Agent

## Technical SEO
- Crawlability audit (robots.txt, sitemap.xml, canonical tags)
- Core Web Vitals (LCP, FID, CLS) analysis and fixes
- Mobile-first indexing compliance check
- HTTPS, redirect chains, broken links detection
- Structured data / Schema.org markup generation
- Hreflang for multilingual

## On-Page SEO
- Title tags (55-60 chars), meta descriptions (150-160 chars)
- H1-H6 hierarchy audit (1 H1 par page max)
- Internal linking strategy (anchor text optimization)
- Image alt text, lazy loading, WebP conversion
- Content freshness signals (updated_at schema)
- URL structure (kebab-case, short, descriptive)

## E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness)
- Author bio and credentials section
- About page completeness audit
- External citations and backlink profile
- Review and testimonial integration (schema markup)
- Trust signals (certifications, press mentions)

## GEO/AEO (Generative Engine / Answer Engine Optimization)
- `llms.txt` file generation (tells AI what to use from site)
- Semantic cluster architecture (topic → subtopic → article)
- FAQ schema for featured snippets and voice search
- Conversational content structure (question → answer format)
- Structured data for ChatGPT/Perplexity crawling

## Content Strategy
- Keyword research with search intent mapping (informational/commercial/transactional)
- Topic cluster + pillar page model
- Content gap analysis vs competitors
- Competitor SERP analysis (titles, structures, featured snippets)
- Content calendar based on keyword opportunity

## Rules
- Always check robots.txt before suggesting changes
- Prioritize user experience over keyword density
- Never suggest keyword stuffing or cloaking
- Focus on semantic relevance over exact match
- Mobile score must be ≥90 (Google PageSpeed Insights)
