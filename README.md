# Hornet Defense League website

A simple static website for the Hornet Defense League, a 501(c)(3) nonprofit protecting honeybees and native pollinators from the invasive yellow-legged hornet.

Live site: https://hornetdefenseleague.org/

It is plain HTML and CSS. There is no framework, no build step, no backend, and no login. GitHub Pages serves it for free straight from the `main` branch.

## Files

| File | What it is |
|---|---|
| `index.html` | All the page text and sections |
| `styles.css` | Colors, fonts, layout (colors are at the top under `:root`) |
| `images/` | Logo and photos (compressed WebP) |
| `files/` | Downloads: the queen trapping flyer and the trap instructions PDF |

## How to edit the text

1. On GitHub, open `index.html` and click the pencil icon (Edit this file).
2. Find the section you want. Each one starts with a comment like `<!-- MISSION -->`, `<!-- DONATE -->`, `<!-- CONTACT -->`.
3. Change the words between the tags (for example between `<p>` and `</p>`). Leave the tags themselves alone.
4. Click **Commit changes**. The live site updates in a minute or two.

To swap a photo, upload a new image into `images/` and change the matching `src="images/..."` in `index.html`. Keep images under about 300 KB so the page loads fast on phones (https://squoosh.app is a free compressor).

## Online donations

The Donate button goes to the Zeffy donation form the Hornet Defense League set up in November 2026:
https://www.zeffy.com/en-US/donation-form/donate-to-help-the-pollinatora

To change it, find the `<!-- DONATE -->` section in `index.html` and replace the link in the button's `href`.

## Adding a contact form later

The Contact section uses a plain email link. For a real form without a server, sign up at **Formspree** (https://formspree.io, free tier) and paste their form snippet into the `<!-- CONTACT -->` section.

## Custom domain: hornetdefenseleague.org

The domain **hornetdefenseleague.org** is registered at GoDaddy (using GoDaddy's default nameservers) and was connected to this site on 2026-11-11.

- **GitHub:** the `CNAME` file in this repo holds just `hornetdefenseleague.org`. Do not delete it, or the site falls back to the github.io address.
- **DNS at GoDaddy:** four `A` records on `@` (`185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`) and a `CNAME` record `www` pointing to `hunterjsb.github.io`. The old github.io address redirects to the domain.

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
- The Get Involved section uses material the Hornet Defense League sent on November 9, 2026: the trap instructions (typed out on the page, original PDF in `files/`), the Early Spring Queen Trapping flyer (`images/queen-trapping-flyer.webp` on the page, full-size PNG in `files/`), and the nest stages photo (`images/nest-stages.webp`). The flyer says "Early Spring 2027"; add exact dates to the queen trapping card when they are set.
- The logo (`images/logo.webp`, plus `favicon.png` and `social.jpg`) is the "more black" version sent on November 9, 2026. It arrived on a solid black background, which was cut away so it sits on the light page.
- Hornet facts are paraphrased from official sources (Georgia Department of Agriculture, Clemson Department of Plant Industry, USDA APHIS, UGA, Penn State Extension, Washington State Department of Agriculture), all linked in the Resources section. The approach was inspired by Asian Hornet Alert (UK). Detection numbers change quickly, so check the sources each season.
