# Jekyll Workflow Guide

## Development Workflow

### 1. Local Development Setup

```bash
# Install dependencies
bundle install

# Start local development server
bundle exec jekyll serve

# Access local site
# Open http://localhost:4000 in browser
```

### 2. Creating New Content

#### Blog Post Workflow
1. **Create new post file**:
   ```bash
   # File naming: YYYY-MM-DD-title.markdown
   touch _posts/2025-09-23-my-new-post.markdown
   ```

2. **Use template**:
   - Copy from `copilot/templates/blog-post-template.md`
   - Replace all `{{PLACEHOLDER}}` values
   - Update front matter with real values

3. **Write content**:
   - Follow structure from template
   - Use proper markdown formatting
   - Include code blocks with language specification

4. **Test locally**:
   ```bash
   bundle exec jekyll serve --drafts
   ```

5. **Review and publish**:
   - Check formatting and links
   - Verify responsive design
   - Push to main branch for deployment

#### Page Creation Workflow
1. **Create page file** in root directory
2. **Use page template** from `copilot/templates/`
3. **Update `_config.yml`** if navigation changes needed
4. **Test and deploy**

### 3. Content Management

#### Image Workflow
1. **Create assets directory** if not exists:
   ```bash
   mkdir -p assets/images
   ```

2. **Add optimized images**:
   - Compress for web
   - Use descriptive filenames
   - Include alt text in markdown

3. **Reference in content**:
   ```markdown
   ![Alt text]({{ '/assets/images/filename.jpg' | relative_url }})
   ```

#### SEO Optimization
1. **Front matter optimization**:
   - Descriptive titles
   - Meta descriptions
   - Relevant categories and tags

2. **Content optimization**:
   - Use heading hierarchy (H1, H2, H3)
   - Include internal/external links
   - Write compelling excerpts

### 4. Deployment Workflow

#### Automatic Deployment
1. **Commit changes**:
   ```bash
   git add .
   git commit -m "Add new blog post: Title"
   ```

2. **Push to main**:
   ```bash
   git push origin main
   ```

3. **Monitor deployment**:
   - Check GitHub Actions tab
   - Verify live site updates

#### Manual Deployment Trigger
1. Go to GitHub repository
2. Navigate to Actions tab
3. Select "Deploy to GitHub Pages" workflow
4. Click "Run workflow"

### 5. Maintenance Workflow

#### Regular Updates
- **Monthly**: Update dependencies with `bundle update`
- **Quarterly**: Review and update content
- **As needed**: Security updates and Jekyll version updates

#### Content Audit
1. **Review analytics** (if configured)
2. **Update outdated content**
3. **Fix broken links**
4. **Optimize underperforming posts**

### 6. Troubleshooting

#### Common Issues

**Build Failures**:
```bash
# Check for syntax errors
bundle exec jekyll build --verbose

# Check dependencies
bundle install
```

**Local Development Issues**:
```bash
# Clear cache
rm -rf _site .jekyll-cache

# Restart server
bundle exec jekyll serve --force_polling
```

**Deployment Issues**:
- Check GitHub Actions logs
- Verify repository settings
- Ensure Pages is enabled

### 7. Quality Checklist

Before publishing content:
- [ ] Content follows style guide
- [ ] All links work correctly
- [ ] Images have alt text
- [ ] Mobile responsive
- [ ] SEO optimized
- [ ] Spell-checked and proofread
- [ ] Local testing completed

### 8. Git Workflow

#### Branch Strategy
- **main**: Production-ready content
- **drafts**: Work-in-progress content
- Feature branches for major changes

#### Commit Messages
```bash
# Good commit messages
git commit -m "Add blog post: Understanding Jekyll Workflows"
git commit -m "Update about page with new bio"
git commit -m "Fix broken link in navigation"

# Include context for major changes
git commit -m "Restructure site navigation

- Add portfolio section
- Update header layout
- Improve mobile responsiveness"
```

This workflow ensures consistent, high-quality content creation and deployment.