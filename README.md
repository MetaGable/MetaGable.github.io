# Gene Chen — personal page

Source for <https://metagable.github.io>. Plain static HTML and CSS: no build step and no
JavaScript.

| File         | What it is                                                         |
|--------------|--------------------------------------------------------------------|
| `index.html` | The whole page (About, Research, Publications, Talks, CV, Contact) |
| `style.css`  | Styles; accent colour `#23637E` matches the CV                     |
| `cv.pdf`     | The CV linked from the page (public copy, no phone number)         |

## Preview locally

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Publishing changes

The repository is served by GitHub Pages from `main`, folder `/ (root)`. Commit and push to
`main`; the live page updates after a minute or two.

## Editing the text

Everything is in `index.html`. Each research entry is one `<article class="entry">`; the
publications are an ordered list; talks are a list. A detail that is not yet confirmed gets a
`<mark class="todo">TODO: …</mark>` so it shows on the page; remove each one once resolved
(`grep -c TODO index.html` should print `0` before pushing).

## Updating the CV

`cv.pdf` is the public build of the résumé, which leaves out the phone number so the page
publishes no phone number or street address. Rebuild it from the résumé sources
(`resume-public.tex`, which inputs `resume.tex`) and replace `cv.pdf`. Do not copy the full
`resume.pdf` over it.
