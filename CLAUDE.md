# Claude AI Assistant Context

## Project Overview

This is a Jekyll-based GitHub Pages website for Christian Arentsen's personal site. The project is designed to be fully managed by AI assistants with comprehensive context and documentation.

**Site URL**: https://carentsen.github.io/
**Repository**: Personal Jekyll site with automated deployment
**Theme**: Minima (Jekyll default)

## Key Information

### Contact & Social
- **Email**: dr.c.arentsen@gmail.com
- **GitHub**: carentsen
- **Twitter**: carentsen

### Technical Stack
- **Platform**: GitHub Pages
- **Generator**: Jekyll
- **Theme**: Minima
- **Ruby Gems**: github-pages, jekyll-feed
- **Deployment**: GitHub Actions (`.github/workflows/deploy.yml`)

## AI Management Commands

### Content Creation
```bash
# Create new blog post
bundle exec jekyll post "Post Title"

# Serve locally for testing
bundle exec jekyll serve

# Build site
bundle exec jekyll build
```

### Common Tasks
- **New Blog Post**: Create in `_posts/` with format `YYYY-MM-DD-title.markdown`
- **Update About**: Edit `about.markdown`
- **Modify Config**: Edit `_config.yml`
- **Add Pages**: Create `.markdown` files in root directory

## File Structure

```
├── _config.yml           # Site configuration
├── _posts/              # Blog posts
├── _site/               # Generated site (ignored)
├── copilot/             # AI context & templates (excluded from build)
│   ├── instructions/    # Detailed AI instructions
│   ├── templates/       # Content templates
│   ├── examples/        # Example content
│   └── specs/          # Technical specifications
├── .github/
│   ├── workflows/       # GitHub Actions
│   └── ruleset.yml     # Repository rules
├── about.markdown       # About page
├── index.markdown       # Homepage
└── Gemfile             # Ruby dependencies
```

## Content Guidelines

### Blog Posts
- Use Jekyll post naming convention: `YYYY-MM-DD-title.markdown`
- Include proper front matter with layout, title, date, categories
- Follow the style guide in `copilot/specs/STYLE_GUIDE.md`

### Style & Design
- Primary color: Sky Blue (#87CEEB)
- Complementary: Warm Coral (#FFAB87)
- Follow color palette defined in `copilot/specs/STYLE_GUIDE.md`
- Maintain accessibility standards (WCAG AA)

## Deployment

- **Automatic**: Pushes to `main` branch trigger GitHub Actions deployment
- **Manual**: Can be triggered via GitHub Actions web interface
- **URL**: Changes go live at https://carentsen.github.io/

## Repository Rules

- Main branch protected with code review requirements
- Pull requests require 1 approval
- Linear history enforced
- Force pushes blocked

## AI Context Location

All AI-specific context, templates, and instructions are stored in the `copilot/` directory, which is excluded from the Jekyll build process via `_config.yml`.

## Quick Reference

### Creating Content
1. **Blog Post**: Add to `_posts/` with proper naming and front matter
2. **Page**: Add `.markdown` file to root with front matter
3. **Update About**: Edit `about.markdown`

### Testing Changes
1. Run `bundle exec jekyll serve` locally
2. View at http://localhost:4000
3. Make changes and test before pushing

### Deployment
1. Push to `main` branch
2. GitHub Actions automatically builds and deploys
3. Changes live at https://carentsen.github.io/

---

*This file provides essential context for AI assistants managing this Jekyll site. For detailed instructions and templates, see the `copilot/` directory.*