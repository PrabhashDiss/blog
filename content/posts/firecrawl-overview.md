+++
title = "Firecrawl: Powerful Website Scraping & Extraction API"
date = "2025-06-30T19:18:32+05:30"
author = "Prabhash Dissanayake"
authorTwitter = ""
cover = ""
coverCaption = ""
tags = ["api", "web scraping", "llm", "firecrawl"]
keywords = ["firecrawl", "web scraping", "api", "llm", "data extraction"]
description = "Overview of Firecrawl, an API by Mendable AI for scraping, crawling, and extracting data from websites in LLM-ready formats."
showFullContent = true
readingTime = true
hideComments = false
color = ""
+++

**Firecrawl** is an API service developed by Mendable AI that enables users to **scrape, crawl, and extract data from entire websites**, transforming them into formats suitable for large language models (LLMs) such as markdown or structured data.

## Core Features

- **Scrape:** Retrieve content from a single URL in LLM-ready formats (markdown, HTML, structured data, screenshots).
- **Crawl:** Crawl a URL and all its accessible subpages, returning clean data for each—no sitemap required.
- **Map:** Quickly enumerate and retrieve all URLs from a website.
- **Search:** Perform web searches and fetch content from the results, with support for output in various formats.
- **Extract:** Use AI to extract structured data from single pages, multiple pages, or entire domains, using prompts and/or JSON schemas.
- **Batching:** Scrape thousands of URLs asynchronously using a batch endpoint.
- **Actions:** Automate interactions such as clicking, scrolling, or waiting on dynamic web pages before extraction.

## Output Formats

- **Markdown**
- **HTML**
- **Structured JSON** (with or without a schema)
- **Links**
- **Screenshots**
- **Metadata**

## Advanced Capabilities

- Handles complex sites: proxies, anti-bot, dynamic content, authentication.
- Customizability: control crawl depth, exclude tags, interact with pages.
- Media Parsing: PDFs, DOCX, images.
- Reliability: robust data fetching.

## API & Integrations

- **API:** RESTful endpoints for scraping, crawling, mapping, searching, and extracting.
- **SDKs:** Python, Node.js, Go, Rust.
- **LLM Frameworks:** LangChain, Llama Index, Crew.ai, and more.
- **Low-code Tools:** Dify, Langflow, Flowise AI, Cargo, Pipedream, Zapier, Pabbly Connect.

## Example Usage

### Scraping a Single Page

```bash
curl -X POST https://api.firecrawl.dev/v1/scrape \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer YOUR_API_KEY' \
    -d '{
      "url": "https://docs.firecrawl.dev",
      "formats" : ["markdown", "html"]
    }'
```

### Crawling a Website

```bash
curl -X POST https://api.firecrawl.dev/v1/crawl \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer fc-YOUR_API_KEY' \
    -d '{
      "url": "https://docs.firecrawl.dev",
      "limit": 10,
      "scrapeOptions": {
        "formats": ["markdown", "html"]
      }
    }'
```

### Extracting Structured Data with a Schema

```bash
curl -X POST https://api.firecrawl.dev/v1/extract \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer YOUR_API_KEY' \
    -d '{
      "urls": ["https://firecrawl.dev/*"],
      "prompt": "Extract the company mission, whether it is open source, and whether it is in Y Combinator from the page.",
      "schema": {
        "type": "object",
        "properties": {
          "company_mission": {"type": "string"},
          "is_open_source": {"type": "boolean"},
          "is_in_yc": {"type": "boolean"}
        },
        "required": ["company_mission", "is_open_source", "is_in_yc"]
      }
    }'
```

## Deployment & Access

- **Hosted API:** Requires signup and an API key.
- **Self-hosting:** Local runs supported, but not production-ready.
- **Docs & Playground:** See [GitHub](https://github.com/mendableai/firecrawl) for details.

## Use Cases

- Building RAG pipelines.
- "Chat with your website" bots.
- Automated web data extraction for AI/ML.
- Integrating web content into LLM apps.

**Note:** Firecrawl is actively developed. For the latest, see the [official documentation](https://github.com/mendableai/firecrawl).
