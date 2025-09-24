# AI Pull Request Workflow

## Branching Strategy Overview

This project uses a **development → main** branching strategy designed for AI-driven content creation and human-controlled releases.

### Branch Structure
- **`main`**: Production branch (protected, no direct commits)
- **`development`**: Integration branch for AI work (protected, PR-only)
- **Feature branches**: AI creates these for each task (e.g., `feature/new-blog-post`, `feature/update-about`)

## AI Workflow Process

### 1. Feature Development Workflow

#### Step 1: Create Feature Branch
```bash
# Always work from development branch
git checkout development
git pull origin development

# Create descriptive feature branch
git checkout -b feature/descriptive-name

# Examples:
# feature/blog-post-jekyll-tips
# feature/update-portfolio-section
# feature/fix-navigation-mobile
```

#### Step 2: Make Changes
- Follow templates in `copilot/templates/`
- Use instructions in `copilot/instructions/`
- Test locally: `bundle exec jekyll serve`
- Commit with descriptive messages

#### Step 3: Create Pull Request to Development
```bash
# Push feature branch
git push origin feature/descriptive-name

# Create PR using GitHub CLI
gh pr create \
  --base development \
  --title "Add new blog post: Jekyll Tips" \
  --body "$(cat <<'EOF'
## Summary
- Added new blog post about Jekyll optimization tips
- Includes code examples and best practices
- Follows style guide and template structure

## Changes
- New post: `_posts/2025-09-23-jekyll-optimization-tips.md`
- Updated navigation if needed
- Added any required assets

## Testing
- [x] Local build successful
- [x] Content follows style guide
- [x] Links work correctly
- [x] Mobile responsive

🤖 Generated with Claude Code
EOF
)"
```

### 2. Pull Request Guidelines

#### PR Title Format
- `Add [content type]: [descriptive title]`
- `Update [section]: [what changed]`
- `Fix [issue]: [brief description]`

**Examples:**
- `Add blog post: Understanding Jekyll Liquid Templating`
- `Update about page: Add new professional experience`
- `Fix navigation: Mobile menu accessibility improvements`

#### PR Description Template
```markdown
## Summary
Brief description of changes and why they were made.

## Changes
- List of specific files changed
- New content added
- Configurations updated

## Testing
- [ ] Local build successful
- [ ] Content follows style guide
- [ ] All links work correctly
- [ ] Mobile responsive
- [ ] SEO optimized

## Additional Notes
Any special considerations or follow-up needed.

🤖 Generated with Claude Code
```

### 3. Development Branch Management

#### Merging PRs to Development
1. **Review changes** in PR interface
2. **Check automated builds** pass
3. **Merge when ready** - creates integration in development
4. **Delete feature branch** after merge

#### Development Branch Testing
- Development branch auto-builds on push
- Preview deployments available (if configured)
- Integration testing happens automatically

### 4. Release Process (Human-Controlled)

#### When Ready for Production
1. **Manual trigger** of Release workflow in GitHub Actions
2. **Choose release type**: patch, minor, or major
3. **Add release notes** describing changes
4. **Automated PR creation** from development to main
5. **Human review and approval** required
6. **Merge triggers deployment** to production

#### Release Workflow Steps
```yaml
# GitHub Actions automatically:
1. Validates development branch builds
2. Creates release branch
3. Opens PR to main with summary
4. Waits for human approval
5. Deploys to production on merge
```

### 5. AI Assistant Guidelines

#### Content Creation Tasks
```bash
# Standard workflow for new content
1. Create feature branch from development
2. Use appropriate template from copilot/templates/
3. Follow content guidelines from copilot/instructions/
4. Test locally
5. Create PR to development with detailed description
```

#### Site Maintenance Tasks
```bash
# For updates and fixes
1. Create feature branch for specific task
2. Make focused, atomic changes
3. Test thoroughly
4. Document changes in PR description
5. Include any necessary follow-up notes
```

#### Quality Checklist
Before creating any PR, ensure:
- [ ] Content follows style guide (`copilot/specs/STYLE_GUIDE.md`)
- [ ] Local Jekyll build succeeds
- [ ] All links are functional
- [ ] Images have proper alt text
- [ ] Mobile responsive design maintained
- [ ] SEO elements included (titles, descriptions, etc.)
- [ ] Commit messages are descriptive
- [ ] PR description is comprehensive

### 6. Workflow Commands Reference

#### Essential Git Commands
```bash
# Start new feature
git checkout development
git pull origin development
git checkout -b feature/task-name

# Work and commit
git add .
git commit -m "Descriptive commit message"
git push origin feature/task-name

# Create PR
gh pr create --base development --title "..." --body "..."

# Check PR status
gh pr status

# Switch back to development
git checkout development
git pull origin development
```

#### Jekyll Commands
```bash
# Local development
bundle exec jekyll serve

# Build site
bundle exec jekyll build

# Build with drafts
bundle exec jekyll serve --drafts
```

### 7. Troubleshooting

#### Common Issues
- **Build failures**: Check Jekyll syntax and missing files
- **PR conflicts**: Rebase feature branch on latest development
- **Permission errors**: Ensure proper branch protections are configured

#### Emergency Procedures
- **Broken development**: Create hotfix branch from last known good commit
- **Production issues**: Create emergency patch PR directly to main (with justification)

This workflow ensures clean separation between AI development work and human-controlled production releases while maintaining code quality and review processes.