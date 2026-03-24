# BIOHACKER SYSTEMS — Landing Page

**biohacker.systems** | Sovereign Health Infrastructure

## Overview

Single-file landing page for Biohacker Systems. Pure HTML/CSS/JS — no build tools, no dependencies, no frameworks. Self-contained and deployable anywhere.

## Files

```
index.html   — Complete landing page (self-contained)
README.md    — This file
```

## Deployment

### Cloudflare Pages (recommended)

1. Push this repo to GitHub
2. Go to Cloudflare Pages → Create a project → Connect to Git
3. Select repo, set build output to `/` (no build command needed)
4. Deploy — it's live

### Netlify Drop

1. Go to netlify.com/drop
2. Drag the folder containing `index.html`
3. Done — assign `biohacker.systems` custom domain

### Manual / VPS

```bash
# Copy to web root
cp index.html /var/www/html/index.html

# Or serve locally for testing
python3 -m http.server 8080
# Open http://localhost:8080
```

### GitHub Pages

1. Push to a repo
2. Settings → Pages → Source: main branch / root
3. Set custom domain to `biohacker.systems`

## Custom Domain (biohacker.systems)

### Cloudflare DNS
```
Type   Name    Content           Proxy
A      @       <server-ip>       ✓
CNAME  www     biohacker.systems ✓
```

### SSL
Cloudflare provides automatic SSL. If self-hosting, use Certbot:
```bash
certbot --nginx -d biohacker.systems -d www.biohacker.systems
```

## Android APK Link

The download button currently points to:
```
https://github.com/Wintermute8426/biohacker-flutter/releases/latest
```

Update this URL in `index.html` when you have a direct APK file link for a better user experience. Search for `releases/latest` and replace both instances.

## Customization

All styles are inline in `<style>` tags. Key CSS variables at the top of the style block:

```css
--cyan:    #00FFFF;   /* primary accent */
--amber:   #FF9800;   /* secondary accent */
--magenta: #FF00FF;   /* tertiary accent */
--green:   #39FF14;   /* status / terminal */
```

## Performance

- No external JS dependencies
- One Google Fonts request (JetBrains Mono + Inter)
- Rain canvas uses `requestAnimationFrame` — pauses when tab is hidden
- Intersection Observer for scroll animations — no scroll event listeners
- Total page weight: ~20KB HTML + ~15KB fonts (cached after first load)

## SEO

Meta tags included:
- `og:title`, `og:description`, `og:type`, `og:url`
- `twitter:card`, `twitter:title`
- `description`, `keywords`
- `canonical` URL (update if domain changes)

---

*Your health. Your data. Your sovereignty.*
