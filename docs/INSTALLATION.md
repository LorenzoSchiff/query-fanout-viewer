# Installation and usage

## Requirements

A browser that supports JavaScript bookmarklets and pop-ups, and access to a supported conversation page. Live retrieval uses your current authenticated session. A normal desktop browser session is recommended; mobile layout support does not guarantee bookmarklet installation or execution on every mobile browser.

No extension, local server, package installation or API key is required to use the bookmarklet.

## Install or upgrade to v1.2.0-rc.14

1. Visit the [prerelease page](https://github.com/LorenzoSchiff/query-fanout-viewer/releases/tag/v1.2.0-rc.14).
2. Download `query-fanout-viewer-v1.2.0-rc.14.txt` under Assets.
3. Open the TXT in a plain-text editor. Select all and copy. The value begins with `javascript:`.
4. In your browser's bookmark manager, create a bookmark (or edit the existing one). Use `Query Fanout Viewer RC14` as its name if you want to retain an older version separately.
5. Paste the entire copied value into the URL/address field and save. Check that the `javascript:` prefix is still present. Do not paste it into the browser's main address bar or a search box.
6. Open a supported conversation, let generation finish, then click the bookmark.
7. Allow the report pop-up for the provider if blocked. Check the version displayed in the report header.

If the browser truncates or rejects a long bookmark URL, try another desktop browser or bookmark manager. Browser compatibility is not universal. Keep the original TXT for reinstalling.

## ChatGPT

Open a conversation on `chatgpt.com` with a conversation ID in the URL (`/c/...`). The bookmarklet retrieves available conversation records through same-origin requests using the active ChatGPT session. It may paginate available records or fall back to another supported conversation format. Inspect the diagnostics for incomplete retrieval or unassigned batches.

## Claude

Open a conversation on `claude.ai` and run the bookmarklet. When a supported structured payload is available, the viewer analyses explicit web search, web fetch and citation records. Otherwise, it can display available visible answer/source evidence. Explicitly labelled visible search activity may be shown separately when recoverable. This is not a replacement for structured retrieval.

### Import Claude JSON

In the Claude report or import screen, select **Import Claude JSON** if available. Use **Load JSON file** or paste supported JSON and select **Parse pasted JSON**. Use an original supported Claude conversation JSON or a documented Anthropic Messages API response containing the relevant tool records. The import operates locally, does not initiate an API call and does not supplement imported data with visible evidence from the current conversation.

The viewer's own JSON report is an analysis export, not a provider payload. Arbitrary HAR files, binary transports, Claude Code CLI logs and undocumented Research formats are not supported import formats.

### Rescan

Where available, **Rescan visible citations** rechecks visible evidence in the original conversation. Return to the same conversation before using it. It is not a new provider search and cannot guarantee recovery of additional sources or concealed data. For a new conversation or a newly generated answer, rerun the bookmarklet.

## Help tooltips

Hover over a question mark in the live dashboard to display its explanation near the pointer. The tooltip follows the pointer while it remains on the marker, flips above when needed and stays within the viewport. Tab to a question mark for keyboard help; Escape dismisses it. Saved HTML reports remain script-free and use native browser hover help, with CSS-based keyboard help where supported.

## Reports

Use **Save report (HTML)** for a static readable snapshot and **Save report (JSON)** for structured analysis. Clipboard actions copy available evidence or report data. Browser download and clipboard permissions may affect these operations. Treat all exports as potentially sensitive; see [Privacy](PRIVACY.md).

## Troubleshooting

| Symptom | Action |
| --- | --- |
| Nothing opens | Verify the saved `javascript:` prefix, bookmark length and pop-up permissions. |
| Session or provider error | Check the active login and conversation URL; rerun after the answer finishes. |
| Partial or unavailable metrics | Check diagnostics. Missing records are not proof of zero searches. |
| Claude lacks structured records | Inspect available visible evidence or import a supported original JSON if you already have one. No full Opus retrieval fix is claimed. |
| Private/incognito failure | Use a normal browsing session; private browsing was not revalidated in RC14. |
| Wrong version | Replace the saved bookmark URL with the correct release asset and check the report header. |
| Clipboard or download blocked | Use the browser's permitted copy/download method or try another supported browser. |

## Rollback

Keep a separate bookmark with the previous known-good release, or restore its original bookmarklet URL. See the repository's [releases](https://github.com/LorenzoSchiff/query-fanout-viewer/releases). Do not mix a source file and an encoded asset from different versions.
