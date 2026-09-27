# oittracker.com

Marketing, support, and legal pages for [OIT Tracker](https://oittracker.com), an iOS app that helps parents manage their child's oral immunotherapy (OIT) treatment. Owned by Jones Technical Enterprises, LLC.

Built with **Jekyll**, hosted on **AWS Amplify**. The domain and DNS live in **Amazon Route 53** in the same AWS account.

> **Status (Sept 2026): moving from GitHub Pages to AWS Amplify.**
> Until the move is finished, GitHub Pages still builds `main` and serves oittracker.com. The step-by-step runbook is in `internal-docs/runbooks/amplify-move.html`, a local-only file. When the move is done, delete this note and the `CNAME` file.

## How deploys work

```
push to main ──▶ Amplify build (amplify.yml) ──▶ _site/ ──▶ oittracker.com
                  1. install Ruby 3.4 (Amazon Linux 2023)
                  2. bundle install  → vendor/gems (cached)
                  3. jekyll build
```

- **Trigger:** every push to `main`. Build logs are in the Amplify console under the app, then **Deployments**.
- **Build recipe:** `amplify.yml`. Its comments explain each line.
- **Domain:** `oittracker.com` is the main address, and `www.oittracker.com` redirects to it. Amplify manages the HTTPS certificate and the Route 53 records for both.
- **Repo access:** once the move is done, this repo is **private**. Amplify reads it through the AWS Amplify GitHub App, which has access to this repo only.
- **Cost:** roughly $1 a month for build minutes and data served. There's a billing alert at $5.

## Project structure

```
oittracker.com/
├── index.html                  # Homepage (self-contained HTML + inline CSS/JS)
├── support.md                  # /support — App Store Support URL (layout: legal)
├── legal/                      # SYNCED from the app repo — do not edit here (see below)
│   ├── privacy-policy.md
│   ├── terms-of-service.md
│   └── consumer-health-data-privacy-policy.md
├── _layouts/
│   └── legal.html              # Navy/teal layout matching the homepage
├── assets/images/              # App icon, screenshots
├── previews/                   # Design experiments — in git, never published
├── _config.yml                 # Jekyll config, including the `exclude` list
├── amplify.yml                 # AWS Amplify build recipe
├── Gemfile / Gemfile.lock      # Ruby dependencies (Jekyll 4.4, Minima)
└── CNAME                       # GitHub Pages only — delete after the Amplify move

Local-only (gitignored, never committed):
├── internal-docs/              # Legal memos, security program, runbooks
├── allergy-plans/              # Reference PDFs of allergy action plans
├── vendor/                     # Gems installed by bundle / the Amplify build
└── _site/                      # Build output
```

## Pages

| URL | Source |
|-----|--------|
| `/` | `index.html` |
| `/support` | `support.md` |
| `/legal/privacy-policy` | `legal/privacy-policy.md` |
| `/legal/terms-of-service` | `legal/terms-of-service.md` |
| `/legal/consumer-health-data-privacy-policy` | `legal/consumer-health-data-privacy-policy.md` |

Links drop the `.html` extension. Amplify serves `/support` from `support.html` automatically.

## Local development

### Prerequisites

Use **Ruby 3.4** so local builds match Amplify. Amazon Linux 2023 only offers Ruby 3.2 and 3.4. Homebrew's plain `ruby` formula is 4.x, so install the versioned one:

```bash
brew install ruby@3.4
echo 'export PATH="/opt/homebrew/opt/ruby@3.4/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
ruby -v   # ruby 3.4.x
```

`ruby@3.4` isn't on your PATH until you add it, which keeps it from clashing with other Rubies. If `bundle` or `jekyll` then says "command not found", run `gem env | grep "EXECUTABLE DIRECTORY"` and add that folder to your PATH the same way.

### Serve

```bash
bundle install              # first time, and after Gemfile changes
bundle exec jekyll serve    # http://127.0.0.1:4000
```

`Gemfile.lock` records Bundler 4.0.10. If you have an older Bundler, it downloads 4.0.10 on first run.

## Legal pages are synced, not edited here

The privacy policy, terms of service and consumer health data policy are maintained in **`acholonu/oit-tracker`** under `docs/legal/`. A GitHub Action in that repo copies them here and commits them as `github-actions[bot]` with the message `sync: update legal docs from oit-tracker`. **Edit them in the app repo.** Any edit made here is overwritten on the next sync.

The synced files currently use `layout: default`, which is the Minima theme's layout, not the custom navy/teal `legal` layout that `support.md` uses. To give them the homepage look, change their front matter to `layout: legal` in the app repo.

**Required link:** Washington's My Health My Data Act requires a prominent link to the consumer health data privacy policy on the homepage. It's currently in the homepage nav ("Health Data") and footer. Keep it in any redesign.

## What gets published

Everything Jekyll writes to `_site/` goes live. To keep a file off the site, add it to `exclude` in `_config.yml`. Setting `exclude` replaces Jekyll's defaults, so they're repeated in the list. It currently excludes `README.md`, `amplify.yml`, `previews/`, `internal-docs/`, `allergy-plans/`, `vendor/`, `Gemfile*`, and Jekyll's caches.

**Never commit internal documents** (legal memos, security docs, plans) to this repo, even while it's private. Put them in `internal-docs/`, which is gitignored.

## If a build fails

1. Amplify console, then the app, then the failed deployment: open the build log and find the first error.
2. Common causes and fixes are in the runbook's "If something breaks" section.
3. To roll back the site, redeploy the previous successful build from the Amplify console.
