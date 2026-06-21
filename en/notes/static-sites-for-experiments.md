---
layout: page_en
title: "Why Small Experiments Belong on Static Sites"
---

A static site has no database or permanent application server, which is often ideal for self-contained experiments. Every page has a durable entry point, and the files are easy to cache, mirror, and preserve.

![A static browser page containing controls, content, and a generated result](/images/notes/browser.svg)

Data can live in JSON, images, or scripts while the browser handles interaction. Publishing becomes a replacement of files rather than a migration of live state. Reverting a broken release is similarly straightforward.

## Treat the URL as part of the interface

Query parameters and fragments can preserve an experiment's configuration so another person opens the same state. Fragments are not sent to the server and work well for client-side state; query parameters appear in requests and logs.

Static does not mean unstructured. Consistent directories, shared layouts, and link checks prevent gradual decay and make old projects understandable when revisited years later.

## Separate authored content from generated output

Keep Markdown, templates, scripts, and source images outside the publication directory. The build should create a clean destination from scratch. This prevents stale pages from surviving after their source is deleted.

Copy only assets intended for visitors. Package manifests, editor settings, and source maps can be excluded unless they have a deliberate purpose. A `.nojekyll` marker avoids unexpected processing when publishing through GitHub Pages.

## Make deployment reproducible

Pin dependency versions with a lockfile and use the same build command locally and in continuous integration. The deployment workflow should build, upload one artifact, and publish that artifact without modifying the source branch.

Add inexpensive checks: fail on unresolved template markers, missing local files, duplicate output paths, and invalid front matter. Static sites rarely fail through complex server behavior; they fail through quiet omissions.

## Plan for base paths and custom domains

Root-relative URLs work well on a custom domain but break when the site is hosted under a repository subpath. Decide which deployment model the project supports and encode that decision in one URL helper rather than scattering assumptions through templates.

Preserve a custom-domain file in generated output and verify redirects after deployment. A static site is operationally simple, but its links still depend on a consistent public origin.

[中文版](/zh/notes/static-sites-for-experiments.html)
