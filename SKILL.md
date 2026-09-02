---
name: clean-data-presentation
description: Audit, redesign, or create data-bearing artifacts so evidence is truthful, comparison-ready, information-dense, and visually clear. Use for charts, tables, dashboards, reports, slides, spreadsheets, documents, and web views that present quantitative or mixed evidence; do not use for purely decorative artwork with no evidence task.
---

# Clean Data Presentation

Present evidence so a reader can understand what happened, compare it with the right context, judge the claim's credibility, and inspect the supporting detail without fighting the design.

This skill operationalizes principles synthesized from Edward Tufte's *The Visual Display of Quantitative Information*, *Envisioning Information*, and *Beautiful Evidence*. Treat those principles as analytical design tests, not a fashionable minimalist style. Clarity may require adding evidence, labels, context, uncertainty, or explanation. Removing ink is useful only when it removes no meaning.

## Operating contract

Apply this skill in one of three modes, inferred from the request:

- **Audit:** inspect the artifact and report findings; do not edit it.
- **Improve:** edit the artifact while preserving its evidence, purpose, and platform conventions.
- **Create:** build the artifact from supplied data and requirements.

Honor the user's chosen format and scope. Do not change source data, analytical definitions, business logic, or substantive claims unless explicitly authorized. When a visual defect originates in the data or analysis, identify the defect and stop short of silently repairing the underlying facts.

Use the artifact's native authoring and rendering workflow. Judge the rendered output at its actual delivery size, not only its source representation. For interactive artifacts, inspect the default state and every materially different state.

## The governing question

Before changing a mark, ask:

> What evidence-thinking task must this artifact help the reader perform?

Express the answer as one or more concrete tasks:

- describe magnitude, distribution, composition, or change;
- compare groups, periods, scenarios, or benchmarks;
- understand a relationship, mechanism, sequence, or causal claim;
- locate exceptions, uncertainty, missingness, or risk;
- assess the credibility and provenance of a claim;
- decide or act using stated thresholds and tradeoffs.

Design must follow that task. Do not default to a dashboard, chart type, card grid, story arc, or visual style before the task is known.

## Evidence contract

Establish this contract from the artifact and its context. Infer what is obvious; flag what cannot be established.

```text
EvidenceContract
  audience: who must understand or decide
  question: the analytical question
  claims: claims the artifact makes or implies
  measures: definitions, units, denominators, and aggregation
  comparison: the baseline, reference, or counterfactual
  scope: population, geography, time window, inclusions, exclusions
  source: origin, owner, retrieval date, and version
  transformations: filters, joins, normalization, calculations, models
  uncertainty: sampling, measurement, model, and missing-data limits
  delivery: medium, dimensions, interaction, accessibility needs
```

If the contract lacks information needed to validate a major claim, the artifact cannot receive a full pass. Preserve the gap as an explicit limitation.

## Review and design workflow

### 1. Inventory the evidence

Identify every data-bearing element: chart, table, number, map, image, diagram, annotation, KPI, legend, caption, and claim. Trace each important visual statement back to a source field or documented calculation.

Distinguish:

- observed values from estimates;
- counts from rates and percentages;
- nominal from inflation-adjusted values;
- actuals from targets, forecasts, and scenarios;
- zero from missing, unavailable, suppressed, and not applicable;
- association from mechanism and causation;
- source evidence from decorative or illustrative imagery.

### 2. Test graphical integrity first

Run all Integrity Gates below before polishing. A beautiful artifact that fails an Integrity Gate fails the skill.

### 3. Choose the comparison structure

Show the comparison the question requires within one eyespan whenever practical. Prefer spatial adjacency over forcing the reader to remember values across tabs, pages, tooltips, or slides.

Use a representation suited to the task:

- exact lookup or mixed text and numbers: table or text-table;
- change over ordered time: line or aligned sequence;
- discrete magnitude: dot plot or bar;
- relationship: scatterplot or connected multivariate display;
- distribution: dots, histogram, interval, box plot, or density with sample context;
- repeated comparable conditions: small multiples with common scales;
- geography: map only when location is analytically meaningful;
- structure or process: diagram with explicit semantics;
- compact local trend: sparkline with context and endpoint/reference cues.

