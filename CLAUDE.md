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

### Development Workflow
```bash
# Start new feature from development branch
git checkout development && git pull origin development
git checkout -b feature/descriptive-name

# Local development and testing
bundle exec jekyll serve

# Create PR to development branch
gh pr create --base development --title "..." --body "..."
```

### Content Creation
- **New Blog Post**: Use template from `copilot/templates/blog-post-template.md`
- **Update About**: Edit `about.markdown` via feature branch
- **Add Pages**: Use `copilot/templates/page-template.md`
- **Project Showcase**: Use `copilot/templates/project-showcase-template.md`

### Branching Strategy
- **main**: Production (protected, no direct commits)
- **development**: Integration branch (AI work via PRs)
- **feature/***: AI creates for each task

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

- **Development**: PRs to development trigger CI builds and testing
- **Production**: Manual release workflow creates PR from development to main
- **Release Process**: Human-controlled via GitHub Actions "Release to Main" workflow
- **URL**: Production changes go live at https://carentsen.github.io/ after main deployment

## Repository Rules

- Main branch protected with code review requirements
- Pull requests require 1 approval
- Linear history enforced
- Force pushes blocked

## AI Context Location

All AI-specific context, templates, and instructions are stored in the `copilot/` directory, which is excluded from the Jekyll build process via `_config.yml`.

## Quick Reference

### AI Workflow (Development Branch)
1. **Create Feature Branch**: `git checkout -b feature/task-name` from development
2. **Make Changes**: Use templates and follow guidelines
3. **Test Locally**: `bundle exec jekyll serve` at http://localhost:4000
4. **Create PR**: `gh pr create --base development` with detailed description
5. **Review & Merge**: Human or AI approval merges to development

### Release to Production (Human-Controlled)
1. **Trigger Release**: Use GitHub Actions "Release to Main" workflow
2. **Choose Release Type**: patch, minor, or major
3. **Add Release Notes**: Describe changes in the release
4. **Review PR**: Automated PR from development to main
5. **Merge**: Human approval deploys to https://carentsen.github.io/

---

*This file provides essential context for AI assistants managing this Jekyll site. For detailed instructions and templates, see the `copilot/` directory.*