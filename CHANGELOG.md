# Changelog

All notable changes to this project will be documented in this file.

## 1.1.0

- Updated `src/bookmarklet.js` with fan-out citation path analysis
- Added ChatGPT search batch reconstruction from `web.run` calls, search results, open/view refs and final citations
- Added real final cited URL extraction and canonical URL deduplication
- Added query-to-batch and batch-to-citation deep links for open-web queries
- Kept real cited URL chips inline for domain-scoped queries
- Added final cited URL list and copy action
- Added ChatGPT model slug detection from provider payload metadata
- Changed cited URL/domain links to open real recovered URLs instead of Google searches
- Kept Google SERP links only on the fan-out query action button

## 0.1.0

- Initial public release
- ChatGPT live parsing
- Claude live parsing with import fallback
- Domain-scoped vs open-web grouping
- Cited domain concentration view
- Terminal-style UI
