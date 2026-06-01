# Ewithome's Blog

This is my personal blog built with [Hexo](https://hexo.io/) and hosted on [GitHub Pages](https://pages.github.com/).

## Repository Structure

This repository uses two branches:

- **hexo**: Contains the Hexo source code and blog content
- **main**: Contains the generated static website (auto-deployed)

## Quick Start

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn

### Installation

```bash
# Clone the repository (hexo branch)
git clone --branch hexo https://github.com/Ewithome/Ewithome.github.io.git
cd Ewithome.github.io

# Install dependencies
npm install
```

### Local Development

```bash
# Start local server
hexo server

# The blog will be available at http://localhost:4000
```

### Create a New Post

```bash
hexo new "Your Post Title"

# Edit the file in source/_posts/
```

### Generate and Deploy

```bash
# Clean generated files
hexo clean

# Generate static files
hexo generate

# Deploy to GitHub Pages (will push to main branch)
hexo deploy
```

Alternatively, use the shorthand:

```bash
hexo clean && hexo generate && hexo deploy
```

## Configuration

The blog configuration is managed in `_config.yml`. Key settings:

- **title**: Blog title
- **author**: Blog author name
- **language**: zh-CN (Chinese Simplified)
- **timezone**: Asia/Shanghai
- **url**: https://Ewithome.github.io
- **theme**: landscape

## Directory Structure

```
.
├── scaffolds/          # Post/page templates
├── source/             # Blog content
│   ├── _posts/        # Blog posts
│   ├── _drafts/       # Draft posts
│   ├── about/         # About page
│   ├── archives/      # Archives page
│   ├── categories/    # Categories page
│   ├── tags/          # Tags page
├── themes/             # Hexo themes
├── _config.yml         # Main configuration
├── package.json        # Dependencies
└── README.md           # This file
```

## Deployment

This blog is automatically deployed to GitHub Pages via:

1. Push changes to the `hexo` branch
2. Run `hexo deploy` to build and push to `main` branch
3. GitHub Pages will serve the content from the `main` branch

## How to Contribute

If you find issues or have suggestions, feel free to open an issue or pull request!

## License

This blog content is free to use for personal purposes.

---

For more information, visit [Hexo Documentation](https://hexo.io/docs/)