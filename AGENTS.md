# AGENTS.md

## Cursor Cloud specific instructions

This is a **GitHub Profile README** repository — it renders as the owner's public GitHub profile page. There is no application, build system, package manager, test suite, or linting configuration.

### Repository structure

- `README.md` — The profile page content (Markdown + inline HTML with external SVG/image references)
- `github-metrics.svg` — Auto-generated GitHub metrics image (committed by CI)
- `.github/workflows/metrics.yml` — GitHub Actions workflow that regenerates `github-metrics.svg` daily using [lowlighter/metrics](https://github.com/lowlighter/metrics)
- `.github/workflows/snake.yml` — GitHub Actions workflow that regenerates contribution snake SVGs to the `output` branch using [Platane/snk](https://github.com/Platane/snk)

### Development workflow

- **No dependencies to install.** No `package.json`, `requirements.txt`, or any other dependency file exists.
- **No build/lint/test commands.** The project is purely static Markdown content.
- To develop: edit `README.md`, commit, and push. GitHub renders the profile automatically.
- The GitHub Actions workflows require repository secrets (`GITHUB_TOKEN`, `GH_TOKEN`) and only run on GitHub infrastructure — they cannot be run locally.

### Previewing changes locally

To preview the README locally, you can use Python's `grip` tool:
```bash
pip3 install grip
grip README.md
```
Or generate a simple HTML preview and open it in a browser.
