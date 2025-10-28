### Introduction to GitHub Actions
GitHub Actions is a powerful tool for automating workflows directly within your GitHub repositories.


### What is a Runner?
A runner is a server that executes the commands defined in your GitHub Actions workflows. It provides the environment for running jobs, which can be configured to meet specific requirements


### Types of Runners

GitHub-Hosted Runners: These are virtual machines provided and maintained by GitHub. They are preconfigured with tools and environments for most workflows and are a great choice for general automation tasks.

Self-Hosted Runners: These are servers you configure and manage yourself. They allow for more control and customization, such as using specialized hardware or accessing private resources.


### Prerequisites
```
A GitHub account.
A GitHub repository where you have write access.
Basic understanding of YAML syntax.
Familiarity with basic command-line operations.
```

### Project Structure
```
.github/workflows/checkout.yml

```

### Detailed Breakdown of Steps

```
- name: Checkout repository
  uses: actions/checkout@v4
```
 Purpose: Clones the repository onto the runner. This step ensures access to the repository's files for subsequent steps.

### List Files
```
- name: List files
  run: ls -la
```
Purpose: Lists all files in the repository directory, including hidden ones. Outputs file permissions, ownership, and sizes.


### Display System Information

```
- name: Show system info
  run: |
    echo "Repository: $GITHUB_REPOSITORY"
    echo "Operating System: $(uname -a)"
    echo "Current Directory: $(pwd)"
```

Purpose:
Demonstrates using environment variables (e.g., $GITHUB_REPOSITORY).
Displays system information using Linux commands (uname, pwd).

### Check Software Versions

```
- name: Check versions
  run: |
    echo "Node version: $(node --version)"
    echo "Python version: $(python --version)"
    echo "Git version: $(git --version)"
```
Purpose: Verifies the versions of Node.js, Python, and Git installed on the runner. Uses command substitution to insert command output into echo statements.