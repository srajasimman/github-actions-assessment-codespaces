# GitHub Actions Assessment in Codespaces

This repository contains assessment tasks for evaluating GitHub Actions and JavaScript Actions development skills.

## Getting Started

1. Click the "Code" button above
2. Select "Open with Codespaces"
3. Click "Create codespace"

The environment will automatically set up with all necessary tools for GitHub Actions development.

## Environment Features

- Pre-installed tools:
  - [nektos/act](https://github.com/nektos/act) for local GitHub Actions testing
  - Node.js and npm
  - GitHub CLI
  - Docker
  - VS Code with GitHub Actions extensions

<!-- start-assessment-tasks -->
## Assessment Tasks

### Task 1: Create a CI/CD Workflow

Create a GitHub Actions workflow in `.github/workflows/ci-cd.yml` that:

- Runs on pull requests and pushes to main
- Performs linting and unit tests
- Builds and packages the application
- Performs a mock deployment based on the branch
- Implements a matrix strategy for testing across Node.js versions

### Task 2: Create a Custom JavaScript Action

Create a custom JavaScript action in `.github/actions/repo-scanner/` that:

- Scans the repository for specific patterns (outdated dependencies, security issues)
- Generates a report of findings
- Posts a summary as a PR comment
- Fails the workflow if critical issues are found
<!-- end-assessment-tasks -->

## Testing Your Solutions

You can test your workflows using nektos/act:

```bash
# Test a workflow
act -j job_name

# Test with specific event
act pull_request

# Test with environment variables
act -j job_name -e vars.env
```

## Submission

When you've completed the assessment:
1. Commit your changes to a new branch
2. Push the branch to GitHub
3. Create a pull request
4. Share the PR link with the interviewer