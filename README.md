# vivienanh-hub.github.io

Personal site for Van-Anh Nguyen (Vivian) — product management notes, projects, and long-form writing.

Live at https://vivienanh-hub.github.io

## Structure

- `index.md` — home / about page
- `projects.md` — PM tooling and side projects
- `notes.md` — blog index (`layout: home`), lists posts from `_posts/`
- `contact.md` — contact page
- `_posts/` — blog posts, named `YYYY-MM-DD-title.md`
- `redirects/` — static redirect pages for renamed/moved posts
- `_config.yml` — site-wide settings (title, nav, social links, colours)
- `assets/` — images, custom CSS/JS

## Local development

Requires Ruby + Bundler.

```
bundle install
bundle exec jekyll serve
```

Site will be available at http://localhost:4000.

## Deployment

Hosted on GitHub Pages, built automatically from `master` on push. `.github/workflows/ci.yml` runs a build-only check on every push/PR to catch breakages before they reach Pages.

## Adding a post

Add a file to `_posts/` named `YYYY-MM-DD-title.md` with YAML front matter (see existing posts for the format). If a post is renamed, add a static redirect in `redirects/` (see `redirects/2026-08-02-school-of-one.html` for an example) so old links keep working.

## Credits

Built on [Beautiful Jekyll](https://github.com/daattali/beautiful-jekyll) by [Dean Attali](https://deanattali.com), MIT licensed — see `LICENSE`.
