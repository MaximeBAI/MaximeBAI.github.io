# Agentforce Demo Site (GitHub Pages)

This repo is a simple **GitHub Pages** site with:
- a homepage (`/`)
- an **Agentforce** page (`/agentforce`)

## Configure your Agentforce deployment URL

Edit `_config.yml`:

- `agentforce_url`: used for a direct link
- `agentforce_iframe_url`: used to embed in an iframe (optional)

If the embed doesn’t work, it usually means the deployment blocks iframes via `X-Frame-Options` / CSP. In that case, keep only `agentforce_url`.

## GitHub Pages settings

In your repo: **Settings → Pages**

- **Source**: Deploy from a branch
- **Branch**: `main` / `root`

Then wait ~1–3 minutes and open your site.
