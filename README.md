# Printiqo – one-page printing shop website

A single, standalone page (`index.html`) with no build step, no sign-in and no backend.
Visitors build an order and send it to your WhatsApp.

## Edit these first

Open `index.html` and search for the `CONFIG` block near the bottom of the file:

| Setting | What to put |
|---|---|
| `businessName` | Already set to Printiqo |
| `whatsappNumber` | Set to `27681924221` (068 192 4221). Use country code, digits only |
| `helloText` | The message the floating button pre-fills |

Then search the page for every `[BRACKETED PLACEHOLDER]` (area, tagline, address, hours,
reviews, FAQ answers) and replace it with your real wording. Nothing in brackets was invented.

## Product mockups

The product picker, "What we print" and the live order preview use simple mockups drawn in code
(`MOCKUPS` section of `index.html`), so no product photos are needed. The preview tints the item from the
colour the customer types (navy, white, maroon and so on) and places the chosen design where the print
position says. To use a real photo for a product instead, set its `img` in `PRODUCTS`.

Caps have a "Cap type" picker with 17 styles (baseball, flat brim, trucker, 5 panel, 6 panel, snapback,
strapback, fitted, flexfit, dad hat, golf, visor, flat cap, newsboy, fisherman, army and bucket hat),
each with its own front, side and back drawing. To add or remove a style, edit the `variants` list on the
Caps entry in `PRODUCTS`; each style id also needs a matching entry in `MK_SHAPE`.

## Photos and designs

* **Product photos:** put images in an `images/` folder and set each product's `img` in the
  `PRODUCTS` list, e.g. `img:"images/tshirt.jpg"`.
* **Hero, map and other placeholders:** replace the dashed `<div class="ph">…</div>` boxes with
  `<img>` tags.
* **Ready-made designs:** the `DESIGNS` list is the single place to edit. Each design has a
  `code` (what customers quote, e.g. `XM-01`), a `name`, an `occ` (occasion key) and an `img`
  path such as `designs/XM-01.webp` (resize photos to about 720px wide first to keep the page fast). Add or remove lines freely. Occasion names and colours live
  in `OCCASIONS`.

## Uploaded designs and WhatsApp

A WhatsApp link cannot carry a file. By default the order message says the customer will
attach the file in the chat, and the page shows them a clear notice to do so.

If you want the message to carry a link instead, fill in `CONFIG.upload` with any browser
upload endpoint that returns JSON with a public URL (a Cloudinary unsigned upload preset is
the simplest, see the comment in the file). If the upload fails, the page falls back to the
"attach it in the chat" notice automatically.

## Hosting

Upload `index.html` (plus your `images/` and `designs/` folders) to any static host:
GitHub Pages, Netlify, Cloudflare Pages or normal shared hosting.
