# education.boundlessevents.org

A one-page, static public-information site for Boundless Events (a 501(c)(3)
nonprofit), for the IRS, donors, partner organizations, and the general public.

Content follows the **Boundless Events: Public Information Website Brief**.
Wording the brief marks as approved (intro, mission, vision, values, What We
Do, history) is used verbatim. Policy summaries are condensed from the Code of
Conduct, Consent Policy, Photography & Video and Feedback & Incident Response
pages on www.boundlessevents.org; keep them in sync when those policies change.

Per the brief, the page must not carry event listings, promotions, ticketing or
registration links, social or event feeds, NSFW imagery, or links back to the
main site. Every change must be approved by the Executive Director and the tax
accountant before it is merged.

- Hosting: GitHub Pages, deployed from the `main` branch root, served at
  https://education.boundlessevents.org (the `CNAME` file; DNS is a Namecheap
  `CNAME education → boundless-events.github.io`). The old
  boundless-events.github.io URL redirects there.
- No build step, no analytics, no external scripts or fonts. To update it,
  edit `index.html` in GitHub's web editor (pencil icon), choose "Create a new
  branch and start a pull request", and merge after approval. The site updates
  a minute or two after merge.
- Fonts are self-hosted in `fonts/` (both SIL OFL): Montserrat for body text,
  and Barlow Condensed as the heading fallback. Headings name Blanch first; to
  serve Blanch to every visitor, add a web-licensed `fonts/blanch.woff2` and an
  `@font-face` for it at the top of the `<style>` block.
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
