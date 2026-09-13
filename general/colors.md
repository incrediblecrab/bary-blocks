# Apple HIG: Color System

## How Apple's Color System Works

Apple's design guidelines treat color as **semantic, not decorative** — each color is defined by its *purpose* (a primary action, a secondary text label, a separator) rather than by a fixed value. The purpose stays constant while the actual color shifts underneath it depending on context.

Every color in the system carries **four variants**, built for two independent axes of context:

- **Light mode** and **Dark mode** — the color adjusts so it reads correctly against a light or dark background
- **Default contrast** and **Increased contrast** — a higher-contrast pairing kicks in for accessibility, pulling values further apart so elements stay distinguishable

This is the core idea worth borrowing for a static site palette: don't pick one color per name — pick a **light/dark pair**, and ideally a **higher-contrast fallback** for each, so the palette can adapt to a visitor's OS-level appearance and accessibility settings rather than staying fixed.

Other guiding principles:

- **Consistency over decoration.** A color should mean one thing throughout the interface — don't reuse the same hue for an interactive element in one place and static, non-clickable text elsewhere.
- **Never rely on color alone.** Color-coded meaning (status, state, category) should always be backed up by text, iconography, or shape, since color blindness and low vision affect how colors are perceived.
- **Design for environment.** Colors read differently in bright sunlight vs. a dark room, on wide-gamut vs. standard displays, and even across cultures — red reads as "danger" in some contexts and "prosperity" in others, so don't assume a color's meaning travels universally.
- **Keep values as tokens, not one-offs.** Because a color's actual RGB value can shift over time (a redesign, a new theme, a contrast tier), it's more durable to reference a *named* variable — like `color-accent` or `text-secondary` — than to hardcode a hex code wherever a color is used.

---

## Color Theory Basics

A few fundamentals underlie any palette, digital or print:

- **Hue, saturation, brightness (HSB).** Hue is the color itself (red, blue, green), saturation is its intensity or purity, and brightness (or "value") is how light or dark it is. Two colors can share a hue but feel completely different if their saturation and brightness differ.
- **Color relationships.** Complementary colors (opposite each other on the color wheel) create contrast and visual energy; analogous colors (next to each other) create harmony; a triadic scheme (evenly spaced) balances contrast with cohesion. Apple's system palette works because its hues are evenly distributed around the wheel — each is easy to tell apart from its neighbors at a glance.
- **Contrast is a relationship, not a property.** A color isn't "accessible" or "readable" on its own — it's accessible *against* a specific background. This is why every Apple system color ships as a pair (or set) tuned for different backgrounds and contrast needs, rather than a single fixed value.
- **60-30-10 rule.** A common practical heuristic: ~60% of a layout in a dominant/neutral color, ~30% in a secondary color, ~10% in an accent — which maps well to the "primary / secondary / accent" naming pattern common in web palettes.

## Digital Color vs. Physical Color

Digital and physical (printed) color are fundamentally different systems, and a palette that looks right on screen can shift unexpectedly in print:

- **RGB (screen) is additive.** Red, green, and blue light are combined; mixing all three at full intensity produces white. This is how monitors, phones, and websites render color — light emitted directly into your eyes.
- **CMYK (print) is subtractive.** Cyan, magenta, yellow, and black ink absorb (subtract) light from the white paper underneath; mixing all of them approximates black, not white. Printers convert RGB files to CMYK before running them, and colors — especially vivid blues, greens, and neons — often look duller and less saturated once converted, since CMYK physically covers a smaller range of visible color.
- **Because of this, a color designed only in RGB may print flat or shift hue.** If a palette will ever end up on a physical product (business cards, packaging, merch), it's worth checking a CMYK preview or soft-proofing before finalizing — what pops on a screen doesn't always survive the switch to ink.

## Color Gamut & Color Space (sRGB vs. Display P3 / Adobe RGB)

A **gamut** is the full range of colors a device or format is capable of displaying or reproducing — not every device can show every visible color, so gamuts define the boundaries of what's possible.

