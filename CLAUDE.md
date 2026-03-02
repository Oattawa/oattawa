# CLAUDE.md — AI Assistant Guide for Oattawa/oattawa

## Repository Overview

This is the **GitHub profile special repository** for the GitHub user `Oattawa`. GitHub automatically renders the `README.md` from a repository named after the account owner directly on their public profile page at `https://github.com/Oattawa`.

This repository has a single, high-visibility purpose: **it is the owner's public-facing GitHub profile**.

---

## Repository Structure

```
oattawa/
└── README.md      # GitHub profile README — rendered on the profile page
└── CLAUDE.md      # This file — AI assistant guide
```

There are no source code files, build systems, package managers, or test suites. This is a **content-only** repository.

---

## Key File

### `README.md`
- Rendered publicly at `https://github.com/Oattawa`
- Supports full **GitHub Flavored Markdown (GFM)**
- Supports embedded HTML (GitHub renders a safe subset)
- Supports static images, badges, and GIFs hosted on a CDN or within the repo
- Does **not** support JavaScript or dynamic content — it is static markdown

---

## Development Conventions

### Branch Strategy
- `main` / `master` — stable, production branch (what appears on the profile)
- `claude/<description>-<id>` — branches used for AI-assisted changes (e.g., `claude/add-claude-documentation-xJt28`)
- Always develop changes on a feature branch and open a PR to merge into `main`

### Commit Style
- Use short, imperative commit messages (e.g., `Update profile README with bio`)
- Each commit should represent a single logical change

### Content Editing Workflow
1. Checkout or create the appropriate `claude/` branch
2. Edit `README.md` directly — no build step required
3. Commit with a descriptive message
4. Push to the branch: `git push -u origin <branch-name>`
5. Open a pull request targeting `main`

---

## README.md Authoring Guidelines

When helping write or update the profile `README.md`:

### Supported elements
- **Badges**: Use [shields.io](https://shields.io) or [img.shields.io](https://img.shields.io) for dynamic badges
- **GitHub stats cards**: e.g., `github-readme-stats` (hosted externally, embedded as `<img>` tags)
- **Markdown tables**, code blocks, headers, lists, blockquotes
- **Emoji** via `:emoji_name:` syntax (GitHub renders these)
- **HTML**: `<div>`, `<p>`, `<img>`, `<a>`, `<br>`, `<details>`, `<summary>`, `<table>`, `<br/>` are commonly used
- **Relative links** to assets stored in the same repo

### Not supported
- JavaScript / `<script>` tags (stripped by GitHub)
- CSS `<style>` with most properties (heavily sandboxed)
- iframes
- External resources that don't allow hotlinking

### Best practices
- Keep it concise and scannable — profile READMEs are skimmed
- Include a clear personal intro, current focus areas, and contact/links
- Avoid excessively large images or GIFs that slow page load
- Check preview locally or on a staging branch before merging to `main`

---

## Git Operations

```bash
# Switch to feature branch
git checkout -b claude/<description>-<id>

# Stage and commit changes
git add README.md CLAUDE.md
git commit -m "Your descriptive commit message"

# Push branch (first time)
git push -u origin claude/<description>-<id>

# Subsequent pushes
git push
```

> **Important**: Branch names used for AI-assisted work must follow the pattern `claude/<description>-<session-id>`. Pushing to a differently named branch may fail with HTTP 403.

---

## Notes for AI Assistants

- There is **no test suite** — validate changes by reviewing markdown syntax and rendered output
- There is **no linter or formatter** required, though consistent formatting is preferred
- Changes to `README.md` are immediately visible on the GitHub profile once merged to `main`
- Always commit and push on the designated `claude/` branch; never push directly to `main` without explicit permission
- If asked to add sections (skills, stats, social links), prefer clean, readable markdown over heavy HTML
