# Deploy HTML to GitHub Pages with GitHub Actions</h1>

## This repository demonstrates a simple HTML deployment to GitHub Pages using GitHub Actions.
# Overview

The workflow automates the deployment of an index.html file to GitHub Pages whenever changes are pushed to the main branch. It uses GitHub Actions to streamline this process.

# Workflow Explanation

The workflow file is located in .github/workflows/deploy.yml. Here's a breakdown of each section:

# Trigger
The workflow triggers automatically on a push event to the main branch:
```
on:
  push:
    branches:
      - main
```
# Job: ```deploy```
The job runs on Ubuntu and consists of several steps:
1. Checkout Code
Fetches the repository code so the workflow can access it.
```
   - name: Checkout Code 
     uses: actions/checkout@v4
```
2. Set Up GitHub Pages
Prepares the environment for GitHub Pages deployment.

```
- name: Set up GitHub Pages
  uses: actions/configure-pages@v4
```
3. Upload HTML Files
Uploads the contents of the repository as an artifact to GitHub Pages.

```
- name: Upload HTML to GitHub Pages
  uses: actions/upload-pages-artifact@v2
  with:
    path: ./  # Uploads everything in the root directory
```
 4.  Deploy to GitHub Pages
Deploys the uploaded artifact to GitHub Pages.

```
- name: Deploy to GitHub Pages
  uses: actions/deploy-pages@v2
```

project-idea-from: https://roadmap.sh/projects/github-actions-deployment-workflow

