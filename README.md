# Relative URL Finder Bookmarklet

This bookmarklet scans a webpage and its loaded scripts to extract relative URLs, useful for bug bounty and security research.

## Usage
1. Copy the code from `bookmarklet.js`.
2. Create a new browser bookmark.
3. Paste the code into the bookmark’s URL field.
4. Visit any site and click the bookmark to open the panel.

   
## Features

fix: rewrite as single-line minified bookmarklet for Edge/Chrome compatibility

- Fixed bookmarklet not running due to multi-line formatting in browser URL field
- Replaced loose lookahead regex with a stricter quoted-string URL pattern
- Added isLikelyUrl() filter to cut false positives (assets, short noise strings)
- Scripts now fetched in parallel via Promise.allSettled() with cache:force-cache
- Panel now shows immediately after all fetches resolve instead of a fixed 3s timeout
- Results sorted alphabetically
- Click any URL row to copy it individually (flashes green on copy)
- Copy button gives inline feedback instead of alert()
- Live result count updates as you type in search
- Dark theme UI with hover states, rounded corners, drop shadow

## Disclaimer
For educational and bug bounty purposes only. Use responsibly.
