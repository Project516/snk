# 🐍 SNK — GitHub Contribution Snake Animation

Automatically generates a snake animation from your GitHub contribution graph.

The animation is rendered as SVG files and pushed to the `output` branch, making it easy to embed in your GitHub profile README or anywhere else.

## How It Works

This repository uses the [Platane/snk](https://github.com/Platane/snk) GitHub Action to generate a snake game animation from a user's contribution graph. The workflow runs automatically every 24 hours and on every push to the `master` branch.

### Output Files

| File | Description |
|------|-------------|
| `github-contribution-grid-snake.svg` | Light theme animation |
| `github-contribution-grid-snake-dark.svg` | Dark theme animation (GitHub Dark palette) |

Both files are published to the `output` branch.

## Usage

### Manual Trigger

Go to **Actions → generate animation → Run workflow** to regenerate the animation on demand.

### Embed in Your Profile

Add the following to your GitHub profile README to display the animation:

```markdown
![Snake animation](https://raw.githubusercontent.com/Project516/snk/output/github-contribution-grid-snake.svg)
```

For dark mode:

```markdown
![Snake animation](https://raw.githubusercontent.com/Project516/snk/output/github-contribution-grid-snake-dark.svg?palette=github-dark)
```

## Workflow Details

The [workflow](.github/workflows/snk.yml) performs two steps:

1. **Generate** — Uses `Platane/snk/svg-only@v3` to create SVG animations from the repository owner's contribution graph
2. **Publish** — Pushes the generated SVGs to the `output` branch using `crazy-max/ghaction-github-pages@v5.0.0`

Dependabot is configured to check for GitHub Actions updates weekly.

## Credits

- [Platane/snk](https://github.com/Platane/snk) — The snake animation generator
- [crazy-max/ghaction-github-pages](https://github.com/crazy-max/ghaction-github-pages) — GitHub Pages deployment action
