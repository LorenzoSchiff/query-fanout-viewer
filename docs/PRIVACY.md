# Privacy and data handling

Query Fanout Viewer v1.2.0-rc.14 is a client-side bookmarklet. It runs in the context of the provider page on which you deliberately invoke it and presents a separate report window. It does not operate a project backend or telemetry service.

## Data access

- ChatGPT live mode reads the existing session information and uses the active session token for authenticated same-origin conversation requests. It does not ask you to enter a token or an API key.
- Claude live mode uses same-origin authenticated requests for organization and conversation data and may inspect explicitly available evidence in the current page.
- Supported Claude JSON imports are processed locally. The import does not send a request to the Anthropic Messages API and does not merge visible evidence from an unrelated open conversation.
- Analysis is intended to be read-only with respect to the provider conversation. The viewer does not create prompts or initiate provider searches. It is intended to process search evidence, not private reasoning.

The providers still receive their normal authenticated requests and may process or log them under their own policies. Provider internals and browser policies can change.

## Network activity

There is no project-hosted service receiving conversation data. The legacy report and import/error interface can load Google Fonts stylesheets and fonts, so not every screen is strictly offline. Browser or provider requests may occur as part of normal operation. Opening an external source, Google SERP or author link is a deliberate navigation to a third party; a SERP action sends the selected query to Google.

The modern report uses HTTP(S) external links with referrer/opener protections. URL filtering and normalization reduce some risks but are not a guarantee that every sensitive URL or query parameter is removed. Review evidence before opening or sharing it. Do not run the bookmarklet on untrusted pages or install code from an unverified source.

## Reports and clipboard

Queries, result titles, source URLs, citation information, model labels and diagnostic metadata may reveal sensitive commercial or personal information. Clipboard actions and saved HTML/JSON reports transfer data to your local clipboard or filesystem. You control subsequent storage and sharing.

The HTML export removes live controls, script and linked-resource elements and applies a restrictive Content Security Policy. It is a static report, not an anonymization tool. JSON exports may also contain identifying or contextual data. Review both formats before distribution, including query strings, URL paths, titles, snippets or diagnostic fields as applicable.

Do not publish private prompts, authentication headers, cookies, tokens, conversation IDs, personal information or full provider payloads. Do not attach raw HAR captures to public issues. Share only the smallest sanitized reproduction necessary, and use the repository's [security reporting instructions](../SECURITY.md) for sensitive findings.

## Control and removal

Remove the bookmark to stop using it. Delete downloaded reports and clear relevant clipboard data when no longer needed. The project does not provide an account, server-side report storage or a remote deletion mechanism. Your provider account and browser data remain governed by their respective settings and policies.
