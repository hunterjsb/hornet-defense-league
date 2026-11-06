# Hornet Defense League website

A simple static website for the Hornet Defense League, a 501(c)(3) nonprofit protecting honeybees and native pollinators from the invasive yellow-legged hornet.

Live site: https://hunterjsb.github.io/hornet-defense-league/

It is plain HTML and CSS. There is no framework, no build step, no backend, and no login. GitHub Pages serves it for free straight from the `main` branch.

## Files

| File | What it is |
|---|---|
| `index.html` | All the page text and sections |
| `styles.css` | Colors, fonts, layout (colors are at the top under `:root`) |
| `images/` | Logo and photos (compressed WebP) |

## How to edit the text

1. On GitHub, open `index.html` and click the pencil icon (Edit this file).
2. Find the section you want. Each one starts with a comment like `<!-- MISSION -->`, `<!-- DONATE -->`, `<!-- CONTACT -->`.
3. Change the words between the tags (for example between `<p>` and `</p>`). Leave the tags themselves alone.
4. Click **Commit changes**. The live site updates in a minute or two.

To swap a photo, upload a new image into `images/` and change the matching `src="images/..."` in `index.html`. Keep images under about 300 KB so the page loads fast on phones (https://squoosh.app is a free compressor).

## Adding online donations later (no backend needed)

The Donate button currently opens an email to Hornetdefenseleague@gmail.com. The organization has a checking account but no payment processor yet. Any of these free nonprofit options connects to the checking account and gives you a link to paste in:

- **Zeffy** (https://www.zeffy.com): 100% free for nonprofits, no platform fees.
- **Givebutter** (https://givebutter.com): free, donors can leave an optional tip.
- **PayPal** (https://www.paypal.com/us/non-profit): discounted nonprofit rates, or free enrollment through PayPal Giving Fund.

Then in `index.html`, find the `<!-- DONATE -->` section. The comment there lists the three edits: put the link in the button's `href`, change the button text to "Donate online", and change the note under it.

## Adding a contact form later

The Contact section uses a plain email link. For a real form without a server, sign up at **Formspree** (https://formspree.io, free tier) and paste their form snippet into the `<!-- CONTACT -->` section.

## Custom domain: hornetdefenseleague.org (not connected yet)

The domain **hornetdefenseleague.org** is registered at GoDaddy (registered 2026-10-19, using GoDaddy's default nameservers). It is **not** connected to this site yet. There is intentionally no `CNAME` file in this repo; adding one is step 1 below.

When ready:

1. **GitHub:** repo **Settings > Pages > Custom domain**, enter `hornetdefenseleague.org` and Save. This creates a `CNAME` file in the repo containing just `hornetdefenseleague.org`.
2. **DNS** (at GoDaddy, or at Cloudflare if the nameservers are moved there first):
   - Remove GoDaddy's default parking `A` records on `@`.
   - Add four `A` records for `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Add a `CNAME` record: name `www`, value `hunterjsb.github.io`
   - If using Cloudflare, set these to **DNS only** (grey cloud) at first so GitHub can issue the HTTPS certificate.
3. Wait for GitHub to show the domain as verified, then tick **Enforce HTTPS** in Settings > Pages.
4. Optional (Cloudflare only): switch records to Proxied afterwards and set **SSL/TLS** mode to **Full**.

GitHub's guide: https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site

## Content notes

- The mission statement is the text the Hornet Defense League provided in November 2026 (only typos fixed). Update it in `index.html` if the board revises it.
- The Hornet Defense League is not officially working with the SC Department of Agriculture or any agency. Agency pages are linked only as public resources; do not add wording that implies a partnership.
- EIN 42-5169018 is approved for display and appears in the footer and Donate section.
- The honeybee photo (`images/honeybee-flower.webp`) was provided by the Hornet Defense League.
- The look is light and bee-inspired (honey, amber, warm cream, black accents), as the Hornet Defense League asked in November 2026. All colors are at the top of `styles.css`.
- Wording rules from the Hornet Defense League: say "hawking" (never "hovering") for hornets hunting at a hive, write the species as yellow-legged hornet (*Vespa velutina*) and do not add "also known as Asian hornet", and never call the nest a "paper nest" (people confuse it with paper wasp nests).
- Lead with South Carolina (the Lowcountry is the epicenter), then Georgia, then North Carolina.
- The South Carolina numbers (643 nests statewide, 569 in Beaufort County, as of October 27, 2026, source Hornet Herald) and the "over 80% of nests reported by citizens" point were provided by the Hornet Defense League. Update them in the `<!-- SC NUMBERS -->` block of `index.html` when a new Hornet Herald comes out.
- The four hawking photos (`images/hawking-1.webp` to `hawking-4.webp`) were provided by the Hornet Defense League.
- The Get Involved section is waiting on three things, each marked with an `EDIT (still needed)` comment in `index.html`: the trap-building link and bait instructions, photos of the nest stages, and the Early Spring Queen Trapping date and flyer.
- Hornet facts are paraphrased from official sources (Georgia Department of Agriculture, Clemson Department of Plant Industry, USDA APHIS, UGA, Penn State Extension, Washington State Department of Agriculture), all linked in the Resources section. The approach was inspired by Asian Hornet Alert (UK). Detection numbers change quickly, so check the sources each season.
