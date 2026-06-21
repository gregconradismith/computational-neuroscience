# Codex Handoff

Date: 2026-06-21

Repo: `computational-neuroscience`

Branch: `main`

Current Git status after the 2026-06-21 announcement cleanup:

```bash
## main...origin/main
 D docs/_posts/2025-01-22-welcome-to-computational-neuroscience-spring-2025.md
 D docs/_posts/2025-01-24-preparation-for-class-tuesday-january-28.md
 D docs/_posts/2025-01-28-slides-from-today-preparation-for-thursday.md
 D docs/_posts/2025-01-30-bring-the-reading-to-class-today.md
 D docs/_posts/2025-01-31-preparation-for-class-tuesday-february-4.md
 D docs/_posts/2025-02-05-preparation-for-class-thursday-february-6.md
 D docs/_posts/2025-02-08-preparation-for-class-tuesday-february-11.md
 D docs/_posts/2025-02-12-preparation-for-class-thursday-february-6-2.md
 D docs/_posts/2025-02-14-preparation-for-class-tuesday-february-18.md
 D docs/_posts/2025-02-19-preparation-for-next-class-tuesday-february-25.md
 D docs/_posts/2025-02-26-reading-for-thursday-february-27-2.md
 D docs/_posts/2025-02-28-preparation-for-class-tuesday-march-4.md
 D docs/_posts/2025-03-05-reading-for-thursday-march-6.md
 D docs/_posts/2025-03-07-enjoy-spring-break.md
 D docs/_posts/2025-03-19-reading-for-thursday-february-27.md
 D docs/_posts/2025-03-20-preparation-for-class-tuesday-march-25.md
 D docs/_posts/2025-03-25-reading-for-thursday-february-27-3.md
 D docs/_posts/2025-03-28-preparation-for-class-tuesday-april-1.md
 D docs/_posts/2025-04-02-preparation-for-class-thursday-april-3.md
 D docs/_posts/2025-04-04-preparation-for-class-tuesday-april-8.md
 D docs/_posts/2025-04-09-preparation-for-class-thursday-april-10.md
 D docs/_posts/2025-04-12-preparation-for-class-tuesday-april-15.md
 D docs/_posts/2025-04-16-preparation-for-class-thursday-april-17.md
 D docs/_posts/2025-04-21-preparation-for-class-tuesday-april-22.md
 D docs/_posts/2025-04-24-notes-from-class-thursday-april-24.md
 D docs/_posts/2025-05-06-final-project-reminders.md
 M .codex/handoff.md
```

## Repository Role

This repository publishes the APSC 450 Computational Neuroscience course site
from editable Markdown source in `docs/`.

## High-Value Context

- Read `AGENTS.md` before editing.
- Source pages live in `docs/_materials/`.
- Source posts live in `docs/_posts/`.
- GitHub Actions builds Jekyll from `docs/` and deploys Pages.
- The original WordPress export is preserved under `tmp/`.
- Oversized WordPress media may be left as external links rather than copied
  into the repository.
- Public site: https://gregconradismith.github.io/computational-neuroscience/
- Recent design work aligned the site with the
  `cellular-biophysics-and-modeling` course-site style:
  - landing page uses a full-width image banner;
  - landing page menu uses large centered buttons;
  - home page recent announcements use a centered dated list;
  - `/posts/` Announcements uses a centered dated list rather than card panels;
  - archive/export framing was removed from public-facing pages.
- The latest pushed commit at this handoff is `133aa48` (`Remove announcements
  subtitle`). If local state differs, inspect `git log --oneline -5`.
- On 2026-06-19, the published CN `/posts/` HTML and CSS were fetched directly
  and confirmed to no longer include the Announcements subtitle and to include
  `.posts-listing` centering rules. If Greg sees stale text, suspect browser or
  CDN cache first.
- On 2026-06-21, Greg reviewed all 26 announcement posts in `docs/_posts/`
  one by one and chose `delete` for each. The directory now has no remaining
  posts. `git diff --check` passed after the deletions.

## Useful Commands

Check Git state:

```bash
git status --short --branch
git diff --check
```

Inspect the Pages workflow:

```bash
sed -n '1,220p' .github/workflows/pages.yml
```

## Notes For The Next Codex

- Do not run local Jekyll/Bundler unless Greg explicitly asks.
- Keep source edits in Markdown and shared layouts/assets.
- Preserve the CBM-inspired live-course-portal feel. Avoid reverting to
  generic WordPress-export card grids for the landing page or Announcements.
- Avoid committing generated `_site/`, Bundler artifacts, or export noise.
- After adding or updating `AGENTS.md` / `CODEX-HANDOFF.md`, commit the scoped
  change and push it to `main`.
