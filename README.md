# Cloudflare Complete Dataset

> Cloudflare's blog, developer documentation, and learning center — scraped, cleaned, and structured as a free dataset.

---

## What's Inside

74 clean JSON files covering:

- **Blog** — tag pages across security, AI, DNS, DDoS, workers, zero trust, performance, privacy and more
- **Developer Docs** — Workers, Pages, R2, D1, AI Gateway, Vectorize, DNS, SSL, Cache, Analytics, Access, Tunnel, Stream, Images, Spectrum and more
- **Learning Center** — DDoS, DNS, SSL, CDN, firewalls, bots, HTTP/3, zero trust, networking

---

## How It Was Built

Scraped with **[PhantomCrawl](https://github.com/var-raphael/PhantomCrawl)** — a 4-layer web crawler with TLS fingerprinting and anti-bot evasion. Cleaned with **[PhantomClean](https://github.com/var-raphael/PhantomClean)** — a multi-layer data cleaning pipeline.

Zero blocks. All Layer 1. Their own bot protection didn't stop it.

---

## Schema

Each file follows this structure:

```json
{
  "url": "https://...",
  "title": "Page Title",
  "content": "Cleaned text content...",
  "word_count": 1200,
  "quality_score": 1.00,
  "language": "en",
  "cleaned_at": "2026-03-18T...",
  "links": [],
  "images": []
}
```

---

## Stats

| Metric | Value |
|---|---|
| Total files | 74 |
| Average quality score | 1.00 |
| Average word count | ~900 words |
| Scraped | March 18, 2026 |
| Format | JSON |

---

## Usage

```python
import json
import os

dataset = []
for root, dirs, files in os.walk('./organized'):
    for file in files:
        if file.endswith('.json'):
            with open(os.path.join(root, file)) as f:
                dataset.append(json.load(f))

print(f"{len(dataset)} documents loaded")
print(f"Example: {dataset[0]['title']}")
```

---

## Tools Used

- **PhantomCrawl** — [github.com/var-raphael/PhantomCrawl](https://github.com/var-raphael/PhantomCrawl)
- **PhantomClean** — [github.com/var-raphael/PhantomClean](https://github.com/var-raphael/PhantomClean)

---

Built by [Raphael Samuel](https://var-raphael.vercel.app) · Lagos, Nigeria

