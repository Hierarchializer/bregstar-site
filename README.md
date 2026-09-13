# bregstar.com

Static site for Bregstar, hosted on GitHub Pages. Edit the HTML, push to master, live in about a minute.

- `index.html` — landing page (source of truth for copy; the voiceai repo has the original draft in `gtm/`)
- `privacy.html`, `terms.html` — registered with carriers in the Twilio A2P 10DLC campaign; keep the SMS sections consistent with what the backend sends
- `CNAME` — custom domain for Pages

## After changing `style.css`

Bump the version in every page's stylesheet link so browsers don't reuse a cached copy (GitHub Pages
serves CSS with a 10-minute cache):

```bash
v=$(git rev-parse --short HEAD); sed -i '' -E "s#/style\.css(\?v=[^\"]*)?\"#/style.css?v=$v\"#" *.html
```
