# Colors

**For LLM:** Use when choosing, auditing or documenting a color palette. Apple's system is the reference model: a color is defined by its purpose rather than by a fixed value, and every purpose ships variants for light and dark appearance and for increased contrast. Apply the reasoning to any palette. Apply the listed values only where Apple's platform conventions are actually in scope.

## How Apple's system works

Apple's guidelines treat color as semantic rather than decorative. Each color is defined by its purpose — a primary action, a secondary text label, a separator — and the purpose stays constant while the value underneath it shifts with context.

Every color carries four variants across two independent axes. Light and dark mode adjust the color so it reads correctly against the background. Default and increased contrast pull values further apart so elements stay distinguishable when a reader has raised the contrast setting.

The idea worth carrying into any palette is that a name should not resolve to one value. Pick a light and dark pair, and a higher-contrast fallback for each, so the palette adapts to appearance and accessibility settings instead of staying fixed.

A color should mean one thing throughout an interface. Do not reuse a hue for an interactive element in one place and static text in another.

Never rely on color alone. Meaning carried by color — status, state, category — needs text, iconography or shape behind it, because color blindness and low vision change how the color is perceived.

Design for the environment. Colors read differently in bright sunlight than in a dark room, and differently on wide-gamut than on standard displays. Define values in sRGB as the baseline, since CSS hex and `rgb()` assume it, and reach for `color(display-p3 ...)` only where the added vividness is worth a more muted rendering elsewhere. Meaning does not travel universally either; red reads as danger in some contexts and prosperity in others.

Keep values as tokens. A color's value can change with a redesign, a new theme or a contrast tier, so referencing a named variable such as `color-accent` or `text-secondary` is more durable than hardcoding a hex value at each use.

## Color theory basics

Hue, saturation and brightness are the three axes. Hue is the color itself, saturation is its intensity, and brightness is how light or dark it is. Two colors sharing a hue can feel entirely different if saturation and brightness differ.

Relationships on the color wheel do predictable work. Complementary colors sit opposite each other and create contrast; analogous colors sit adjacent and create harmony; a triadic scheme spaces three colors evenly and balances contrast against cohesion. Apple's palette works partly because its hues are distributed evenly enough that neighbors stay distinguishable at a glance.

Contrast is a relationship, not a property. A color is not accessible on its own, only against a specific background. That is why each system color ships as a set tuned for different backgrounds and contrast needs rather than as a single value.

The 60-30-10 heuristic is a practical starting point: roughly 60 percent of a layout in a dominant or neutral color, 30 percent in a secondary, 10 percent in an accent. It maps onto the primary, secondary and accent naming common in web palettes.

## Palettes

### Named system colors

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

### Neutral and gray scale

| Name | Default (Light) | Default (Dark) | Increased Contrast (Light) | Increased Contrast (Dark) |
|------|------------------|-----------------|------------------------------|------------------------------|
| Gray | R142 G142 B147 | R142 G142 B147 | R108 G108 B112 | R174 G174 B178 |
| Gray (2) | R174 G174 B178 | R99 G99 B102 | R142 G142 B147 | R124 G124 B128 |
| Gray (3) | R199 G199 B204 | R72 G72 B74 | R174 G174 B178 | R84 G84 B86 |
| Gray (4) | R209 G209 B214 | R58 G58 B60 | R188 G188 B192 | R68 G68 B70 |
| Gray (5) | R229 G229 B234 | R44 G44 B46 | R216 G216 B220 | R54 G54 B56 |
| Gray (6) | R242 G242 B247 | R28 G28 B30 | R235 G235 B240 | R36 G36 B38 |

### Semantic roles worth naming

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
