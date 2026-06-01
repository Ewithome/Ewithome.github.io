# Hexo Blog Setup - Final Steps

## Current Status

✅ Hexo project has been initialized and configured
✅ All source files are ready
✅ GitHub Actions workflow is configured
✅ Blog builds successfully locally

## Next Steps to Complete Setup

### 1. Set Up Branches

The blog uses two branches:

**hexo branch** (source code):
```bash
# If you haven't created the hexo branch yet:
git checkout -b hexo
git push -u origin hexo
```

**main branch** (generated site for GitHub Pages):
```bash
# Create an empty main branch
git checkout --orphan main
git rm -rf .
echo "# Blog Published Content" > README.md
git add README.md
git commit -m "Initial main branch for GitHub Pages"
git push -u origin main
```

### 2. Configure GitHub Pages

1. Go to your repository settings: https://github.com/Ewithome/Ewithome.github.io/settings/pages
2. Under "Build and deployment":
   - Source: Deploy from a branch
   - Branch: Select `main` and `/root` folder
3. Save

### 3. First Deployment

Option A: Manual deployment (one-time)
```bash
git checkout hexo
npm run deploy
```

Option B: Automatic deployment (via GitHub Actions)
```bash
git checkout hexo
git push origin hexo
# GitHub Actions will automatically build and deploy to main
```

### 4. Verify

After deployment (may take 1-2 minutes):
- Visit https://Ewithome.github.io
- You should see your blog homepage

## Deployment Workflow

### Create a New Post

```bash
hexo new "Post Title"
# Edit source/_posts/post-title.md
```

### Local Preview

```bash
hexo server
# Visit http://localhost:4000
```

### Publish

**Manual method:**
```bash
hexo clean && hexo generate && hexo deploy
```

**Or push to trigger GitHub Actions:**
```bash
git add .
git commit -m "Add new post"
git push origin hexo
```

## Theme Customization

The default theme is `landscape`. To customize:

1. Edit theme files in `themes/landscape/`
2. Modify main config in `_config.yml`
3. Rebuild: `hexo clean && hexo generate`

## Common Commands

```bash
# Create new post
hexo new "Title"

# Create new page
hexo new page "page-name"

# Local server
hexo server

# Clean generated files
hexo clean

# Generate static files
hexo generate

# Deploy
hexo deploy

# All in one
hexo clean && hexo generate && hexo deploy
```

## Troubleshooting

### Blog not showing on GitHub Pages

1. Verify the `main` branch exists
2. Check GitHub Pages settings point to `main` branch
3. Check deployment status in Actions tab

### Changes not reflecting

1. Clear local cache: `hexo clean`
2. Rebuild: `hexo generate`
3. Re-deploy: `hexo deploy`

### GitHub Actions failing

1. Check Actions tab for error logs
2. Verify `GITHUB_TOKEN` permissions (usually automatic)
3. Check `.github/workflows/deploy.yml` syntax

## Additional Resources

- [Hexo Official Docs](https://hexo.io/docs/)
- [GitHub Pages Help](https://docs.github.com/en/pages)
- [Landscape Theme Docs](https://github.com/hexojs/hexo-theme-landscape)

---

Your blog is ready! Start writing and sharing! 🎉
