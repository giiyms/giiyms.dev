# giiyms.dev

Static site hosted on GitHub Pages. Primary purpose: serve the
`apple-app-site-association` Universal Link manifest for the
**Ampr** (TeslaTracker) iOS app's Tesla Fleet API OAuth flow.

## Layout

- `index.html` — landing page
- `tract/index.html` — Tract product / App Store support page
- `tract/privacy/index.html` — Tract privacy policy (`/tract/privacy/`)
- `tract/terms/index.html` — Tract terms of use (`/tract/terms/`)
- `.well-known/apple-app-site-association` — Universal Link config (must be served as JSON, no extension, no redirect)
- `oauth/tesla/index.html` — fallback if app isn't installed
- `CNAME` — GitHub Pages custom domain
- `.nojekyll` — disable Jekyll so `.well-known/` is served verbatim

## DNS

`giiyms.dev` apex → GitHub Pages IPs:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

## Verification

```sh
curl -i https://giiyms.dev/.well-known/apple-app-site-association
# expect: HTTP/2 200, content-type: application/json
```
