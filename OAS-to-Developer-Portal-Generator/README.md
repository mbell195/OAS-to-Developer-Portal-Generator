# Automated API Documentation (OAS 3 to GitHub Pages)

[![Build and Deploy API Docs](https://github.com/your-username/your-repo/actions/workflows/deploy-docs.yml/badge.svg)](https://github.com/your-username/your-repo/actions/workflows/deploy-docs.yml)

This project provides a "docs-as-code" pipeline to automatically generate and deploy a beautiful, searchable API documentation website.

It uses a GitHub Action to monitor your OpenAPI 3 specification. When the spec changes, the action automatically:  
1. Converts the `openapi.json` file to Markdown using **Widdershins**.  
2. Builds a static HTML website from the Markdown using **MkDocs** and the Material theme.  
3. Deploys the final site to **GitHub Pages**.

The flow is as follows:  
1. A **Push to `main`** is made (e.g., you update your `openapi.json` file).  
2. The **GitHub Action** triggers.  
3. **Widdershins** runs, converting the `openapi.json` file into `docs/index.md`.  
4. **MkDocs** runs, using the configuration in `mkdocs.yml` to build a full static site from the files in the `docs/` folder.  
5. The **Deploy** job pushes the built HTML/CSS/JS site to the `gh-pages` environment, making it live.

---

## Installation & First-Time Setup

### 1. Fork/Clone this Repository

```bash
git clone [https://github.com/your-username/your-repo.git](https://github.com/your-username/your-repo.git)  
cd your-repo
```

### 2. Add Your OpenAPI Specification

Replace the placeholder openapi.json file in the root of the repository with your own valid OpenAPI 3 specification file.

### 3. Update Site Configuration

Edit the mkdocs.yml file and update the site_url, repo_url, and repo_name values to match your repository.

### 4. Enable GitHub Pages

1. Go to your repository's **Settings** tab.  
2. In the left sidebar, click **Pages**.  
3. Under "Build and deployment," set the **Source** to **GitHub Actions**.

### 5. Push Your Changes

Commit your files and push them to main.

```bash
git add .  
git commit -m "Initial API spec and configuration"  
git push origin main
```

Your first build will trigger. You can watch its progress in your repository's **Actions** tab.

---

## **🛠️ Maintenance & How to Use**

### Updating Your API Docs

**To update your documentation, simply edit openapi.json and push the change to the main branch.**

The GitHub Action will automatically detect the change, rebuild the site, and deploy the updates.

### Running Locally (for Testing)

**Prerequisites:**

* [Node.js](https://nodejs.org/) (for Widdershins)  
* [Python](https://www.python.org/) (for MkDocs)

**Steps:**

1. **Install tools:**  
```bash
pip install mkdocs mkdocs-material  
npm install -g widdershins
```

2. **Run the generation script:**  
```bash
widdershins --summary openapi.json -o docs/index.md  
mkdocs serve
```

3. **Preview your site** at http://127.0.0.1:8000.

## **📂 Project Structure**

.  
├── .github/  
│   └── workflows/  
│       └── deploy-docs.yml   # The GitHub Action automation  
├── docs/  
│   └── index.md              # The generated Markdown (do not edit manually)  
├── .gitignore                # Ignores local build files  
├── mkdocs.yml                # Site configuration (colors, nav, features)  
└── openapi.json              # Your API "source of truth"

---

### 4. Placeholder & Utility Files

You'll need these files to make the project work.

**`openapi.json`** (A simple placeholder to get you started)  
```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "My Sample API",
    "version": "1.0.0",
    "description": "A sample API to demonstrate the documentation pipeline."
  },
  "paths": {
    "/users": {
      "get": {
        "summary": "Get Users",
        "description": "Retrieve a list of users.",
        "responses": {
          "200": {
            "description": "A successful response."
          }
        }
      }
    }
  }
}
```

**docs/index.md** (A placeholder for the very first run)

# API Reference

This documentation is automatically generated. Please wait for the first build to complete.

**.gitignore** (To keep your repository clean)

# Python  
__pycache__/  
*.pyc  
venv/  
*.env

# MkDocs  
site/

# Node  
node_modules/  
npm-debug.log