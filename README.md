# taylorwallgren.com

Static homepage for the apex domain. GitHub Pages, no build step.

## Structure

```
index.html                          the homepage
distributed-ai-cluster.html         write-up: 3-node MLX cluster on M1 Max Macs
agent-coordination-incidents.html   tracker: 2026 agent-coordination incidents, kept current
style.css                           design system (shared visual language with the FieldGuide repo)
CNAME                               taylorwallgren.com
```

The homepage's Writing list is maintained by hand in `index.html`. Its rows
carry a start date rather than a last-updated date, so updating an article
does not require touching the homepage. If a homepage row does change, bump
the homepage `<lastmod>` in `sitemap.xml` too.

Article pages reuse the components in the `ARTICLE PAGES` block at the bottom
of `style.css`, ported from the FieldGuide stylesheet so both properties keep
reading as one body of work.

## Contact

No email address on the page, deliberately — it would be scraped.
LinkedIn is the contact channel.

## Deploy

The repo name does not matter here: a project repo serves a custom apex
domain fine. `twallgren.github.io` naming is only needed if you also want the
default `twallgren.github.io` URL.

1. Push to a GitHub repo.
2. Settings -> Pages: source = deploy from branch, `main`, `/ (root)`.
3. Settings -> Pages -> Custom domain: `taylorwallgren.com`
   (the `CNAME` file is already committed, so this should populate itself).
4. DNS at the registrar — four `A` records at the apex:

   ```
   A   @   185.199.108.153
   A   @   185.199.109.153
   A   @   185.199.110.153
   A   @   185.199.111.153
   ```

   Optional, to catch the `www` form:

   ```
   CNAME   www   twallgren.github.io
   ```

5. Once DNS propagates, tick **Enforce HTTPS**.

## Related

`fieldguide.taylorwallgren.com` is a separate repo (`FieldGuide`) on its
own subdomain, so it can be split off to its own domain later without a
migration.
