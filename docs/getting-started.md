# Getting Started

Welcome to the getting started guide for this documentation site.

## Overview

This documentation is built with MkDocs and uses Mike for version management.

## Installation

To work with this documentation locally:

```bash
# Clone the repository
git clone https://github.com/yourusername/mkdocs-gh-pages.git
cd mkdocs-gh-pages

# Install dependencies
pip install -r requirements.txt

# Serve locally
mkdocs serve
```

## Building Documentation

### Local Development

```bash
# Start development server
mkdocs serve

# Build static site
mkdocs build
```

### Version Management with Mike

```bash
# Deploy a new version
mike deploy --push --update-aliases 1.0 latest

# List all versions
mike list

# Set default version
mike set-default --push latest
```

## Project Structure

```
mkdocs-gh-pages/
├── docs/
│   ├── index.md
│   ├── getting-started.md
│   └── api.md
├── mkdocs.yml
├── requirements.txt
└── .github/
    └── workflows/
        └── deploy.yml
```

## Features

### Code Highlighting

```python
def hello_world():
    print("Hello, World!")
    return True
```

### Admonitions

!!! note "Note"
    This is a note admonition.

!!! warning "Warning"
    This is a warning admonition.

!!! tip "Tip"
    This is a tip admonition.