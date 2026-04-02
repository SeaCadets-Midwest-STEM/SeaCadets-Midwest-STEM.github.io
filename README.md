# Sea Cadets Midwest STEM

A static website for the Sea Cadets Midwest STEM initiative, built with [Hugo](https://gohugo.io/) and deployed via GitHub Pages.

## Quick Start

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.158.0 or later)
- [Dart Sass](https://sass-lang.com/dart-sass/) (v1.98.0 or later)
- [Git](https://git-scm.com/)

### Local Development

```bash
# Clone the repo
git clone https://github.com/SeaCadets-Midwest-STEM/SeaCadets-Midwest-STEM.git
cd SeaCadets-Midwest-STEM

# Start the development server (includes draft content)
hugo server -D
```

The site will be available at `http://localhost:1313/`.

### Building for Production

```bash
hugo build --minify
```

Output goes to the `public/` directory.

## Deployment

The site automatically builds and deploys via GitHub Actions when changes are pushed to the `main` branch. The workflow is defined in `.github/workflows/hugo.yaml`.

To deploy:
1. Commit your changes
2. Push to the `main` branch
3. GitHub Actions builds and deploys to GitHub Pages

## Project Structure

```
├── .github/workflows/     # GitHub Actions CI/CD
├── archetypes/            # Content templates for new pages
├── content/               # All site content (Markdown)
│   ├── about/             # About / Mission
│   ├── contact/           # Contact information
│   ├── events/            # Training events
│   ├── faq/               # Frequently asked questions
│   ├── gallery/           # Photo gallery
│   ├── news/              # News and announcements
│   ├── programs/          # STEM program descriptions
│   └── resources/         # Learning resources
├── themes/
│   └── seacadets-midwest/ # Custom Hugo theme
│       ├── assets/scss/   # Stylesheets (SCSS)
│       └── layouts/       # HTML templates
└── hugo.toml              # Site configuration
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for a guide on adding and editing content. The guide is written for non-technical contributors and covers everything from creating events to formatting with Markdown.

## License

See [LICENSE](LICENSE) for details.
