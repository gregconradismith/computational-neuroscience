# Computational Neuroscience

This repository contains a WordPress export and a generated static version of
the APSC 450 Computational Neuroscience course site.

## Static site

Open `docs/index.html` in a browser to browse the generated site locally. For
GitHub Pages, configure the repository to serve from the `main` branch and the
`/docs` folder.

The generated site includes:

- A course landing page
- Static pages for the syllabus, calendars, readings, foundations, computational
  topics, project descriptions, and resources
- A course updates archive generated from published WordPress posts
- Local copies of the WordPress media export where practical
- Lightweight filtering on the page and post index views

Media files over 100 MB are not copied into `docs/`; links to missing or
oversized WordPress media are left external.

## Regenerate

```sh
sage -python tools/build_static_site.py
```

The generator reads `tmp/computationalneuroscience.WordPress.2026-05-06.xml`,
copies media from `tmp/media-export-156333255-from-0-to-3943`, and rewrites
`docs/`.

If a media file is referenced in the XML but missing from the local media export,
you can attempt a direct download from WordPress with:

```sh
sage -python tools/download_wordpress_uploads.py
```
