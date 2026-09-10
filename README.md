# Product portfolio — tham-tracy.github.io

Source for [tham-tracy.github.io](https://tham-tracy.github.io), a fintech
product-management portfolio. Built with Jekyll and served by GitHub Pages'
native build (no Actions workflow).

## Structure

| Path | Purpose |
|------|---------|
| `index.md` | Portfolio summary — the page to link from a resume or LinkedIn. Prints to a clean PDF. |
| `work/aura.md` | Case study: Aura wealth management platform. |
| `work/tcbs-loan-management.md` | Case study: TCBS loan management system. |
| `_layouts/` | `default`, `summary`, `case-study` templates. |
| `_includes/nav.html` | Top navigation. |
| `assets/style.css` | The entire stylesheet — hand-written, no framework. |
| `assets/img/` | Sanitised screenshots and diagrams. |
| `_config.yml` | Site title, nav, contact links. |

## Local preview (optional)

Requires Ruby. GitHub builds the site server-side regardless, so this is only
for previewing before you push.

```
bundle install
bundle exec jekyll serve --livereload
```

Then open <http://localhost:4000>.

## Editing content

Case-study section order is fixed. Each `## ` heading becomes an entry in the
on-page navigation automatically. Replace the placeholder phone frames in
`work/aura.md` with real images once sanitised screenshots are added to
`assets/img/aura/`.

## A note on confidentiality

Both case studies describe real work. Confidential metrics, internal system
names, and proprietary business rules are generalised or omitted.
