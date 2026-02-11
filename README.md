# oittracker.com

Marketing and legal pages for [OIT Tracker](https://oittracker.com) — an iOS app that helps parents manage their child's oral immunotherapy treatment.

Hosted on **GitHub Pages** with Jekyll. Pushes to `main` auto-deploy to [oittracker.com](https://oittracker.com).

## Project Structure

```
oittracker.com/
├── index.html              # Homepage (self-contained HTML + inline CSS)
├── _layouts/
│   └── legal.html          # Custom layout for legal pages (matches homepage theme)
├── legal/
│   ├── privacy-policy.md   # Privacy Policy (markdown, uses legal layout)
│   └── terms-of-service.md # Terms of Service (markdown, uses legal layout)
├── assets/
│   └── images/             # App icon, screenshots
├── _config.yml             # Jekyll configuration
├── CNAME                   # Custom domain (oittracker.com)
├── Gemfile                 # Ruby dependencies for local development
└── .gitignore              # Excludes _site/ and Jekyll cache
```

## Local Development

### Prerequisites

- **Ruby** (3.0+) — install via Homebrew: `brew install ruby`
- **Bundler** — comes with Homebrew Ruby, or install with `gem install bundler`

If your shell defaults to the macOS system Ruby (2.6), use the Homebrew version explicitly:

```bash
/opt/homebrew/opt/ruby/bin/bundle install
/opt/homebrew/opt/ruby/bin/bundle exec jekyll serve
```

Or add Homebrew Ruby to your PATH:

```bash
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

### Setup and Serve

```bash
bundle install          # Install dependencies (one-time)
bundle exec jekyll serve  # Start local server at http://127.0.0.1:4000
```

### Pages

| URL | Source |
|-----|--------|
| `/` | `index.html` |
| `/legal/privacy-policy` | `legal/privacy-policy.md` |
| `/legal/terms-of-service` | `legal/terms-of-service.md` |

## Deployment

GitHub Pages automatically builds and deploys on every push to `main`. The custom domain is configured via the `CNAME` file and GitHub repository settings.

## Editing Legal Pages

Legal pages are written in **markdown** with a `layout: legal` front matter. The `legal.html` layout applies the homepage's dark navy/teal theme. To edit content, modify the markdown files directly — no HTML changes needed.
