# Privacy

Query Fanout Viewer is designed as a client-side bookmarklet.

## What it does

- reads conversation payloads from supported providers
- extracts provider-side search queries
- extracts cited domains and related URLs
- renders the results locally in a new browser window

## What it does not do

- it does not ship with a backend
- it does not upload your chat data to a repository-owned server
- it does not require an API key
- it does not persist conversation data outside your browser session by design

## Important caveats

- it uses same-origin provider endpoints
- provider payload structures may change over time
- the generated viewer currently loads Google Fonts
- private browsing may affect Claude live mode

## Recommendation

Do not use any browser-side inspection tool on conversations you are not comfortable inspecting in your current session context.
