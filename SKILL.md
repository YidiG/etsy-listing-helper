---
name: perlith-listing-helper
description: >-
  Generate complete, copy-paste-ready Etsy listing content for Perlith Jewelry Co (pearl
  jewelry): English title, 13 tags, materials, category, attributes, alt text, plus the
  description in English and French with the shop's fixed "Please Note", the price,
  quantity and SKU, and the shop's fixed shipping defaults. Use whenever the user provides
  pearl jewelry product info (pearl type, size in mm, metal, length, price, quantity, SKU,
  etc.) and/or product photos and wants Etsy listing info, listing copy, SEO tags, or
  anything related to publishing a product on Etsy. Also trigger when the user only sends
  product photos in a session where product info was given earlier — reuse that info.
  One image = one listing output.
---

# Perlith Listing Helper

Turn pearl jewelry specs + product photos into ready-to-paste Etsy listing content for **Perlith Jewelry Co**, in a **fixed format**: everything in **English**, with a **French version of the description only**, plus reasoning.

Forked from the general-purpose etsy-listing-helper (MIT) and specialised for this shop.

## Shop profile

- Shop: Perlith Jewelry Co. Tagline: natural pearl jewelry collections. Positioning: natural pearl jewelry reimagined with intentional design, "everyday luxury". Made in Canada.
- Current range (from the shop page): necklaces — layered/multi-strand, station, bow pendant, choker, long/sweater-length, bridal. Mostly freshwater pearls (white, cream, peach, light gold, pale pink), 4–9 mm; sterling silver, silver-tone, PT750 or gold-tone chains. Prices roughly $36–$147.
- Brand voice: polished, boutique, aspirational but accurate. Words like "timeless", "natural beauty", "everyday luxury" fit. Avoid hype and anything not supported by the spec.
- The user may add other jewelry types later (earrings, bracelets, rings). Same rules apply; pick the matching category.

Read [references/pearl-jewelry.md](references/pearl-jewelry.md) for pearl-specific vocabulary, keyword angles, accuracy rules, and the fixed shop defaults (section 8).

## Language rules

1. **English** — title, tags, materials, category/attributes and alt text are written in English only. These go into Etsy's main fields.
2. **Description** — written in **both English and French**. The English version goes into the main description field; the French version goes into Etsy's French translation field for the description (Shop Manager → Settings → Languages and currencies, if French is enabled). Write natural, marketing-quality French (not word-for-word), using the vocabulary in the pearl reference.
3. Do **not** produce French titles, tags, materials or alt text.

Never mix languages inside a copy-paste block. Annotations (rationale, notes) use the **language the user is chatting in**.

## Inputs you may receive

1. **Product base info**: pearl type, pearl size (mm), shape, color, metal/chain material, length(s), clasp metal, strand count, extras, care notes.
2. **Price, quantity and SKU** for the listing.
3. **One or more product photos**.

Rules:
- **N images → N complete listings**, numbered Listing 1, Listing 2…
- **Images only** → reuse the most recent product base info (and price, quantity, SKU only if the user said they apply) from this conversation; if none, ask for it.
- **Spec text only** → generate one listing; mark design details (style, shape, color) that need a photo as placeholders.
- Look carefully at each image: strand count, pearl size/shape/color impression, pendant or station detail, chain type, clasp metal if visible. These drive the keywords. Never describe the clasp's shape.
- Do not guess what you can't verify (pearl type, metal purity, length). If a key fact is missing, put `[CONFIRM: …]` in the output and list what to check.
- **Price, quantity and SKU are never invented.** Copy them exactly as the user gave them (keep the currency symbol/format). If any is missing, show `[CONFIRM: price]`, `[CONFIRM: quantity]` or `[CONFIRM: SKU]` and list it under "To confirm". If the user says to skip the SKU, write "Skipped".
- **Fixed shop defaults** (weight, packed size, delivery option, returns, gift box, no clasp shape) always apply and are never asked for — see section 8 of `references/pearl-jewelry.md`.
- **Uploading to Etsy (when asked to list it)**: always upload every file the user attached for the listing, photos AND videos, in the order sent, before saving the draft. Use Claude in Chrome: find the file input (never click the upload button) and call file_upload with the attachment paths. The built-in browser cannot upload. Etsy allows videos of max 10 seconds: trim longer ones to the first 10 s (ffmpeg -t 10). Try the original video first; if the upload tool refuses it, do not compress (Etsy accepts the original), send the file with SendUserFile and ask the user to add it under "Add videos". Save as draft only; never publish unless the user clearly says so.
- **Title check before entering it**: ~15 words or fewer, no repeated words, no subjective words (perfect, beautiful), ≤140 characters.
- **Variations**: most products have none, so do not include a Variations section or suggest variations. Only if the user says a product has variations, add a "Variations" section after "Price, Quantity, SKU & Shipping" with the options they gave.

