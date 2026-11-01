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

The Donate button currently opens an email to Hornetdefenseleague@gmail.com. Any of these free nonprofit options gives you a link you can paste in instead:

- **Zeffy** (https://www.zeffy.com): 100% free for nonprofits, no platform fees. Create a donation form and copy its link.
- **PayPal Giving Fund** (https://www.paypal.com/us/webapps/mpp/givingfund): free enrollment for 501(c)(3)s.
- **Stripe Payment Link** (https://stripe.com/payments/payment-links): standard card fees, nonprofit discount available on request.

Then in `index.html`, find the `<!-- DONATE -->` section and replace the `href="mailto:..."` on the button with the new link, and update the button text (for example "Donate online").

## Adding a contact form later

The Contact section uses a plain email link. For a real form without a server, sign up at **Formspree** (https://formspree.io, free tier) and paste their form snippet into the `<!-- CONTACT -->` section.

## Pointing a custom domain (Cloudflare) at GitHub Pages

Once you buy a domain (Cloudflare Registrar sells them at cost):

1. **GitHub:** repo **Settings > Pages > Custom domain**, enter the domain (for example `hornetdefenseleague.org`) and Save. This adds a `CNAME` file to the repo.
2. **Cloudflare:** in the domain's **DNS** tab add:
   - Four `A` records for the root (`@`): `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - A `CNAME` record: name `www`, target `hunterjsb.github.io`
   - Set these records to **DNS only** (grey cloud) at first so GitHub can issue the HTTPS certificate.
3. Wait for GitHub to show the domain as verified, then tick **Enforce HTTPS** in Settings > Pages.
4. Optional: you can switch the records back to Proxied (orange cloud) afterwards. If you do, set Cloudflare **SSL/TLS** mode to **Full**.

GitHub's guide: https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site

## Content notes

- The mission statement is transcribed from the board-review draft. Update it in `index.html` if the board revises it.
- Hornet facts are paraphrased from official sources (Georgia Department of Agriculture, Clemson Department of Plant Industry, USDA APHIS, UGA, Penn State Extension, Washington State Department of Agriculture), all linked in the Resources section. The approach was inspired by Asian Hornet Alert (UK). Detection numbers change quickly, so check the sources each season.
