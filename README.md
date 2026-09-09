# Bilal Ibrahim — Cover Letter Site

A single-file, self-contained personal cover-letter / portfolio page for
**Bilal Ibrahim Mohamed**, Cloud & DevOps Engineer.

**Live site:** https://bilalibrahim1.github.io/cover-letter/

## What's on the page

- A short intro connecting an electronics/communications engineering
  background to cloud & DevOps work.
- A timeline ("The path") of education and experience.
- Project cards, each with a small inline workflow diagram and a link to
  the project's own GitHub repo.
- Technical skills, certifications, and contact details.

## Features

- **Dark / light mode** — toggle in the top toolbar; the choice is
  remembered on your next visit.
- **In-place editing** — click **Edit page**, then click directly on any
  heading, paragraph, or project text to change it. Changes auto-save as
  you go (look for the "Saved ✓" indicator).
- **Add / remove projects** — in edit mode, a **+ Add a new project**
  button appears at the bottom of the projects list, and a **Delete
  project** button appears under each card.
- **Change the photo** — in edit mode, hover the profile photo and click
  **Change photo** to upload a new image; drag to reposition and use the
  zoom slider to crop it, then save.
- Click **Reset to original** at any time to discard all local edits and
  return to the version in this repo.

## How it works / tech notes

Everything — HTML, CSS and JavaScript — lives in a single file,
`index.html`. There's no build step and no backend:

- Styling uses CSS custom properties, so the dark/light theme is just a
  variable swap driven by a `data-theme` attribute on `<html>`.
- Edits (text, added/removed projects, the profile photo, and the theme
  choice) are saved to the browser's `localStorage`, so they persist per
  browser/device. Because this file is also designed to work inside a
  Claude.ai artifact preview (which provides its own `window.storage`
  API instead of `localStorage`), the page includes a small storage
  adapter that automatically uses whichever one is available — no code
  changes needed to move between the two environments.
- The profile-photo cropper is a small `<canvas>`-based tool: drag to pan,
  use the slider to zoom, and "Save photo" bakes the current view into a
  square image stored as a data URL.

## Updating the live site

This repo is deployed with **GitHub Pages** from the `main` branch. Any
push to `main` that updates `index.html` will redeploy the live site
within about a minute — no separate build/deploy step required.

## Related repos

- [`k8s-cluster-provisioning`](https://github.com/BilalIbrahim1/k8s-cluster-provisioning) — Terraform + Ansible + GitLab CI/CD
- [`system-monitoring-tool`](https://github.com/BilalIbrahim1/system-monitoring-tool) — Bash CPU/memory/disk watchdog with SMTP alerts