Avoid area, angle, volume, perspective, animation, or pictorial encodings when the reader must make precise comparisons and a position or length encoding would work better.

### 4. Build the explanatory surface

Integrate words, numbers, and images near the evidence they explain. Give the reader both:

- a macro reading: purpose, dominant pattern, scale, and conclusion;
- a micro reading: values, exceptions, definitions, and evidence needed to verify the conclusion.

Do not make the title, chart, legend, caption, source, and caveat into a scavenger hunt. Put explanations at the point of need.

### 5. Apply visual economy

For each element, ask:

> If this were removed or subdued, what evidence, comparison, orientation, or accessibility would be lost?

- If nothing would be lost, remove it.
- If orientation would be weakened, retain it but reduce its visual weight.
- If evidence would be lost, keep it and strengthen its legibility.

This is the operational form of the data-ink principle. Do not calculate or optimize a literal numeric data-ink ratio. Necessary axes, labels, uncertainty intervals, reference lines, annotations, and source notes are evidence-supporting ink.

### 6. Add advanced structure only when earned

Use advanced techniques when they improve the evidence task:

- small multiples for repeated comparisons;
- layering and separation for dense overlapping systems;
- micro/macro composition for overview plus inspection;
- multivariate displays when interactions among variables matter;
- high-resolution detail when the audience can examine it;
- narratives of space and time when sequence, movement, or process matters;
- mapped images when location on an image is itself evidence;
- sparklines when local context is more valuable than a standalone chart;
- causal diagrams only when links have defined meaning and evidentiary support.

Do not force complexity into a simple finding. Information density means useful evidence per unit of attention, not maximum marks per pixel.

### 7. Render and verify

Inspect the final artifact at its intended size and in all relevant formats. Verify:

- no clipping, overlap, truncation, overflow, or illegible reduction;
- labels, scales, legends, notes, and units remain readable;
- data and text survive export without changed values or missing glyphs;
- color and hierarchy work in light/dark or print contexts when applicable;
- interactive controls, filters, tooltips, keyboard flow, and default state work;
- the artifact remains understandable without relying on hover alone;
- visual comparisons still work at the smallest supported viewport or page size.

## Acceptance criteria

Use `PASS`, `FAIL`, or `N/A` for every applicable criterion. Do not average failures into a cosmetic score.

### I. Integrity Gates — all are blocking

#### I-01 Traceable evidence

Every material claim, displayed number, and data mark is traceable to a named source or a documented calculation. Source, time coverage, and freshness are visible at an appropriate level.

#### I-02 Correct definitions

Measures, units, denominators, population, time window, and aggregation are stated or unambiguous. Percentages identify their denominator; rates identify their basis; currency identifies denomination and adjustment when relevant.

#### I-03 Proportional representation

The visual magnitude of an effect is proportional to the numerical effect. Length, area, volume, angle, color, and animation do not exaggerate or suppress differences. When testing graphical distortion, compare:

```text
visual effect shown / numerical effect in the data
```

Material deviation from 1 must be inherent to a clearly explained transform, not decoration or manipulation.

#### I-04 Honest scales and baselines

Scale type, direction, domain, intervals, breaks, and transformations are visible and appropriate. Bars that encode magnitude begin at zero. A nonzero baseline for position-based charts is allowed only when it serves the question without overstating the effect and is clearly shown. Logarithmic, indexed, normalized, and dual scales are explicitly labeled.

#### I-05 Comparable encodings

Items intended for comparison use common definitions, scales, units, and visual encodings. If scales differ, the difference is conspicuous and analytically justified. Three-dimensional perspective never changes apparent magnitude.

#### I-06 Complete relevant context

The display includes the relevant benchmark, prior period, distribution, denominator, target, or counterfactual needed to interpret the claim. It does not cherry-pick a window, subgroup, category, or axis domain that reverses or materially inflates the conclusion.

#### I-07 Missingness and uncertainty

