# Branch Protection Configuration

GitHub branch protection rules and rulesets cannot be configured via YAML files in the repository. They must be configured through the GitHub web interface or API.

## How to Configure Branch Protection

1. Go to your repository on GitHub
2. Navigate to **Settings** → **Branches**
3. Click **Add branch protection rule**
4. Configure the following settings for the `main` branch:

### Recommended Settings for Main Branch

- **Branch name pattern**: `main`
- **Require a pull request before merging**
  - Required approving reviews: 1
  - Dismiss stale pull request approvals when new commits are pushed
  - Require review from Code Owners (if using CODEOWNERS file)
- **Require status checks to pass before merging**
  - Require branches to be up to date before merging
  - Status checks: `build` (from GitHub Actions)
- **Require conversation resolution before merging**
- **Require linear history**
- **Do not allow force pushes**
- **Do not allow deletions**

## Alternative: Repository Rulesets (Beta)

GitHub also offers Repository Rulesets (newer feature):

1. Go to **Settings** → **Rules** → **Rulesets**
2. Click **New ruleset** → **New branch ruleset**
3. Configure similar protections as above

## For Repository Admins

If you need to merge without approval (emergency fixes), you can:
- Temporarily disable branch protection
- Or ensure "Allow administrators to bypass" is enabled in the protection rules

## Reference

- [GitHub Docs: About protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)
- [GitHub Docs: Repository rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets)