## Reference files — read before writing

- [references/pearl-jewelry.md](references/pearl-jewelry.md) — **always read**. Pearl terms EN/FR, keyword angles, accuracy rules, the fixed Please Note text, the fixed listing defaults.
- [references/listing-fields.md](references/listing-fields.md) — **always read**. Consolidated per-field Etsy rules (ranking, title, tags, description, materials, category, attributes, variations).
- [references/etsy-categories.md](references/etsy-categories.md) — official category tree. Do NOT read whole; grep for the product type (e.g. "Necklaces", "Earrings") and choose the **deepest matching subcategory**. Use exact official names.
- `references/sources/` — original Etsy articles; consult only if the rulebook leaves a question open.

Validate every title ≤ 140 characters and every tag ≤ 20 characters before output.

## SEO principles (from Etsy Seller Handbook)

- Think like a buyer: keywords = **pearl type + size/color + product type + recipient/occasion + style**.
- Title: clear and scannable, ~15 words or fewer. Name the item and its key traits first (pearl type, size, metal, product type), no repeated words, no subjective fluff, no price/shipping info, never start with the shop name. Occasion words (bridal, wedding) only if they define the item. Never include clasp shape words.
- Tags: **13 tags in total** (not per language), all in English; multi-word natural phrases; mix high-traffic and long-tail; cover several brainstorming dimensions; no plural duplicates, no misspellings, don't repeat the category or attribute words; no clasp-shape tags.
- Description: essential info (pearl size, length, metal) at the top, top keywords in the first sentences (Google snippet), don't copy the title, never open with "Welcome to my shop".
- Category and attributes act like tags: deepest official category; fill every attribute that truly applies.
- First photo: clean background, no text overlays, 2000 px+ recommended.

## Fixed output format

Use this exact template for every listing. Each copy-paste block contains only one language.

---

```
## Listing {N} — {short name, e.g. "5-Layer Freshwater Pearl Necklace"}

### 1. Title (~15 words, ≤140 chars)
{English title}

### 2. Tags (13 total, English only, ≤20 chars each)
{tag1}, {tag2}, … {tag13}

### 3. Description — English
{• Opening hook with main keywords (first ~160 chars feed the Google snippet)}
{• ✨ THE DESIGN — what it looks like, strands/stations/pendant, color}
{• 📏 DETAILS — pearl type, pearl size, metal/chain, length(s), clasp metal if known}
{• 🎁 PERFECT FOR — occasions & recipients}
{• 🧼 CARE — only if the spec provides care info}
{• 📦 PACKAGE — 1 {product} in a gift box (always)}
{• PLEASE NOTE — the fixed text from references/pearl-jewelry.md, verbatim}

### 3b. Description — French
{same structure, natural French, with the fixed French Please Note verbatim}

### 4. Materials (≤13)
{e.g. Freshwater pearl, Sterling silver}

### 5. Category & Attributes
- Category: {deepest official Etsy category path}
- Primary color / Secondary color / Occasion / Holiday / other applicable attributes (only ones that truly apply)

### 6. Photo Alt Text (≤250 chars)
{English alt text}

### 7. Price, Quantity, SKU & Shipping
- Price: {as given by the user}
- Quantity: {as given by the user}
- SKU: {as given by the user, or "Skipped"}
- Item weight: 0.5 kg
- Packed size: 25 × 20 × 4 cm (L × W × H)
- Delivery option: default delivery setup
- Returns and exchanges: Returns only, 7 days

### 8. Rationale
{2–5 bullets in the conversation language: title order, tag balance, category/attribute choice}

### 9. To confirm
{only if something was missing or uncertain: list the [CONFIRM] items — otherwise omit}
```

---

Multiple listings: repeat the template per image, separated by `---`. Keep headings identical every time — the user batch-copies these into Etsy.

## Maintaining this skill

Generation reads exactly three files: `pearl-jewelry.md`, `listing-fields.md`, plus a grep of `etsy-categories.md`.

1. **Shop-specific facts** (voice, product range, fixed texts, vocabulary, fixed defaults) → `references/pearl-jewelry.md`.
2. **General Etsy rules** → merge into `references/listing-fields.md`, deduplicated; replace contradicted rules; originals go in `references/sources/` with URL and date.
3. **Don't add more always-read files.** Add a section to an existing one.
4. `etsy-categories.md` stays a pure lookup table.
5. SKILL.md stays workflow-only.

## Quality bar

- Count characters for every tag and title.
- Never invent product facts (pearl type, metal purity, length, origin, treatment) or price, quantity or SKU. Etsy prohibits misleading descriptions. Don't call a pearl "Akoya", "South Sea", or "Tahitian" unless the spec says so; don't write "solid gold" or "925" unless stated.
- The Please Note paragraph is fixed text — copy it exactly, don't rephrase.
- Remind the user once per session if a listed claim needs their confirmation.