Missing, estimated, suppressed, imputed, and not-applicable values are distinct from zero. Material uncertainty, sample size, error, range, or model status is shown in the display or immediately adjacent note.

#### I-08 Observation versus causation

Causal language and arrows appear only when supported by an appropriate design and evidence. Association, chronology, mechanism, and causality are not treated as synonyms. Alternative explanations or limitations are acknowledged when material.

#### I-09 Reproducible transformation

Material filters, exclusions, joins, derived measures, normalization, smoothing, modeling, and revisions are documented sufficiently for an informed reviewer to reproduce or challenge the result.

#### I-10 No concealed contradiction

Annotations, titles, sorting, emphasis, and narrative agree with the displayed evidence. The design does not hide inconvenient values, exceptions, categories, or source limitations needed to evaluate the claim.

### C. Core analytical design — mandatory when applicable

#### C-01 Question-led composition

The artifact has a clear analytical purpose. Its title or opening context identifies the question or a claim supported by the evidence, not merely a topic label such as “Dashboard” or “Monthly Results.”

#### C-02 Comparison within eyespan

The principal comparison is spatially adjacent or aligned. The reader is not required to memorize values across distant pages, slides, tabs, dropdown states, or legends when direct comparison is feasible.

#### C-03 Appropriate representation

The chosen chart, table, image, map, or diagram matches the analytical task and data type. A graphic is not used when a sentence or small table would communicate the evidence more precisely.

#### C-04 Data priority

Evidence is the most visually prominent content. Branding, container chrome, gradients, illustrations, icons, shadows, borders, and backgrounds do not compete with it.

#### C-05 Functional ink

Every visible element provides evidence, comparison, structure, navigation, explanation, or accessibility. Redundant decoration and repeated labels are removed; necessary scaffolding is quiet but legible.

#### C-06 Direct identification

Series, groups, reference lines, unusual points, and important values are labeled directly where practical. Legends are used only when direct labels would cause more confusion, and they remain close to the evidence.

#### C-07 Ordered for reasoning

Categories are ordered by value, sequence, geography, hierarchy, or a meaningful domain order. Alphabetical order is used only when lookup is the task. Sorting does not conceal the original or expected structure.

#### C-08 Visible magnitude and variation

The artifact reveals level, change, spread, and exceptions relevant to the question. Aggregates do not hide distributions or subgroup differences that could change the conclusion.

#### C-09 Integrated explanation

Words, numbers, annotations, and images work together. Notes sit beside the marks they explain. The reader can distinguish observation, interpretation, and recommendation.

#### C-10 Documentation at the point of need

Units, definitions, source, update time, caveats, and methodology are placed where readers can find them without leaving the artifact. Detail may be layered, but credibility information is not buried.

#### C-11 Legible density

The artifact uses the available resolution to show useful detail without collision or crowding. Increasing size, adding panels, or improving layering is preferred to discarding analytically necessary evidence.

#### C-12 Stable visual grammar

The same variable keeps the same color, symbol, scale direction, unit, and naming across the artifact. A visual change signals a data difference, state change, or semantic distinction—not arbitrary variety.

### L. Layering, color, and multidimensional information

#### L-01 Layering and separation

Foreground evidence, comparison/reference information, annotation, and background structure occupy perceptually distinct layers. The design uses position, weight, value, texture, or spacing before adding saturated color.

#### L-02 Color carries information

Color encodes a defined variable, state, emphasis, or grouping. Categorical palettes distinguish; sequential palettes order; diverging palettes use a meaningful midpoint. Decorative color does not create false grouping or salience.

#### L-03 Small intense accents

Strong color is reserved for small, important signals such as selection, exception, alert, or reference. Large saturated fields do not overpower fine evidence unless magnitude itself is encoded by that field.

#### L-04 Redundant accessibility cues

Color is not the only carrier of meaning. Labels, position, shape, line style, or texture preserve the distinction for color-vision differences, monochrome output, and low-quality displays.

#### L-05 Micro/macro reading

Complex displays provide an immediate overall structure and support close inspection of individual values or local patterns. The overview remains truthful to the detail; the detail is not hidden behind an unsupported summary.

#### L-06 Escaping flatland

