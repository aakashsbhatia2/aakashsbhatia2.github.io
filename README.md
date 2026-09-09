# aakashsbhatia2.github.io

A simple Jekyll blog starter for GitHub Pages.

## Quick start (macOS)

Verified on macOS 26 (Tahoe), Apple Silicon.

### 1) Install Homebrew

Skip if `r` already works.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### 2) Install Ruby 3.3

macOS ships Ruby 2.6, which is far too old for this site's dependencies. Install
Ruby 3.3 — the same version GitHub Pages runs:

```bash
brew install ruby@3.3
```

Do **not** use plain `brew install ruby` (currently 4.x). The `github-pages` gem
cannot resolve its dependency tree on Ruby 4, and instead of failing cleanly
Bundler silently downgrades everything to decade-old versions, then dies trying
to compile a native extension.

### 3) Put Ruby 3.3 on your PATH

`ruby@3.3` is keg-only, so Homebrew does not link it for you:

```bash
echo 'export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
ruby -v   # => ruby 3.3.x
```

On Intel Macs, replace `/opt/homebrew` with `/usr/local`.

### 4) Install Bundler and dependencies

`Gemfile.lock` was written by Bundler 4.0.8, so install that version rather than
the one bundled with Ruby:

```bash
gem install bundler -v 4.0.8
bundle install
```

### 5) Run locally

```bash
bundle exec jekyll serve
```

Then open:

```text
http://127.0.0.1:4000
```

The site rebuilds automatically as you edit. Press `Ctrl + C` to stop.

### Troubleshooting

- **Bundler prints downgrades (`Using colorator 0.1 (was 1.1.0)`) and then a
  native build fails on `yajl-ruby` or `posix-spawn`.** You are on the wrong
  Ruby. Run `which ruby`; it must point inside `ruby@3.3`, not `/usr/bin/ruby`.
- **`GitHub Metadata: No GitHub API authentication could be found.`** Harmless
  locally — it only affects `site.github.*` fields.
- **Port 4000 already in use.** Use `bundle exec jekyll serve --port 4001`.

## Quick start (Linux)

### 1) Install prerequisites

You need Ruby, build tools, and Bundler.

Ubuntu/Debian:

```bash
sudo apt update
sudo apt install -y ruby-full build-essential zlib1g-dev
gem install bundler
```

### 2) Install project dependencies

From the repository root:

```bash
bundle install
```

### 3) Run locally

```bash
bundle exec jekyll serve
```

Then open:

```text
http://127.0.0.1:4000
```

### 4) Stop the server

Press `Ctrl + C` in the terminal.

## Deploy on GitHub Pages

1. Push this repo to GitHub.
2. In repo settings, open **Pages**.
3. Set source to **Deploy from a branch**.
4. Select branch `main` and folder `/ (root)`.
5. Save.

For user-site repos named `<username>.github.io`, this will publish at:

```text
https://<username>.github.io
```

## Project structure

```text
.
├── _config.yml
├── _posts
│   └── 2026-03-10-welcome.md
├── Gemfile
├── index.md
└── assets
	└── css
		└── style.scss
```

## Customize

- Update site details in `_config.yml`.
- Edit intro text on the blog page in `index.md`.
- Add new posts in `_posts/` with filenames like `YYYY-MM-DD-title.md`.
- Adjust styling in `assets/css/style.scss`.