- **sRGB** is the long-standing default color space for the web. Most monitors, browsers, and image formats assume sRGB unless told otherwise, which makes it the safest baseline for a website — colors will render consistently (or close to it) across the widest range of devices.
- **Display P3** (Apple's preferred wide-gamut space) covers a noticeably larger range than sRGB, especially in reds and greens, producing more vivid, saturated colors on compatible displays (most iPhones, iPads, and Macs since ~2016). A color picked in P3 can look correct and vivid on a P3 screen but appear slightly washed out or shifted on an sRGB-only screen.
- **Adobe RGB** is a separate wide-gamut space used heavily in photography and print workflows — it covers more of the green/cyan range than sRGB, but isn't the same shape of gamut as P3, so a color converted between the two isn't a 1:1 match.
- **Practical implication for a web palette:** define colors in sRGB as the baseline (this is what CSS hex/rgb() values assume), and only reach for `color(display-p3 ...)` in CSS if you specifically want more vivid colors *and* are comfortable with them rendering differently (more muted) on non-P3 screens. Don't assume a color picked by eye on a modern Apple display will look identical on an average Windows monitor — always check the same palette on both a P3 and a standard-gamut screen before shipping it.

---

## Named System Colors

| Name | Default (Light) | Default (Dark) | Increased Contrast (Light) | Increased Contrast (Dark) |
|------|------------------|-----------------|------------------------------|------------------------------|
| Red | R255 G56 B60 | R255 G66 B69 | R233 G21 B45 | R255 G97 B101 |
| Orange | R255 G141 B40 | R255 G146 B48 | R197 G83 B0 | R255 G160 B86 |
| Yellow | R255 G204 B0 | R255 G214 B0 | R161 G106 B0 | R254 G223 B67 |
| Green | R52 G199 B89 | R48 G209 B88 | R0 G137 B50 | R74 G217 B104 |
| Mint | R0 G200 B179 | R0 G218 B195 | R0 G133 B117 | R84 G223 B203 |
| Teal | R0 G195 B208 | R0 G210 B224 | R0 G129 B152 | R59 G221 B236 |
| Cyan | R0 G192 B232 | R60 G211 B254 | R0 G126 B174 | R109 G217 B255 |
| Blue | R0 G136 B255 | R0 G145 B255 | R30 G110 B244 | R92 G184 B255 |
| Indigo | R97 G85 B245 | R109 G124 B255 | R86 G74 B222 | R167 G170 B255 |
| Purple | R203 G48 B224 | R219 G52 B242 | R176 G47 B194 | R234 G141 B255 |
| Pink | R255 G45 B85 | R255 G55 B95 | R231 G18 B77 | R255 G138 B196 |
| Brown | R172 G127 B94 | R183 G138 B102 | R149 G109 B81 | R219 G166 B121 |

---

## Neutral / Gray Scale

| Name | Default (Light) | Default (Dark) | Increased Contrast (Light) | Increased Contrast (Dark) |
|------|------------------|-----------------|------------------------------|------------------------------|
| Gray | R142 G142 B147 | R142 G142 B147 | R108 G108 B112 | R174 G174 B178 |
| Gray (2) | R174 G174 B178 | R99 G99 B102 | R142 G142 B147 | R124 G124 B128 |
| Gray (3) | R199 G199 B204 | R72 G72 B74 | R174 G174 B178 | R84 G84 B86 |
| Gray (4) | R209 G209 B214 | R58 G58 B60 | R188 G188 B192 | R68 G68 B70 |
| Gray (5) | R229 G229 B234 | R44 G44 B46 | R216 G216 B220 | R54 G54 B56 |
| Gray (6) | R242 G242 B247 | R28 G28 B30 | R235 G235 B240 | R36 G36 B38 |

---

## Quick Reference: Semantic Roles Worth Naming as Variables

| Purpose | Example use |
|---------|--------------|
| Primary text | Main body copy, headings |
| Secondary text | Subheadings, supporting copy |
| Tertiary text | De-emphasized captions, metadata |
| Quaternary text | Watermark-level or barely-visible text |
| Placeholder text | Empty input/field hint text |
| Separator (translucent) | Dividers where underlying content should stay visible |
| Opaque separator | Dividers where underlying content should be fully hidden |
| Link | Clickable inline text |

---

*Source: [Apple Human Interface Guidelines — Color](https://developer.apple.com/design/human-interface-guidelines/color) (last updated December 16, 2025)*