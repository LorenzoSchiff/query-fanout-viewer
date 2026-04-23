# Installation

## Chrome or Chromium-based browsers

1. Create a new bookmark
2. Name it `Query Fanout Viewer`
3. Open `src/bookmarklet.js`
4. Copy the entire single-line bookmarklet string
5. Paste it into the bookmark URL field
6. Save

## Firefox

1. Create a new bookmark
2. Open its properties
3. Paste the full bookmarklet string into the location field
4. Save

## Usage

1. Open a supported conversation page
2. Click the bookmark
3. A new window opens with the analysis console

## Claude notes

Claude live mode may fail depending on session state or private browsing restrictions.
When live mode fails, use the JSON import fallback.

## Troubleshooting

### Nothing happens
- allow pop-ups for the provider domain

### ChatGPT fails
- verify you are logged in
- verify the URL contains a conversation id
- reload the conversation page

### Claude fails
- verify you are logged in
- try normal browsing mode
- use the JSON import fallback
