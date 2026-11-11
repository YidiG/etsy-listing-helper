# Pearl Jewelry Reference (Perlith Jewelry Co)

Shop-specific facts for the listing helper. Always read before writing.

## 1. Fixed "Please Note" text (copy verbatim, never rephrase)

**English:**

Please Note: As pearls are natural gemstones, each pearl may vary slightly in shape, size, color, surface, and luster. These natural variations are part of their beauty and make every necklace unique. Metal components may also undergo oxidation and discoloration as a result of use.

**French (draft translation — have a native French speaker confirm once, then keep it fixed):**

À noter : les perles étant des gemmes naturelles, chaque perle peut présenter de légères variations de forme, de taille, de couleur, de surface et de brillance. Ces variations naturelles font partie de leur beauté et rendent chaque collier unique. Les éléments métalliques peuvent également s'oxyder et se décolorer avec l'usage.

When the product is not a necklace (earrings, bracelet, ring), keep the text identical except "necklace" → the product word ("pair of earrings", "bracelet", "ring"; FR: "paire de boucles d'oreilles", "bracelet", "bague"). Flag this substitution in "To confirm".

## 2. Vocabulary EN ↔ FR

| English | French |
|---|---|
| freshwater pearl | perle d'eau douce |
| natural pearl jewelry | bijoux en perles naturelles |
| pearl necklace | collier de perles |
| choker | ras-de-cou / collier ras de cou |
| multi-strand / layered necklace | collier multi-rangs / collier superposé |
| long / sweater-length necklace | collier long / sautoir |
| station necklace | collier de perles espacées |
| pendant necklace | collier pendentif |
| bow pendant | pendentif nœud |
| fringe necklace | collier à franges |
| sterling silver | argent sterling |
| gold-tone / silver-tone | doré / argenté |
| dainty / minimalist | délicat / minimaliste |
| bridal / wedding jewelry | bijoux de mariée / bijoux de mariage |
| gift for her | cadeau pour elle |
| bridesmaid gift | cadeau demoiselle d'honneur |
| clasp / extender chain | fermoir / chaîne de rallonge |

Use natural French marketing phrasing; don't translate word-for-word. Have a native speaker review the first batch and add corrections here.

## 3. Keyword angles for pearl jewelry (brainstorm per product)

- **What it is:** pearl necklace, pearl choker, layered pearl necklace, pearl station necklace, bow pendant necklace
- **Pearl details:** freshwater pearl necklace, 6mm pearl necklace, white pearl, cream pearl, peach pearl, pink pearl, baroque pearl (only if the spec/photo shows irregular shapes)
- **Metal:** sterling silver pearl necklace, gold-tone chain (use only what the spec states)
- **Style:** dainty pearl necklace, minimalist pearl jewelry, classic pearl necklace, statement pearl necklace, coquette pearl necklace (only for bow/ribbon styles)
- **Recipient/occasion:** bridal pearl necklace, wedding jewelry, bridesmaid gift, mother's day gift, anniversary gift, gift for her, birthday gift
- **Solution:** everyday jewelry, something old/new wedding gift (only if appropriate)
- **Size/length:** 16 inch necklace, layered choker, long pearl necklace

Tags are max 20 characters including spaces. Fits: "freshwater pearl" (16), "pearl choker" (12), "bridal necklace" (15), "dainty pearl choker" (19). Too long: "silver pearl necklace" (21) → use "silver pearls" or "pearl necklace" plus a separate silver tag.

## 4. Accuracy rules (Etsy prohibits misleading listings)

- State pearl type exactly as the spec says: freshwater / Akoya / etc. Never upgrade it. Don't write "genuine" or "real" unless the spec supports it; "natural pearls" is the shop's own wording and can be used.
- Do not state metal purity (925, PT750, 14k) or plating/filled/solid unless the spec says so. PT750 appears in some existing titles — use it only when the spec for that product confirms it.
- Don't claim hypoallergenic, tarnish-proof, waterproof, or "heirloom quality" unless the spec says so.
- Describe pearl color only as the spec/photo shows; for mixed-color pieces, list the colors.
- If a listing's length, pearl size, or metal isn't in the spec or visible, use `[CONFIRM: …]`.
- Natural variation is already covered by the fixed Please Note — don't duplicate it elsewhere in the description.

## 5. Category notes (official tree)

- Necklaces → pick from: Beaded Necklaces, Choker Necklaces, Multi-Strand Necklaces, Pendant Necklaces, Lariat & Y Necklaces, Tassel Necklaces, Charm Necklaces.
  - Pearl strands usually → **Jewelry > Necklaces > Beaded Necklaces**; layered strands → **Multi-Strand Necklaces**; chokers → **Choker Necklaces**; bow/single-pearl pendants → **Pendant Necklaces**.
  - Always grep `etsy-categories.md` to confirm the exact path before output.
- Earrings: Stud Earrings, Dangle & Drop Earrings, Hoop Earrings, Threader Earrings, Cluster Earrings. Bracelets: Beaded Bracelets, Chain & Link Bracelets, Cuff Bracelets. Rings: Stackable Rings, Solitaire Rings, Statement Rings.
- Attributes commonly applicable: primary color (white/cream/pink/gold/silver as appropriate), occasion (wedding, anniversary, birthday, mother's day), plus any chain/strand attributes Etsy shows for the category.

## 6. Description voice

- Boutique, warm, precise. Open with the item, pearl type, and size in the first sentence.
- Preferred themes: timeless elegance, natural beauty, everyday luxury, intentional design, made in Canada (only if true for that product — confirm).
- End with a short brand-story sentence about intentional design, then the Please Note.
- Keep sentences short; use the emoji section bullets from the template.

## 7. Shop-level reminders (advise once per session, not per listing)

- Etsy's Handmade Policy: if production partners are used, disclose them; the shop's About text mentions pearls imported from China, Japan and Australia and pieces made in Canada — keep listing claims consistent with that.
- Make sure French translations are enabled in Shop Manager if you want the French blocks to be live.

## 8. Fixed listing defaults (apply to every listing; never ask for these)

- Item weight: 0.5 kg. Packed size: 25 cm × 20 cm × 4 cm (length × width × height).
- Delivery option: "default delivery setup" (the shop's existing calculated-shipping profile).
- Returns and exchanges: Returns only, 7 days.
- Gift box: every product comes in a gift box. In the PACKAGE line write "1 {product} in a gift box" (French: "dans un écrin cadeau").
- Clasp: never mention or describe the clasp shape (no "heart clasp" etc.) in the title, tags, description or alt text. Say "silver clasp" only if the user says the clasp is silver.
- Videos: always upload every video the user attached too, never skip one. Etsy accepts max 10 seconds (trim longer videos to the first 10 s with ffmpeg -t 10). Try file_upload on the original video first, to the video file input (the "Add videos" slot). Claude in Chrome's upload tool has refused videos before (even the original .mov, and compressed copies in other folders); if it refuses, do not compress, because Etsy accepts the original file. Send the file to the user with SendUserFile and ask them to add it by hand under "Add videos".
- Photos when listing on Etsy: always upload every photo and video the user attached to the listing's Photos section, in the order sent, before saving the draft. Use Claude in Chrome: find the photo file input (never click the upload button), then file_upload with the attachment paths. The built-in browser cannot upload; if Chrome is not connected, ask the user to open Chrome with the Claude extension and retry, and only then ask them to add photos by hand. Confirm thumbnails appear. Also paste the section 6 alt text into each photo if Etsy offers the field.
