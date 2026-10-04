# Annotation and Review Framework

Read this reference before designing the annotated pages. It defines the default right-sidebar system, figure/table analysis, typography, density decisions, paper-type critique, and visual acceptance checks.

## Annotation density

### 精简

Use for rapid orientation. Highlight only the research question or thesis, central method, decisive results, and the most consequential limitation. Add notes only for major logical transitions or obstacles. Favor a strong front guide over numerous page notes.

### 标准

Use by default. Highlight load-bearing claims, assumptions, results, and explicit caveats. Explain the main conceptual and methodological obstacles, important figures and formulas, and the argument's transitions. A highlight or note should earn its place by preventing a likely misunderstanding or making later sections easier to follow.

### 深入

Use when the user wants replication, close study, or seminar preparation. Highlight additional definitions, design decisions, and result interpretations that matter for reconstruction. Reconstruct important derivations and design choices, explain most consequential figures and tables, trace assumptions through results, and add more comparisons or robustness questions. Deep does not mean highlighting everything or providing a line-by-line translation.

## Reader calibration

- **入门读者**: explain field-specific motivation, common baselines, and notation; use intuition before formal detail.
- **研究生读者**: assume general research literacy; explain paper-specific machinery and hidden inferential steps.
- **同领域研究者**: compress background and emphasize novelty, technical assumptions, comparisons, robustness, and reusable details.

## Page planning and geometry

Plan every original page before composing the PDF. Record:

- the page's section role and contribution to the paper's argument;
- a one-to-three-sentence `本页概括`;
- whether a figure or table is important enough for `图表解读`;
- a small set of exact highlight/note anchors, ranked by value;
- added formulas that need mathematical typesetting;
- expected sidebar density and the first notes to remove if space is tight.

Use the plan as a final completeness manifest, not merely as drafting notes.

For an original page of width `W` and height `H`:

- keep the original page region at `W x H`, at its original coordinates and scale;
- extend the output canvas on the right by about `0.40 W` to `0.45 W` by default;
- adapt the exact width to aspect ratio, language, and content, but keep it visibly narrower than the source page rather than creating a second equal-width page;
- place a light vertical divider at the boundary, with enough inner padding that neither source content nor sidebar text crowds it;
- preserve vector text and graphics in the source region; do not rasterize the paper to simplify composition;
- render the sidebar, highlights, anchors, and guidance into static page content. The final PDF must contain no interactive annotation objects.

If pages have varying dimensions, size each output page from its corresponding source page instead of globally scaling the paper. Guide and closing pages may use the expanded output size for visual continuity.

## Sidebar hierarchy and module responsibilities

Lay out the right sidebar from top to bottom in this order:

1. **Page title and section role** - a compact locator and a functional label, not a rewritten section heading.
2. **本页概括** - required on every original page.
3. **图表解读** - only on selected important figure/table pages.
4. **Detailed notes** - selective numbered notes connected to exact anchors.
5. **Footer legend** - a compact reminder of semantic categories and the static/non-interactive nature of the annotations.

### 本页概括

Use one to three sentences to say both what the page contains and why that page matters in the paper's overall progression. Keep it when there are no detailed notes. Do not:

- restate only the printed section title;
- list every local detail;
- repeat the same explanation in the detailed notes;
- claim that a page proves more than it actually establishes.

Give this module a restrained light background, such as a cool pale tint, with sufficient contrast for text.

### 图表解读

Select visuals by argumentative importance rather than by count. Prefer:

- a core method, pipeline, or decision process;
- a result that directly supports a principal empirical claim;
- a reliability, performance, cost, or hyperparameter tradeoff;
- an important ablation or cross-dataset comparison;
- a table that determines metric definitions, experimental interpretation, or method configuration.

The module should answer, as compactly as the evidence permits:

1. **Observation:** What is directly visible in the figure or table?
2. **Support:** Which paper claim or interpretation does that pattern support?
3. **Limits:** What does the visual not establish, or what weakens the inference?

Check and mention consequential details such as missing error bars, number of random splits or runs, sample size, axis scale or truncation, metric definition, reliance on a human or model judge, selection effects, and performance-cost tradeoffs. For multi-panel pages, one compact module may explain the relationship among panels instead of treating them independently.

Distinguish qualitative examples that clarify labels, tasks, or evaluation protocols from quantitative evidence of effectiveness. A visually persuasive example is not automatically representative evidence. Describe associations as associations unless the design supports a causal claim.

Do not add a `图表解读` module merely to paraphrase a caption. Give it a light background distinct from but coordinated with `本页概括`, such as a pale green tint.

### Detailed notes and anchors

Use numbered anchors only for passages that affect understanding, argument structure, evidence, assumptions, or limitations. Keep each note focused on one job and label it semantically, for example:

- `主张 / 定义`;
- `方法 / 假设`;
- `结果 / 证据`;
- `限制 / 边界`.

Also identify the voice as `论文主张`, `理解辅助`, or `批判性评价` when ambiguity is possible. The label must carry the meaning even in grayscale; color is secondary. Notes should complement rather than restate `本页概括` or `图表解读`.

## Typography, spacing, and math

