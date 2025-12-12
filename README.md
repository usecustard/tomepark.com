# TOMÉ PARK : Website

Jekyll static site for TOMÉ PARK, deployed on Netlify.

## Setup

### Prerequisites
- Ruby 3.3.0 (managed via rbenv)
- Bundler
- Node.js (for Netlify CLI)

### Installation

```bash
# Install Ruby dependencies
bundle install

# Install Node dependencies (for Netlify CLI)
npm install
```

## Development

### Standard Jekyll development server
```bash
npm run dev
# or
bundle exec jekyll serve
```

Site will be available at http://localhost:4000

### Netlify development server (with redirects)
```bash
npm run dev:netlify
# or
netlify dev
```

Site will be available at http://localhost:8888

This runs Jekyll in the background and proxies through Netlify CLI, which:
- Handles `_redirects` rules locally
- Simulates Netlify's routing behavior
- Tests headers and other Netlify features

## Build

```bash
npm run build
# or
bundle exec jekyll build
```

Output will be in the `public/` directory.

## Deployment

### Deploy to production
```bash
npm run deploy
# or
netlify deploy --prod
```

### Deploy preview
```bash
npm run deploy:preview
# or
netlify deploy
```

## Configuration

- `_config.yml` - Jekyll configuration
- `netlify.toml` - Netlify build and deployment settings
- `.ruby-version` - Ruby version for rbenv
- `src/_redirects` - Netlify redirect rules

## TODO

- og image is a bit blurry
- Get analytics-code
- get Better images from ton
- webpack for css prefixing, js, browserfy & whatever
- optimize for reader view
