# aakashsbhatia2.github.io

A simple Jekyll blog starter for GitHub Pages.

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