- Guide-page body: about 12.5-13.5 pt with generous leading.
- Sidebar body: about 10-10.5 pt; avoid going below 9.5 pt.
- Sidebar body leading: about 1.5-1.6 times the font size.
- Use visibly distinct sizes, weights, spacing, and rules for page titles, module labels, body text, note metadata, and the footer legend.
- Maintain real space between modules and paragraphs. Do not reduce margins, line spacing, or type size until the hierarchy collapses.

When content overflows, resolve it in this order:

1. preserve `本页概括`;
2. preserve `图表解读` for a selected important visual;
3. shorten repetitive phrasing;
4. remove the lowest-priority detailed notes;
5. simplify a derivation or refer to the original equation number;
6. only then make a small typography adjustment while remaining within the recommended readable range.

Do not add commentary merely to fill unused sidebar space.

All added mathematics, including inline variables, must use actual mathematical composition. Use native math fonts or vector output with conventional fraction bars, limits, scripts, brackets, accents, expectations, Greek letters, and set symbols. Check that display equations fit the sidebar without arbitrary scaling; break a derivation at meaningful mathematical boundaries or refer to an original equation if the expression cannot remain readable. Never expose authoring strings such as `\frac{n+1}{n}`, `n+1/n`, or `E[A]` to the reader.

## Review focus by paper type

### Empirical or causal paper

Check data provenance, sampling, measurement, identification assumptions, controls, leakage, multiple testing, uncertainty, robustness, subgroup claims, and the gap between statistical and practical significance.

### Machine-learning or computational paper

Check dataset representativeness, train/test contamination, baselines, ablations, hyperparameter and compute fairness, variance across runs, metric choice, reproducibility, generalization, and whether gains support the breadth of the claims.

### Theoretical or mathematical paper

Check definitions, theorem assumptions, proof dependencies, edge cases, necessity versus convenience of assumptions, relation between formal results and motivating claims, and whether examples demonstrate the claimed scope.

### Experimental science paper

Check controls, randomization and blinding where applicable, sample size, measurement validity, protocol deviations, error bars, replication, alternative mechanisms, and whether figures support the textual interpretation.

### Review, survey, or position paper

Check search and inclusion logic, taxonomy quality, coverage, selection bias, treatment of conflicting evidence, distinction between consensus and advocacy, and whether conclusions follow from the reviewed literature.

### Qualitative or humanities paper

Check corpus or case selection, interpretive framework, evidentiary traceability, counterexamples, historical or contextual scope, alternative readings, and how clearly the paper distinguishes evidence from interpretation.

## Note quality test

Keep a proposed note only if it does at least one of the following:

- reveals the role of a passage in the argument;
- resolves a likely conceptual or technical obstacle;
- makes a figure, table, formula, or method interpretable;
- exposes an assumption or scope condition;
- identifies a specific evidentiary weakness or alternative explanation;
- connects distant parts of the paper in a way that aids understanding.

Remove notes that merely paraphrase an already clear sentence, repeat the front guide, or offer generic praise or criticism.

## Mathematical note quality

A mathematical annotation should normally do more than reproduce an equation. It should clarify at least one of these:

- what each non-obvious symbol represents;
- the intuition behind the expression;
- the assumptions needed for the step;
- an omitted intermediate step;
- the consequence of the equation for the argument;
- how the expression connects to a result, figure, or later derivation.

Typeset all added expressions in the final PDF. Keep raw LaTeX only in intermediate authoring files, never in the reader-facing annotation.

## Visual acceptance checklist

Do not treat successful generation, text extraction, heading counts, or other script assertions as proof of layout quality. Complete both structural and visual checks.

### Structural checks

- Match every source page to exactly one annotated paper page, in order.
- Confirm that the source region retains all text, equations, figures, tables, captions, footnotes, and images at the original scale and effective resolution.
- Enumerate PDF annotation objects and require none. Static highlights and sidebar content must be part of the rendered page content.
- Use the page plan to confirm `本页概括` on every original page and `图表解读` on every selected important figure/table page.
- Verify original-page and printed-page labels, numbered anchors, and semantic labels.

### Full-document visual pass

Render every final page to an image and create one or more legible contact sheets. Inspect the entire sequence for:

- clipped, overlapping, or out-of-bounds text;
- unreadably small or overly compressed type;
- inconsistent sidebar widths, dividers, padding, or module ordering;
- missing summaries, broken anchor relationships, or isolated headings;
- obscured source content or badly aligned highlight rectangles;
- missing glyphs, fallback boxes, or incorrect Chinese/math fonts;
- excessive empty space caused by avoidable layout errors rather than intentional restraint.

### High-resolution spot checks

Inspect at high resolution and useful zoom:

- the first guide pages, including any formula-bearing overview;
- every page with added formulas, especially formula-dense pages;
- the densest sidebars and longest notes;
- each page selected for important figure/table interpretation, including multi-panel plots and small labels;
- representative source pages containing dense equations, images, and tables;
- closing assessment pages.

For mathematics, check the rendered appearance rather than only extracted text: fraction structure, superscript/subscript placement, operator limits, bracket sizing, baselines, glyph completeness, clipping, and vector sharpness. Reject raw LaTeX, linear plain-text approximations, or raster formula screenshots.

For figures and tables, verify that `图表解读` refers to the correct visual and that its observation, supported conclusion, and limitation remain distinguishable. Recheck axes, legends, sample sizes, uncertainty displays, run/split counts, metric definitions, judge dependence, and cost-performance statements against the source page.
