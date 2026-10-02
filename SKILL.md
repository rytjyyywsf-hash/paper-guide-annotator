---
name: paper-guide-annotator
description: Create a Chinese guided-reading and annotated PDF for an academic paper when the user wants an AI first-pass explanation, structural roadmap, important-sentence highlighting, selective page-level notes, typeset mathematical explanations, or critical assessment. Preserve the source paper's text, formulas, figures, and images; add guidance without obscuring or rewriting the original. Do not invoke for a simple abstract-only summary or a full translation unless the user also wants the annotated-paper workflow.
---

# Paper Guide Annotator

Turn an academic-paper PDF into a faithful annotated copy that helps a first-time reader understand the argument before reading closely. Use the PDF skill for PDF inspection, construction, rendering, and visual verification.

## Establish the reading profile

Use the user's stated preferences. If they omit them, proceed with these defaults rather than blocking:

- Reader: graduate student new to this paper, but not necessarily new to the field.
- Annotation density: standard/selective.
- Purpose: understand the method and argument, then assess strengths and limitations.
- Language: Chinese, retaining important original technical terms at first mention.
- External context: add only when it materially improves understanding; cite it and keep it distinct from the paper's own claims.

If the source PDF is not available, ask for it. Ask about the reading profile only when a missing choice would substantially change the result.

For density choices and paper-type-specific review criteria, read [references/annotation-framework.md](references/annotation-framework.md).

## Preserve the paper

- Never overwrite the source PDF. Produce a clearly named annotated copy.
- Do not delete, rewrite, translate in place, crop, opaquely cover, or rearrange original text, formulas, tables, figures, captions, or images. Selective translucent PDF highlights are allowed as a separate annotation layer.
- Do not reduce the legibility or effective resolution of original pages.
- Prefer front/back guide pages plus non-obscuring margin notes. If margins cannot be added safely, insert commentary pages keyed to original pages or use unobtrusive PDF annotations. Never place commentary over paper content.
- Preserve the mapping to the original PDF page number and, when present, the paper's printed page number.
- Treat the original page as the source of truth. If extraction or OCR disagrees with the rendered page, inspect the page and avoid silently repairing the paper.

## Read before annotating

Inspect the complete paper, including abstract, section structure, equations, figures, tables, appendices, and references that affect the argument. Build an internal map of:

- the research question and motivation;
- the proposed answer, method, or thesis;
- the chain of reasoning or evidence;
- the role of each major section;
- the main results, assumptions, and scope conditions;
- the strongest contributions and most consequential limitations.

Do not infer the paper's conclusion from the abstract alone. Mark uncertain interpretations explicitly.

## Highlight important source sentences

Highlight the paper's most important original sentences by default. Use true PDF highlight annotations when text coordinates are reliable; otherwise use a carefully aligned translucent annotation only after visual verification. Do not alter the underlying text objects.

Highlight selectively. Many pages may need no highlight. Prioritize exact sentences or short clauses that express:

- the research question, thesis, or central claim;
- a definition or distinction required later;
- a key assumption or consequential method choice;
- a decisive result or the authors' interpretation of it;
- an explicit caveat, limitation, or scope condition.

Avoid highlighting whole paragraphs, routine transitions, literature-review boilerplate, or sentences whose importance is already obvious from a heading. When a sentence is important for a non-obvious reason, connect its highlight to a short margin note.

Use a restrained, consistent palette and include its legend in the front guide:

- yellow: central claim or definition;
- blue: method or key assumption;
- green: main result or supporting evidence;
- orange: caveat, limitation, or scope condition.

Keep highlights translucent enough that punctuation, subscripts, diacritics, and low-contrast text remain legible. Do not use color alone to convey meaning: the legend and any linked note must name the category.

## Compose the front guide

Place a concise Chinese guide before the untouched paper pages. Adapt its length to the paper and include:

- an accessible AI-written abstract, clearly labeled as a guide rather than the paper's original abstract;
- the problem, why it matters, and the paper's answer in plain language;
- the method or evidence at a useful level of detail;
- the main contributions and findings;
- a section-by-section roadmap explaining how the argument develops;
- prerequisites, a compact glossary, and reading advice where useful;
- a short list of questions to carry into the first reading.

Avoid repeating the same material under multiple headings. Preserve technical precision while explaining jargon.

## Add selective annotations

Annotate load-bearing or genuinely difficult points rather than translating every sentence. Prioritize:

- transitions that reveal the paper's logic;
- concepts, notation, formulas, and omitted reasoning steps;
- experimental design, identification strategy, data choices, or proof strategy;
- figures and tables whose interpretation matters to the conclusion;
- assumptions, boundary conditions, and claims that are easy to overread;
- connections to earlier or later parts of the paper;
- places where the evidence is weaker or an alternative interpretation is plausible.

Anchor every note to an exact page and, where possible, a paragraph, equation, figure, table, or section. Use short category labels such as `脉络`, `概念`, `公式`, `方法`, `图表`, `证据`, `提醒`, or `质疑` when they improve scanning.

Keep three voices visibly distinct:

- **论文主张**: what the authors explicitly state or demonstrate;
- **理解辅助**: background, intuition, or reconstructed reasoning;
- **批判性评价**: the annotator's assessment, alternative explanation, or open question.

Never present an inference as an author claim. Retain exact mathematical symbols and define them consistently.

## Typeset mathematical content

Render every mathematical expression added by the annotator as finished typeset math. LaTeX may be used as the authoring source, but the delivered PDF must not expose raw delimiters or commands such as `$...$`, `\(...\)`, `\frac`, `\sum`, or `\mathbb` unless the note is explicitly discussing LaTeX syntax.

- Use inline math for short symbols and relations, and display math for derivations or multi-part equations.
- Prefer vector output or embedded math fonts so formulas remain sharp when zoomed or printed; do not use screenshots of formulas.
- Preserve the paper's notation exactly, including accents, bold symbols, superscripts, subscripts, Greek letters, and equation numbering.
- Align multi-line derivations clearly and explain what each transformation contributes instead of merely restating the expression.
- If a formula cannot be rendered reliably, refer to the original equation number and explain it in prose; report the limitation rather than shipping broken or raw LaTeX.

## Compose the closing assessment

After the paper pages, add a critical synthesis covering the material that is relevant to this paper:

- the most important contribution and what is genuinely new;
- key assumptions and where conclusions apply;
- whether the evidence supports the stated claims;
- limitations acknowledged by the authors versus limitations inferred in this review;
- threats to validity, robustness gaps, possible biases, or missing comparisons;
- unresolved questions and promising follow-up reading or research;
- a compact set of questions for a second, closer reading.

Be fair and specific. Tie criticism to a page, result, assumption, or design choice instead of making generic complaints.

## Verify the deliverable

Before delivery:

- render the final PDF and inspect the guide, annotated pages, dense equations, figures, and closing pages;
- confirm that notes do not overlap, clip, or obscure original content;
- confirm that every highlight aligns tightly with the intended sentence, remains readable, and matches the color legend;
- spot-check original-page regions against the source rendering for unchanged appearance and legibility;
- verify page anchors and the mapping between annotated and original page numbers;
- inspect mathematical annotations at normal size and high zoom; reject raw LaTeX, missing glyphs, rasterized screenshots, broken baselines, or clipped equations;
- check that Chinese text and mathematical symbols render correctly;
- report any pages that could not be reliably extracted or interpreted.

Deliver the annotated PDF and a brief note stating the chosen reader level, annotation density, and any material limitations. Keep intermediate OCR, images, and analysis files out of the deliverables unless the user asks for them.
