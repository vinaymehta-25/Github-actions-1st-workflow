# Portfolio Website — CI/CD with GitHub Actions

A static portfolio website automatically built and deployed to **GitHub Pages** using a custom **GitHub Actions** CI/CD pipeline.

🔗 **Live site:** [vinaymehta-25.github.io/Github-actions-1st-workflow](https://vinaymehta-25.github.io/Github-actions-1st-workflow/)

![Deploy Status](https://github.com/vinaymehta-25/Github-actions-1st-workflow/actions/workflows/portfolio-deploy.yml/badge.svg)

---

## Overview

This project demonstrates an end-to-end CI/CD workflow — every push to `main` automatically triggers a pipeline that packages the site and deploys it live, with zero manual steps.

**Pipeline flow:**
```
Push to main → Checkout code → Configure GitHub Pages → Upload artifact → Deploy to GitHub Pages
```

## Tech Stack

- **Frontend:** HTML, CSS, JS
- **CI/CD:** GitHub Actions
- **Hosting:** GitHub Pages

## Workflow

The deployment pipeline is defined in [`.github/workflows/portfolio-deploy.yml`](.github/workflows/portfolio-deploy.yml) and uses official GitHub Actions:

| Step | Action Used |
|---|---|
| Checkout repo | `actions/checkout@v4` |
| Configure Pages | `actions/configure-pages@v4` |
| Upload artifact | `actions/upload-pages-artifact@v4` |
| Deploy to Pages | `actions/deploy-pages@v4` |

Triggered on every push to the `main` branch via `workflow_dispatch` and `push` events.

## Project Structure

```
Github-actions-1st-workflow/
├── .github/
│   └── workflows/
│       └── portfolio-deploy.yml   # CI/CD pipeline definition
├── index.html                     # Portfolio site
└── README.md
```

## What I Learned

- Writing and debugging a GitHub Actions YAML pipeline from scratch
- Configuring repository permissions (`pages: write`, `id-token: write`) for automated deployments
- Root-cause debugging a failed pipeline using Actions run logs (artifact path resolution issue)
- GitHub Pages deployment flow via Actions vs. traditional branch-based deployment

---

*Built as part of my DevOps learning journey — hands-on CI/CD practice ahead of Docker, Kubernetes, and Terraform.*