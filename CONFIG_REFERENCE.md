# Blog Configuration Reference

## Main Configuration (_config.yml)

Key settings you might want to customize:

```yaml
# Site Information
title: Ewithome's Blog           # Blog title
subtitle: Share technology...   # Blog subtitle  
description: A personal blog    # Site description
author: Ewithome               # Author name
language: zh-CN                # Language code
timezone: Asia/Shanghai        # Timezone

# Site URL
url: https://Ewithome.github.io # Full URL

# Theme
theme: landscape               # Current theme

# Deploy Configuration
deploy:
  type: git
  repo: <your-repo-url>
  branch: main
```

## Directory Structure

```
├── .github/
│   └── workflows/
│       └── deploy.yml              # GitHub Actions CI/CD
├── scaffolds/
│   ├── draft.md                    # Draft post template
│   ├── page.md                     # Page template
│   └── post.md                     # Post template
├── source/
│   ├── _posts/                     # Blog posts (markdown files)
│   ├── _drafts/                    # Draft posts
│   ├── archives/index.md           # Archives page
│   ├── categories/index.md         # Categories page
│   └── tags/index.md               # Tags page
├── themes/
│   └── landscape/                  # Blog theme
├── _config.yml                     # Main site config
├── _config.landscape.yml           # Theme config
├── package.json                    # Node dependencies
└── README.md                       # Project README
```

## Post Front Matter

Example post structure:

```markdown
---
title: My First Post
date: 2026-06-01 12:00:00
updated: 2026-06-01 12:00:00
categories:
  - Tech
  - Life
tags:
  - Hexo
  - Blog
---

Your post content here...
```

### Common Front Matter Fields

| Field | Description |
|-------|-------------|
| `title` | Post title |
| `date` | Created date |
| `updated` | Last updated date |
| `categories` | Post categories (list) |
| `tags` | Post tags (list) |
| `author` | Post author (overrides default) |
| `comments` | Enable/disable comments |
| `permalink` | Custom URL slug |

## Page Front Matter

Example page structure:

```markdown
---
title: About Me
date: 2026-06-01 12:00:00
type: page
layout: page
---

Your page content here...
```

## Theme Customization

### Theme Config (_config.landscape.yml)

```yaml
# Menu
menu:
  Home: /
  Archives: /archives
  Categories: /categories
  Tags: /tags

# Header  
header:
  subtitle: Optional subtitle

# Sidebar
sidebar: right

# Widget order
widgets:
  - recent_posts
  - categories
  - archives
  - tag
```

### Custom CSS

Add custom styles to `themes/landscape/source/css/style.css`

### Custom HTML

Modify theme layout files in `themes/landscape/layout/`

## Common Customizations

### Add Navigation Links

Edit `_config.landscape.yml`:
```yaml
menu:
  Home: /
  About: /about
  Contact: /contact
  Archives: /archives
```

### Change Sidebar Position

Edit `_config.landscape.yml`:
```yaml
sidebar: left  # or right
```

### Add Google Analytics

In `_config.yml`, look for analytics section and add your tracking ID.

### Enable Comments

Popular options:
- Disqus
- Gitalk
- Utterances
- Valine

## Deployment Configuration

The GitHub Actions workflow automatically:
1. Installs dependencies
2. Builds the site
3. Deploys to `main` branch
4. GitHub Pages serves the content

To manually deploy:
```bash
hexo deploy
```

## Important Files

- `package.json` - NPM dependencies
- `_config.yml` - Site configuration
- `_config.landscape.yml` - Theme configuration  
- `.github/workflows/deploy.yml` - CI/CD pipeline
- `.gitignore` - Files to exclude from git

## Tips

1. **Always use `hexo clean` before generate** - Clears old files
2. **Test locally** - Run `hexo server` before deploying
3. **Commit regularly** - Push to hexo branch frequently
4. **Use meaningful git messages** - Helps track changes

---

For more details, see [SETUP_GUIDE.md](SETUP_GUIDE.md)
