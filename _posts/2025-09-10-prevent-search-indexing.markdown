---
layout: post
title:  "Preventing Search Engine Indexing"
date:   2026-07-20 23:40:00 +0800
categories: jekyll update
---

### Preventing Search Engine Indexing

To ensure that hidden text leaves no searchable traces on the internet, this project implements a dual-layer protection mechanism at the SEO directive level:

### 1. Dynamic `noindex` directive:

The project exercises precise control via server response headers (HTTP headers). When a ciphertext parameter (`c`) is detected in the URL, the system automatically injects the `X-Robots-Tag: noindex, nofollow` header. Unlike traditional HTML tags, this method takes effect immediately during the crawling phase, mandating that search engines like Google exclude the specific link from their indices and thereby preventing private information from appearing in search results at the source.

### 2. Canonical tag implementation:

All generated ciphertext pages use a `<link rel="canonical" ...>` tag to point consistently to the root domain (without parameters). This strategy informs search engines that, regardless of the encrypted parameters present in the URL, these pages are merely "variants" of the homepage rather than independent content pages. This "double-safeguard" mechanism ensures that even if crawlers discover the link, they will ignore the page due to the directives and the consolidation of ranking authority, effectively rendering the private information "invisible" on the public web.