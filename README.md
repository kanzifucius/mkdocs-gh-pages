# MkDocs with Mike Versioning

A documentation site built with MkDocs, Material theme, and Mike for version management.

## Features

- 📚 **Multi-version Documentation**: Support for multiple versions using Mike
- 🎨 **Material Theme**: Beautiful and responsive Material Design theme
- 🔍 **Full-text Search**: Built-in search functionality
- 🌙 **Dark/Light Mode**: Theme toggle support
- 🚀 **GitHub Actions**: Automated deployment to GitHub Pages
- 📱 **Mobile Responsive**: Works great on all devices

## Quick Start

### Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/mkdocs-gh-pages.git
   cd mkdocs-gh-pages
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Serve locally:**
   ```bash
   mkdocs serve
   ```

   The site will be available at `http://localhost:8000`

### Building for Production

```bash
# Build static site
mkdocs build

# The built site will be in the 'site' directory
```

## Version Management with Mike

This project uses [Mike](https://github.com/jimporter/mike) for managing multiple versions of documentation.

### Manual Version Deployment

```bash
# Deploy a new version (e.g., version 1.0)
mike deploy --push --update-aliases 1.0 latest

# Deploy a new version and mark as stable
mike deploy --push --update-aliases 2.0 stable

# List all deployed versions
mike list

# Set default version
mike set-default --push latest

# Delete a version
mike delete --push old-version
```

### Automatic Deployment

The repository includes GitHub Actions that automatically deploy documentation:

- **Main branch pushes**: Deployed as `latest` and `dev` versions
- **Tagged releases**: Deployed with the tag name (e.g., `v1.0.0` → `1.0.0`) and marked as `stable`

## GitHub Actions Setup

To enable automatic deployment:

1. **Enable GitHub Pages** in your repository settings
2. **Set source to GitHub Actions** in Pages settings
3. **Update repository URLs** in `mkdocs.yml`:
   ```yaml
   site_url: https://yourusername.github.io/repository-name/
   repo_name: yourusername/repository-name
   repo_url: https://github.com/yourusername/repository-name
   ```

## Project Structure

```
mkdocs-gh-pages/
├── docs/                    # Documentation source files
│   ├── index.md            # Homepage
│   ├── getting-started.md  # Getting started guide
│   └── api.md             # API reference
├── .github/
│   └── workflows/
│       └── deploy.yml     # GitHub Actions workflow
├── mkdocs.yml             # MkDocs configuration
├── requirements.txt       # Python dependencies
└── README.md             # This file
```

## Configuration

### MkDocs Configuration (`mkdocs.yml`)

The configuration includes:
- Material theme with dark/light mode
- Mike plugin for version management
- Useful markdown extensions
- Search functionality
- Navigation structure

### GitHub Actions (`deploy.yml`)

The workflow:
- Triggers on pushes to main and tagged releases
- Builds and tests documentation on PRs
- Deploys automatically with proper version management
- Uses caching for faster builds

## Customization

### Adding New Pages

1. Create a new Markdown file in the `docs/` directory
2. Add it to the navigation in `mkdocs.yml`:
   ```yaml
   nav:
     - Home: index.md
     - Your New Page: new-page.md
   ```

### Theming

The Material theme can be customized in `mkdocs.yml`. See the [Material theme documentation](https://squidfunk.github.io/mkdocs-material/) for all available options.

### Version Strategy

- `latest`: Always points to the main branch
- `dev`: Development version (main branch)
- `stable`: Latest stable release
- Version numbers: Specific releases (e.g., `1.0.0`, `2.1.0`)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test locally with `mkdocs serve`
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Resources

- [MkDocs Documentation](https://www.mkdocs.org/)
- [Material Theme](https://squidfunk.github.io/mkdocs-material/)
- [Mike Documentation](https://github.com/jimporter/mike)
- [GitHub Actions](https://docs.github.com/en/actions)