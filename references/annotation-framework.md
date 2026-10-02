# Annotation and Review Framework

Read this reference when choosing annotation density or adapting the critique to a paper type.

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