When representing multivariate, spatial, or temporal phenomena on a flat surface, the design uses meaningful layers, facets, contours, alignment, annotation, or interaction. It does not simulate dimensionality with ornamental 3D perspective.

### A. Advanced analytical design — apply when the evidence warrants it

#### A-01 Small multiples

Repeated panels use the same design, scale, order, and aspect ratio so differences come from data rather than formatting. Exceptions to shared scales are conspicuous and justified.

#### A-02 Multivariate context

The display includes the variables needed to understand interaction, mechanism, confounding, or heterogeneity. Additional variables earn their presence by answering the evidence question.

#### A-03 Space-time narrative

Sequences preserve direction, duration, order, and location where relevant. Time is not reduced to disconnected snapshots when continuity matters. Animation has a static or inspectable alternative for comparison.

#### A-04 Mapped evidence

Images, maps, and diagrams connect labels and measurements to precise locations. Overlays align with their underlying geometry and include orientation, scale, and registration when material.

#### A-05 Causal links

Lines and arrows have an explicit legend or grammar. Direction, sequence, dependency, association, and causation use distinct semantics. Link confidence or ambiguity is visible when it affects interpretation.

#### A-06 Sparklines and compact trends

Inline trends include enough history, scale context, and endpoint/reference information to prevent an isolated wiggle from becoming a claim. Comparable sparklines share scale or clearly disclose differences.

#### A-07 High-resolution evidence

When the medium permits, show granular evidence, outliers, and local variation instead of substituting oversized summaries. Provide filtering or focus mechanisms without making the default view empty or uninformative.

#### A-08 Evidence breadth

Relevant words, numbers, tables, images, and diagrams may coexist on one surface. Do not segregate evidence by medium when integration improves reasoning.

### X. Delivery and accessibility — mandatory for the target medium

#### X-01 Readable at delivery size

Text, values, marks, line weights, and spacing remain legible at the smallest intended size. No essential interpretation depends on zooming into a low-resolution image.

#### X-02 Accessible equivalent

Provide concise alt text or an adjacent textual summary for meaningful visuals. Complex graphics include a longer description, accessible data table, or equivalent path when required by the medium.

#### X-03 Navigable structure

Headings, table headers, reading order, keyboard navigation, focus states, and interactive labels are semantically correct for the platform.

#### X-04 Format resilience

The evidence survives export, printing, projection, responsive resizing, dark mode, and grayscale where those are delivery requirements. Do not accept a source file that has not been rendered and checked.

#### X-05 Honest interaction

Filters and controls disclose active state and scope. Defaults do not selectively favor the headline claim. Tooltips supplement rather than contain all essential evidence. Reset and empty states are understandable.

## Artifact-specific guidance

### Dashboards and applications

- Organize around decisions and comparisons, not a grid of available metrics.
- Use summary values as entry points into evidence, not as isolated status decoration.
- Show active filters, freshness, units, and scope globally when they affect every view.
- Keep the default state analytically useful; do not require interaction to discover the main result.
- Put related values on shared scales and align repeated panels.
- Avoid gauges when a number plus context or a bullet/position display is more precise.

### Reports and documents

- Place figures and tables near the paragraphs that interpret them.
- Use captions to state what is shown, scope, units, and source—not to repeat the title.
- Keep tables readable as evidence: meaningful order, aligned decimals, restrained rules, explicit units.
- Avoid sending the reader to an appendix for context required to trust the main claim.

### Presentations

- Give each evidence slide a complete analytical point, not a fragment of a later reveal.
- Prefer one integrated evidence surface over bullets describing a chart shown elsewhere.
- Preserve source, scope, and uncertainty on the slide.
- Avoid builds that prevent comparison between states; use adjacent small multiples when comparison is the task.
- Size for the farthest viewer and the actual projection environment.

### Spreadsheets

- Separate raw inputs, transformations, calculations, and presentation ranges.
- Preserve formulas and provenance; do not replace calculations with unexplained hard-coded values.
- Use cell formatting to clarify units, precision, hierarchy, and exceptions—not to create decorative heat.
- Ensure conditional formatting has a defined scale, legend, and non-color cue when it carries meaning.
- Make print/export ranges repeat headers and retain source and scope notes.

