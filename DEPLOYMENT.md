# Deployment Guide

## Quick Start

### Local Development

**Standard Jekyll server** (no redirects):
```bash
npm run dev
```
Access at: http://localhost:4000

**Netlify dev server** (with redirects, recommended):
```bash
npm run dev:netlify
```
Access at: http://localhost:8888

The Netlify dev server will:
- Handle `_redirects` rules (e.g., / → /en/ based on language)
- Apply headers from `netlify.toml`
- Simulate the production Netlify environment

## Deployment

### First Time Setup

If you haven't linked the site to Netlify yet:
```bash
netlify init
```

This will:
1. Connect to your Netlify account
2. Link or create a new site
3. Save the site ID to `.netlify/state.json`

### Deploy Preview (Draft)
```bash
npm run deploy:preview
```

This creates a preview URL for testing before production.

### Deploy to Production
```bash
npm run deploy
```

## Netlify Configuration

### Build Settings (netlify.toml)
- **Build command**: `bundle exec jekyll build`
- **Publish directory**: `public`
- **Ruby version**: Set by `.ruby-version` (3.3.0)

### Redirects
Edit `src/_redirects` to manage URL redirects and rewrites.

Current redirects:
- `/` → `/en/` (302) for English browsers
- `/` → `/fr/` (302) default

### Headers
Configured in `netlify.toml`:
- Security headers (X-Frame-Options, etc.)
- Cache control for static assets (1 year)

## Troubleshooting

### Redirects not working locally?
Make sure you're using `npm run dev:netlify` instead of `npm run dev`.

### Build failing on Netlify?
Check that:
1. Ruby version is compatible (3.3.0)
2. All gems are in Gemfile.lock
3. Build command in netlify.toml matches local build
