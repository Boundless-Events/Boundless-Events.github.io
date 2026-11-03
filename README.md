# boundless-events.github.io

A one-page, static summary of Boundless Events (a 501(c)(3) nonprofit) for
use as the organization website on IRS and other formal filings.

All content is adapted from www.boundlessevents.org (About, Code of Conduct,
Consent Policy, Feedback & Incident Response, Volunteer, Scholarship pages).
Keep it in sync with that site when the mission, contacts, or policies change.

- Hosting: GitHub Pages, deployed from the `main` branch root.
- No build step, no analytics, no external scripts or fonts. Edit `index.html`
  and push; the site updates in a minute or two.
- `logo-mark.png`, `favicon.png` and `apple-touch-icon.png` are cropped from
  the main site's `public/logo.png`.

## Keeping it out of search engines

This page exists only to be referenced on filings, so it is kept out of
search results:

- Every HTML page carries
  `<meta name="robots" content="noindex, nofollow, noimageindex">`.
  GitHub Pages can't set response headers, so an `X-Robots-Tag` header isn't
  available; the meta tag is the supported equivalent.
- There is deliberately **no `robots.txt`**. A `Disallow: /` would stop
  crawlers from fetching the page, so they would never see the `noindex` and
  could still list the bare URL if it were linked from elsewhere.
- The `Robots meta` workflow fails CI if any `.html` file is missing the tag.
  Add the same tag to any new page.
