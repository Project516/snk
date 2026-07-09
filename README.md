# 🐍 SNK — GitHub Contribution Snake

Automatically generates a snake animation that eats through your GitHub contribution graph!

This repo uses the [Platane/snk](https://github.com/Platane/snk) GitHub Action to produce an SVG animation of a snake devouring the contributions on your GitHub profile.

## How It Works

A scheduled GitHub Actions workflow (`snk.yml`) runs every 24 hours (and on every push to `master`) to:

1. Generate the snake animation SVG from the repository owner's contribution graph
2. Push the generated SVGs to the `output` branch

The resulting SVGs are available at:

- `dist/github-contribution-grid-snake.svg` — light theme
- `dist/github-contribution-grid-snake-dark.svg` — dark theme (uses `github-dark` palette)

## Using the SVG on Your Profile

To display the animation on your GitHub profile README, add:

```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Project516/snk/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Project516/snk/output/github-contribution-grid-snake.svg" />
  <img alt="github-snake-animation" src="https://raw.githubusercontent.com/Project516/snk/output/github-contribution-grid-snake.svg" />
</picture>
```

> **Tip:** Replace `Project516` with your own username/organization if you fork this repo.

## Setup

To set this up for your own GitHub profile:

1. Fork this repository (or create a new one using this as a template)
2. Make sure the `snk.yml` workflow is enabled under **Actions**
3. Update the `github_user_name` in the workflow if needed (it defaults to the repository owner)
4. The workflow will generate SVGs and push them to the `output` branch automatically

## Manual Trigger

You can also trigger the generation manually:

1. Go to the **Actions** tab
2. Select the **generate animation** workflow
3. Click **Run workflow**

## Credits

- Animation powered by [Platane/snk](https://github.com/Platane/snk)
- Page deployment by [crazy-max/ghaction-github-pages](https://github.com/crazy-max/ghaction-github-pages)
