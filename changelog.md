# Changelog

Updates to the instruction blocks. Each entry is dated the day the change
landed and grouped by the directory it touched.

## September 13, 2026

### general/

- Added `!think-LEGO.md`: architecture and construction, working from first
  principles to the structure they force, then to its second-order effects.
  Covers modularity, interfaces, boundaries, redundancy, scale, failure paths,
  trust boundaries, single definition per value, and code that reads in the
  order it runs.
- Every block now opens its scope line with `**For LLM:**`, naming the audience
  that actually consumes the file.
- Removed the registry metadata that used to open each file, so a block pasted
  into a model carries instructions and nothing else.

### stop-the-slop/

- The shared contract now appears in `accuracy.md`, `anti-slop.md`,
  `formatting.md` and `voice.md`. Previously only `!editorial.md` carried it,
  which made the four modules weaker when pasted on their own.
- Removed claims the modules could not support, including attributed authorship
  of the detection lists and an overstated rule about semicolons.
- Dated the vocabulary inventory to September 2026 and matched word families
  rather than exact strings.
- Every block opens its scope line with `**For LLM:**`.
- Removed the registry metadata that used to open each file.

### examples/

- `academia/` moved here as `academic-proofs/`. The three blocks are unchanged
  and still carry the shared contract; only their shelving changed.
- Tightened `domains/` guidance across fiction, general, legal, marketing,
  medical, non-fiction, press and technical, and across all five
  `domains/user-interface/` surfaces.
- Corrected `education-levels/`: possessive bounds, irregular plurals, an
  assignment-anchored test in place of a credential-anchored one, and removal
  of a claim the source curriculum does not support.
- Every block opens its scope line with `**For LLM:**`.
- Removed the registry metadata that used to open each file.
