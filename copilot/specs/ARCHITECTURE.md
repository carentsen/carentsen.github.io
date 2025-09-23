# Site Architecture Documentation

## Overview

This Jekyll site is designed for GitHub Pages deployment with a focus on maintainability, performance, and AI-assisted management.

## Technical Architecture

### Core Technologies
- **Static Site Generator**: Jekyll 4.x
- **Theme**: Minima (Jekyll default)
- **Hosting**: GitHub Pages
- **Deployment**: GitHub Actions
- **Version Control**: Git/GitHub

### File Structure

```
carentsen.github.io/
├── _config.yml              # Jekyll configuration
├── _posts/                  # Blog posts (YYYY-MM-DD-title.md)
├── _site/                   # Generated site (auto-generated)
├── _data/                   # Data files (YAML, JSON, CSV)
├── _includes/               # Reusable template partials
├── _layouts/                # Page layouts
├── _sass/                   # Sass/SCSS stylesheets
├── assets/                  # Static assets
│   ├── images/             # Image files
│   ├── css/                # Compiled CSS
│   └── js/                 # JavaScript files
├── copilot/                # AI management context (excluded from build)
│   ├── instructions/       # Detailed AI instructions
│   ├── templates/          # Content templates
│   ├── examples/           # Example content
│   └── specs/              # Technical specifications
├── .github/                # GitHub configuration
│   ├── workflows/          # GitHub Actions
│   └── ruleset.yml        # Repository protection rules
├── about.markdown          # About page
├── index.markdown          # Homepage
├── CLAUDE.md              # AI context overview
├── Gemfile                # Ruby dependencies
└── .gitignore             # Git ignore rules
```

### Content Architecture

#### Page Hierarchy
```
├── Home (index.markdown)
├── About (about.markdown)
├── Blog (auto-generated from _posts/)
└── [Custom Pages] (*.markdown in root)
```

#### URL Structure
- **Homepage**: `/`
- **About**: `/about/`
- **Blog Posts**: `/YYYY/MM/DD/title/`
- **Custom Pages**: `/page-name/`

### Theme Structure (Minima)

#### Layouts Available
- `default` - Base layout with header/footer
- `home` - Homepage layout with post list
- `page` - Static page layout
- `post` - Blog post layout

#### Includes Available
- `header.html` - Site header with navigation
- `footer.html` - Site footer
- `head.html` - HTML head section
- `social.html` - Social media links

## Deployment Architecture

### GitHub Actions Workflow
1. **Trigger**: Push to main branch or manual dispatch
2. **Build**: Jekyll processes source files
3. **Deploy**: Artifacts uploaded to GitHub Pages
4. **Live**: Site available at https://carentsen.github.io/

### Build Process
```yaml
# .github/workflows/deploy.yml
on:
  push:
    branches: [main]
  workflow_dispatch:

jobs:
  deploy:
    - Checkout source code
    - Setup GitHub Pages
    - Upload build artifact
    - Deploy to Pages environment
```

### Environment Configuration
- **Development**: Local Jekyll server
- **Staging**: GitHub Pages preview (if configured)
- **Production**: GitHub Pages main site

## Content Management System

### Front Matter Schema

#### Blog Posts
```yaml
---
layout: post
title: "Post Title"
date: YYYY-MM-DD HH:MM:SS +0000
categories: [category1, category2]
tags: [tag1, tag2, tag3]
excerpt: "Brief description"
author: "Christian Arentsen"
---
```

#### Pages
```yaml
---
layout: page
title: "Page Title"
permalink: /custom-url/
description: "Meta description"
---
```

### Content Types
- **Blog Posts**: Time-based content in `_posts/`
- **Static Pages**: Timeless content in root directory
- **Data Files**: Structured data in `_data/`
- **Assets**: Images, CSS, JS in `assets/`

## AI Management Architecture

### Context Structure
```
copilot/
├── instructions/           # Detailed task instructions
│   ├── content-creation.md
│   ├── site-maintenance.md
│   └── workflow-guide.md
├── templates/             # Standardized content templates
│   ├── blog-post-template.md
│   ├── page-template.md
│   └── project-showcase-template.md
├── examples/              # Reference examples
│   └── sample-content.md
└── specs/                 # Technical specifications
    ├── STYLE_GUIDE.md
    └── ARCHITECTURE.md
```

### AI Integration Points
- **CLAUDE.md**: Main context file for AI assistants
- **Templates**: Standardized content creation
- **Instructions**: Step-by-step workflow guidance
- **Examples**: Quality and style references

## Performance Architecture

### Optimization Strategies
- **Static Generation**: No server-side processing
- **CDN Delivery**: GitHub Pages uses CDN
- **Image Optimization**: Manual optimization workflow
- **Minimal Dependencies**: Lightweight theme and plugins

### Caching Strategy
- **Browser Caching**: Static assets cached by browser
- **CDN Caching**: GitHub Pages CDN handles caching
- **Build Caching**: Jekyll cache for faster local builds

## Security Architecture

### Repository Security
- **Branch Protection**: Main branch requires reviews
- **Dependency Scanning**: GitHub Dependabot enabled
- **Access Control**: Repository permissions managed
- **Secrets Management**: No secrets stored in repository

### Content Security
- **Input Validation**: Markdown is safe by default
- **XSS Prevention**: Jekyll escapes variables
- **HTTPS Enforcement**: GitHub Pages enforces HTTPS
- **CSP Headers**: Can be added via Jekyll plugins

## Monitoring and Analytics

### Available Metrics
- **Build Status**: GitHub Actions provides build monitoring
- **Uptime**: GitHub Pages SLA monitoring
- **Performance**: Can integrate with external services
- **Analytics**: Can add Google Analytics or alternatives

### Error Handling
- **Build Failures**: Logged in GitHub Actions
- **404 Errors**: Custom 404.html page
- **Broken Links**: Manual review process
- **Recovery**: Git history enables rollback

## Scalability Considerations

### Content Scale
- **Posts**: Jekyll handles thousands of posts efficiently
- **Assets**: GitHub repository size limits apply
- **Build Time**: Increases with content volume
- **CDN**: GitHub Pages CDN scales automatically

### Feature Expansion
- **Plugins**: Limited by GitHub Pages whitelist
- **Custom Domains**: Supported via CNAME
- **Comments**: Third-party services (Disqus, etc.)
- **Search**: Client-side search via Lunr.js

## Migration and Backup

### Data Portability
- **Content**: Portable markdown files
- **Configuration**: Standard Jekyll configuration
- **Assets**: Standard file formats
- **Export**: Jekyll can export to various formats

### Backup Strategy
- **Primary**: Git repository on GitHub
- **Secondary**: Local clones and external backups
- **Assets**: Version controlled with source
- **Recovery**: Git history enables point-in-time recovery

This architecture supports long-term maintainability and AI-assisted management while leveraging the reliability and simplicity of Jekyll and GitHub Pages.