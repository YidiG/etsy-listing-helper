# Perlith Listing Helper

A Claude Agent Skill for **Perlith Jewelry Co** (pearl jewelry). Give it product specs and/or photos; it returns copy-paste-ready Etsy listing content in English (with the description also in French): title, 13 tags, description, materials, category, attributes, alt text, price, quantity, SKU, rationale.

Forked from [silennsong/etsy-listing-helper](https://github.com/silennsong/etsy-listing-helper) (MIT) and specialised for pearl jewelry.

## What's different from the original

- Pearl-jewelry vocabulary, keyword angles and accuracy rules (`references/pearl-jewelry.md`)
- English listing, with a French version of the description only (for Etsy's translation field)
- Fixed "Please Note" paragraph, inserted verbatim in both description languages
- Price, quantity and SKU included in the output (never invented)
- `[CONFIRM: …]` markers instead of guessing pearl type, metal purity or length
- Brand voice from the shop profile

## Files

- `SKILL.md` — workflow, output template, rules
- `references/pearl-jewelry.md` — shop profile facts, EN/FR vocabulary, Please Note text, category notes
- `references/listing-fields.md` — consolidated Etsy field rules
- `references/etsy-categories.md` — official Etsy category tree (lookup only)
- `references/sources/` — original Etsy Seller Handbook articles

> Etsy content © Etsy, Inc., included for reference with attribution. Etsy is a trademark of Etsy, Inc. This project is not affiliated with or endorsed by Etsy.

## Install

Claude Code (personal skill):

```bash
git clone https://github.com/YidiG/etsy-listing-helper.git ~/.claude/skills/perlith-listing-helper
```

## Usage

Paste the product info plus a photo, e.g.:

```
Freshwater pearl, 7mm, white. Sterling silver bow pendant, 16" chain + 2" extender.
Price: $58. Quantity: 5. SKU: PL-BOW-001.
Please generate the Etsy listing info.
```

## License

MIT — see [LICENSE](LICENSE).
