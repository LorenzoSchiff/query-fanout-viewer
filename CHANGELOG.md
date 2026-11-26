# Changelog

All notable changes to this project will be documented in this file.

## [v1.2.0-rc.14] - 2026-11-25

Prerelease consolidating the v1.2 development cycle since v1.1.

### Added

- Responsive visual dashboard with overview metrics, query groups, answer sources, retrieval batches, hostname concentration and diagnostics.
- Claude structured web search and web fetch analysis, with explicit operation-ID associations and multi-URL citation groups where records are available.
- Local import of supported Claude conversation JSON and documented Anthropic Messages API response JSON.
- HTML and JSON report export, additional clipboard actions, coverage indicators and evidence provenance.
- Separate Claude fallback for explicitly labelled visible search activity when structured retrieval is unavailable (`publicSearchActivity`, `visible-labelled-search-activity`, `same-visible-section-only`).

### Changed

- Improved ChatGPT parsing of conversation formats, query metadata, compact and JSON web-search commands, result-only batches and open/view evidence.
- Distinguished explicit associations, sequence candidates and normalized-URL overlap rather than implying query-level causality.
- Improved handling of final answer links, native citation evidence and visible source panels.
- Separated record counts, distinct URLs, citation groups and opened/fetched documents.
- Refined domain-scoped query classification, including path restrictions and market-level `site:` operands.
- Displayed unavailable retrieval metrics as `N/A` rather than misleading zero counts.

### Fixed

- Replaced the fixed bottom-center help tooltip with a single pointer-following overlay in the live dashboard; bounded to the viewport and dismissible with Escape.
- Removed duplicate native hover help in the live dashboard. Static HTML exports retain native hover help and restrictive CSP without embedded scripts.

- Preserved multiple URLs in supported Claude citation groups.
- Avoided treating text-only Claude JSON as verified structured retrieval.
- Isolated imported Claude JSON from the current conversation's visible evidence.

### Known limitations

- Structured retrieval has not been validated for Claude Opus 5/5.5 or Claude Research; some Sonnet samples also yielded no structured records.
- The visible-search-activity fallback was tested with a synthetic fixture, not a live Opus session. It does not decode arbitrary binary transports or establish structured batch attribution.
- Retrieval and citation coverage remains dependent on available provider data. Private/incognito Claude usage was not revalidated. Gemini and Google AI Mode are not implemented.

### Validation

Prior validation included ChatGPT replay/regression checks, structured Claude Haiku 5.5 and Sonnet 5.5 replays, multi-URL citations, fetch records, local JSON import, export and responsive rendering. The RC12/RC13 Claude replay reports matched except for version and export timestamp. This is sample-based validation, not a guarantee of exhaustive model or browser compatibility.

RC14 additionally passed offline Chromium interaction and export tests on the two supplied ChatGPT GPT-6.2 Thinking and Claude Sonnet 5.5 report DOMs at desktop and narrow viewport sizes. Retrieval and parser logic was not changed or retested live. Screenshots were rendered from those RC13 reports with the RC14 UI changes.

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
