# EUVD docs content

These markdown files back the static pages of the EUVD website. **They must live in the public repo [`enisaeu/euvd-docs-public`](https://github.com/enisaeu/euvd-docs-public) at the root of `main`.** Copy/move them there — they are checked in here only as a seed for the initial publish.

## Mapping

| File | URL on the site |
|---|---|
| `about.md` | https://euvd.enisa.europa.eu/about |
| `faq.md` | https://euvd.enisa.europa.eu/faq |
| `apidoc.md` | https://euvd.enisa.europa.eu/apidoc |

## How edits propagate

1. Edit a file on `main` in `enisaeu/euvd-docs-public` (pencil icon on GitHub or local commit + push).
2. GitHub's raw CDN refreshes within ~5 minutes.
3. The next visitor sees the new content on hard refresh. No build, no deploy.

If the live site keeps showing the old text after ~5 min, append `?t=1` to the URL to bust the browser's HTTP cache while testing.

## Supported markdown

GitHub-flavored markdown: headings, paragraphs, lists, links, code blocks, tables, blockquotes, horizontal rules, images.

Raw HTML is **disabled** — anything in `<tags>` will appear as plain text. Use markdown syntax instead.

## Failure mode

If the file is missing, renamed, or GitHub is unreachable, the page falls back to the original hardcoded version of the content (bundled in the SPA). The page never shows an error.

## Images

Reference images by absolute URL:

```markdown
![alt](https://raw.githubusercontent.com/enisaeu/euvd-docs-public/main/images/foo.png)
```

Commit the image under `images/` in the same repo.
