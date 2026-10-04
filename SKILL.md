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

For sidebar composition, figure/table analysis, typography, density choices, paper-type-specific review criteria, and the visual QA checklist, read [references/annotation-framework.md](references/annotation-framework.md) before designing the output.

## Preserve the paper

- Never overwrite the source PDF. Produce a clearly named annotated copy.
- Do not delete, rewrite, translate in place, crop, opaquely cover, or rearrange original text, formulas, tables, figures, captions, or images.
- Preserve every original paper page at its original dimensions and effective resolution. Do not shrink, rasterize, or reflow the original content region to make room for commentary.
- For every original paper page, expand the canvas to the right and add a persistent narrow sidebar. Use roughly 40%-45% of the original page width by default, adapting to the page dimensions without creating an equally wide second page. Separate the source page and sidebar with a light, clear rule.
- Make all reading guidance directly visible in the page content. Do not use PDF comments, sticky notes, popups, hidden page-level notes, or any other interactive `/Annot` object. Do not substitute separate page-commentary sheets for the persistent sidebar.
- Keep front guide pages and a closing assessment when useful, but never place commentary over the paper content. If the source page cannot be safely embedded at full size beside a readable sidebar, report the constraint instead of covering or shrinking the paper or hiding notes interactively.
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

Before layout, make a page plan for every original page: its role in the paper, a one-to-three-sentence page summary, whether it contains a decision-critical figure or table, the few worthwhile annotation anchors, and any added mathematical expressions that require typesetting. This plan is also the completeness checklist for the final PDF.

## Highlight important source sentences

Highlight the paper's most important original sentences by default. Render highlights as static translucent visual content aligned to reliable text coordinates; do not create interactive PDF highlight annotations. Preserve the underlying text objects and verify alignment on the rendered page.

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

Use a readable guide-page body size of about 12.5-13.5 pt with generous leading. Do not solve overflow by compressing prose below a comfortable reading size; edit or repaginate the guide instead.

## Build each original-paper page

Use the same visible hierarchy on every paper page:

1. page title and section role;
2. `本页概括`;
3. `图表解读`, only when the page contains a selected important figure or table;
4. selective detailed notes tied to numbered anchors;
5. a compact footer legend.

Every original page must have `本页概括`, even when it has no other note. In one to three sentences, explain what the page contributes to the whole paper and what it mainly does. Do not merely repeat a heading or duplicate the detailed notes.

Add a distinct `图表解读` module for figures and tables that carry the method, central empirical conclusions, reliability/performance/cost tradeoffs, important ablations or cross-dataset comparisons, or definitions that govern experimental interpretation. Explain the direct observation, the conclusion it supports, and the limits of that inference. Do not mechanically annotate every visual, paraphrase only the caption, or turn correlation into causation.

Keep `本页概括`, `图表解读`, and detailed notes visually and rhetorically separate. Use different but coordinated light backgrounds for the first two modules. When space is tight, preserve the summary and important figure/table analysis, then remove or shorten lower-value notes rather than compressing the typography.

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

Never present an inference as an author claim. Use explicit semantic labels such as `主张`, `方法`, `证据`, and `限制`; color may reinforce but never replace those labels. Retain exact mathematical symbols and define them consistently.

Use about 10-10.5 pt for sidebar body text and avoid going below 9.5 pt. Set body leading to about 1.5-1.6 times the font size, and maintain clear spacing among headings, labels, paragraphs, modules, and footer. Do not fill empty space with low-value commentary.

## Typeset mathematical content

Render every mathematical expression added by the annotator throughout guide pages, summaries, figure/table analysis, detailed notes, and closing pages as finished typeset math. LaTeX may be used as the authoring source, but the delivered PDF must not expose raw delimiters, commands, or linear stand-ins such as `$...$`, `\(...\)`, `\frac{n+1}{n}`, `n+1/n`, or `E[A]` unless the note is explicitly discussing source syntax.

- Use inline math for short symbols and relations, and display math for derivations or multi-part equations.
- Require vector output or embedded math fonts so fractions, roots, sums, expectations, superscripts, subscripts, Greek letters, and set symbols remain sharp and conventionally positioned when zoomed or printed. Do not use screenshots of formulas.
- Typeset ordinary inline variables with mathematical fonts and proper scripts, not approximated Unicode or plain-text substitutes.
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

- verify that every source page is present once, in order, and that its text, formulas, figures, tables, and images remain complete, legible, and at the original scale;
- enumerate the PDF's annotation objects and require zero interactive annotations, including highlight, text, sticky-note, popup, and page-level comment annotations;
- confirm that every original page has a visible `本页概括`, and that every figure/table selected in the page plan has a visible `图表解读`;
- render the entire final PDF to page images and a contact sheet. Inspect all pages for clipping, overlap, overflow, unintended blank regions, unreadably small type, and inconsistent spacing;
- perform high-resolution checks of the first guide pages, formula-dense pages, the densest sidebars, and selected important figure/table pages. Do not accept the result based only on successful scripts, text extraction, or string assertions;
- confirm that notes never obscure original content and that each static highlight aligns tightly with its intended sentence, remains readable, and matches the semantic legend;
- compare the original-paper region against source rendering on representative pages and verify the full page mapping; account only for intentional static highlight overlays;
- inspect every page containing added mathematics at normal size and high zoom; reject raw LaTeX, linear plain-text formulas, missing glyphs, rasterized equations, broken baselines, or clipping;
- check that Chinese text and mathematical symbols render correctly, and report any page that could not be reliably extracted, interpreted, or preserved.

Deliver the annotated PDF and a brief note stating the chosen reader level, annotation density, and any material limitations. Keep intermediate OCR, images, and analysis files out of the deliverables unless the user asks for them.