### Web and interactive graphics

- Make the first render meaningful before hover, scroll-triggered animation, or filtering.
- Preserve comparison across responsive breakpoints; stack rather than shrink until labels become illegible.
- Keep interaction latency, focus, and selected state visible.
- Provide stable URLs or exportable states when the evidence must be cited or reviewed.

## Common failure patterns

Reject or repair these patterns when present:

- oversized KPI cards with no comparison, distribution, or source;
- 3D bars, exploded pies, pictograms, or perspective that changes apparent magnitude;
- rainbow palettes without ordered or categorical meaning;
- dual axes that imply a relationship through arbitrary scaling;
- truncated bar axes or hidden scale breaks;
- percentages without denominators or counts;
- averages without spread, sample size, or subgroup context when material;
- smoothed lines without raw observations or disclosed method;
- maps used for non-geographic comparisons;
- legends distant from the data and repeated decoding work;
- labels rotated, abbreviated, or truncated to rescue an unsuitable layout;
- decorative icons that occupy more attention than the evidence;
- causal arrows that merely mean “related to”;
- screenshots of tables that should be accessible native tables;
- interaction that hides the default scope or silently changes denominators;
- dense detail compressed into illegibility rather than layered or given space;
- extreme minimalism that removes orientation, units, uncertainty, or provenance.

## Acceptance decision

Assign one result to the artifact:

- **PASS:** every applicable Integrity Gate and Core criterion passes; applicable Delivery criteria pass; Advanced criteria either pass or are reasonably `N/A`; the rendered output has been verified.
- **CONDITIONAL:** no Integrity Gate fails, but one or more Core or Delivery criteria remain unresolved. State the exact repair needed.
- **FAIL:** any Integrity Gate fails, the central claim cannot be supported from available evidence, or the rendered artifact materially misleads or breaks.

Do not award `PASS` based on aesthetics, polish, or a numerical average.

## Required completion report

After an audit or modification, report concisely:

```text
Clean Data Presentation Review
  result: PASS | CONDITIONAL | FAIL
  evidence task: <one sentence>
  integrity gates: <passed count>/<applicable count>
  core criteria: <passed count>/<applicable count>
  advanced criteria applied: <IDs or none>
  material changes: <what changed, if edits were authorized>
  unresolved findings: <criterion ID, evidence, and repair>
  verification: <rendered formats, sizes, and states checked>
```

Lead with blockers, not a long style critique. Tie each finding to a criterion ID and visible evidence in the artifact. Recommend the smallest change that restores truth, comparison, or legibility.

## Interpretation boundaries

- Do not confuse Tufte's principles with a mandated monochrome or sparse aesthetic.
- Do not remove useful context merely to reduce visual elements.
- Do not add data density that the question, audience, or medium cannot support.
- Do not claim empirical certainty for a design heuristic. When user testing or domain convention conflicts with a heuristic, preserve integrity and choose the design that better serves the evidence task.
- Do not imitate copyrighted examples, diagrams, prose, or page designs from the books. Apply the principles to the user's own evidence.
- Treat accessibility and platform semantics as required operational extensions, not claims about the books' original scope.

## Intellectual basis

This skill is an original operational synthesis, not a substitute for the books. Its principal foundations are:

- *The Visual Display of Quantitative Information*: graphical excellence and integrity, proportional representation, data-ink, chartjunk, data density, small multiples, editing, and high-resolution statistical graphics.
- *Envisioning Information*: escaping flatland, micro/macro readings, layering and separation, small multiples, color as information, and narratives of space and time.
- *Beautiful Evidence*: mapped pictures, sparklines, links and causal arrows, integration of words/numbers/images, analytical design, documentation, credibility, and corruption in evidence presentations.

Authoritative book descriptions:

- https://www.edwardtufte.com/book/the-visual-display-of-quantitative-information/
- https://www.edwardtufte.com/book/envisioning-information/
- https://www.edwardtufte.com/book/beautiful-evidence/
