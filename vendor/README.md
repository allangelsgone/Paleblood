# vendor

React 18.3.1 UMD production builds (MIT licensed, license banner kept), copied unmodified from the npm packages `react@18.3.1` and `react-dom@18.3.1` (`umd/*.production.min.js`).

| File | SHA-384 |
| --- | --- |
| `react.production.min.js` | `sha384-DGyLxAyjq0f9SPpVevD6IgztCFlnMF6oW/XQGmfe+IsZ8TqEiDrcHkMLKI6fiB/Z` |
| `react-dom.production.min.js` | `sha384-gTGxhz21lVGYNMcdJOyq01Edg0jhn/c22nsx0kyqP0TxaV5WVdsSH1fSDUf5YJj1` |

These are the same bytes unpkg.com serves, so they match the integrity hashes hard-coded in `support.js`.

## Why they are here

`support.js` loads React from unpkg.com on every cold start, and the page stays blank if that host is unreachable. `support.js` looks its CDN URLs up in `window.__resources` first, so `index.html` maps them to these files (see the `<script>` above `support.js` in `<head>`). That also stops the runtime from downloading `index.html` a second time.

If `support.js` is ever regenerated with a different React version, update the URLs (the keys of `window.__resources`) to match its `REACT_URL` / `REACT_DOM_URL`; keys that do not match are ignored and the runtime falls back to the CDN.
