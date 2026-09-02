# Clean Data Presentation Skill

## Make every chart, table, dashboard, and report earn the reader's trust.

Clean Data Presentation is a reusable Codex skill for creating and reviewing data-bearing artifacts. It turns enduring information-design principles into explicit acceptance criteria for truth, comparison, visual clarity, evidence density, and delivery quality.

It does not impose a sparse visual style. It asks a harder question:

> Does the artifact help the reader understand the evidence and judge the claim without being misled by the design?

[View the skill](SKILL.md)

## What it does

Run the skill on a dashboard, slide deck, report, spreadsheet, document, chart, table, or web view to:

- trace visible claims back to their evidence;
- detect distorted scales, missing context, unsupported causality, and concealed uncertainty;
- select a representation that matches the analytical task;
- improve comparison, labeling, layering, color, and information density;
- integrate words, numbers, images, annotations, and sources;
- verify the rendered artifact at its real delivery size;
- return a deterministic `PASS`, `CONDITIONAL`, or `FAIL` decision.

The skill can audit an existing artifact, improve one in place, or guide creation from source data.

## Bad versus good

The fictional example below contains the same headline values in both versions.

### Bad: the design manufactures a dramatic result

```text
PRODUCT B CRUSHES PRODUCT A

Product A  ███                         48%
Product B  ████████████████████████    52%

Axis shown: 47% to 53%
```

Why it fails:

- The truncated bar baseline makes a four-point difference appear enormous.
- “Crushes” is not supported by the displayed magnitude.
- The denominator, sample size, uncertainty, population, date, and source are absent.
- The reader cannot determine whether the difference is meaningful or noise.

This fails `I-01`, `I-02`, `I-03`, `I-04`, `I-06`, `I-07`, and `I-10` in the skill.

### Good: the evidence controls the conclusion

```text
Preference is closely divided

               Share     95% interval
Product A       48%       45%–51%
Product B       52%       49%–55%

Question: “Which product would you choose today?”
Population: U.S. adults; n=1,240; fielded May 12–14, 2026
Source: Fictional example survey; weighted to population benchmarks
```

Why it works:

- The title states a conclusion proportionate to the evidence.
- Values are directly comparable without visual exaggeration.
- Uncertainty reveals that the estimates overlap.
- Population, sample size, timing, question wording, and methodology are available at the point of need.
- The compact table is more precise than a chart for two exact values.

Good presentation is not the removal of all supporting ink. Here, adding context makes the display cleaner because it makes the reasoning complete.

## One skill, three modes

### Audit

Inspect an artifact without modifying it.

```text
Use $clean-data-presentation to audit this dashboard. Identify every
integrity blocker, cite the criterion ID, and do not edit the source.
```

### Improve

Repair the presentation while preserving the source data and analytical definitions.

```text
Apply $clean-data-presentation to this quarterly report. Improve the charts,
tables, annotations, and source notes, then verify the rendered PDF.
```

### Create

Use the criteria while building a new data artifact.

```text
Use $clean-data-presentation to turn this dataset into an executive decision
brief. Show the relevant comparison, uncertainty, exceptions, and provenance.
```

## The acceptance model

The skill evaluates 41 explicit criteria in five layers.

| Layer | Purpose | Decision effect |
|---|---|---|
| 10 Integrity Gates | Truth, definitions, proportionality, scales, context, uncertainty, causality, and reproducibility | Any failure blocks acceptance |
| 12 Core Criteria | Purpose, comparison, representation, visual economy, labeling, ordering, and evidence integration | All applicable criteria must pass |
| 6 Layering Criteria | Foreground/background separation, meaningful color, micro/macro reading, and dimensional clarity | Required when applicable |
| 8 Advanced Criteria | Small multiples, multivariate context, space-time narratives, mapped evidence, causal links, and sparklines | Applied only when the evidence warrants them |
| 5 Delivery Criteria | Legibility, accessibility, navigation, export resilience, and honest interaction | Required for the target medium |

No cosmetic score can offset an integrity failure.

## Fundamentals first

The skill begins with non-negotiable evidence quality:

1. Can each claim be traced to a source or calculation?
2. Are units, denominators, populations, and time windows clear?
3. Is the visible effect proportional to the numerical effect?
4. Are scales, baselines, transformations, and comparisons honest?
5. Are missingness, uncertainty, and selection effects visible?
6. Does the language distinguish observation, association, mechanism, and causality?

Only after these pass does it optimize data-ink, direct labeling, visual hierarchy, density, or polish.

## Advanced when earned

Complex evidence may need more information, not less. The skill can guide:

- small multiples with shared scales;
- micro/macro views that support overview and inspection;
- multivariate displays that expose interaction and confounding;
- layered color and annotation systems;
- high-resolution evidence instead of oversized summaries;
- spatial and temporal narratives;
- mapped images and explicitly defined causal links;
- compact sparklines with sufficient context.

These are conditional tools. The skill will not turn a two-number finding into an elaborate dashboard merely to appear sophisticated.

## Works across artifacts

The acceptance criteria include specific guidance for:

- dashboards and applications;
- reports and documents;
- presentations;
- spreadsheets;
- web and interactive graphics.

The skill preserves the conventions and constraints of the chosen medium while keeping the evidence standard consistent.

## Install

The repository is intentionally simple. Install the skill by placing the repository—or its `SKILL.md` file—in a skill folder named `clean-data-presentation` within your Codex skills directory.

Expected structure:

```text
clean-data-presentation/
└── SKILL.md
```

The skill uses standard YAML frontmatter and passes the Codex skill validator.

## Design philosophy

The skill is an original operational synthesis inspired by three Edward Tufte books:

- [The Visual Display of Quantitative Information](https://www.edwardtufte.com/book/the-visual-display-of-quantitative-information/) — graphical excellence and integrity, data-ink, proportional representation, statistical graphics, and small multiples.
- [Envisioning Information](https://www.edwardtufte.com/book/envisioning-information/) — escaping flatland, layering and separation, micro/macro readings, color, and narratives of space and time.
- [Beautiful Evidence](https://www.edwardtufte.com/book/beautiful-evidence/) — integrated evidence, sparklines, mapped pictures, causal links, documentation, credibility, and analytical design.

The repository does not reproduce the books or their examples. Accessibility and platform semantics are included as modern operational requirements and are not attributed to the books' original scope.

## What this skill refuses to do

- Beautify a misleading chart without repairing or flagging the underlying integrity problem.
- Remove axes, labels, uncertainty, or source context merely to look minimal.
- Change source data or analytical definitions without authorization.
- Treat a correlation as a causal result.
- Force every artifact into a dashboard, slide template, or monochrome aesthetic.
- Award a passing score because the output looks polished.

## Output contract

Every completed review reports:

```text
Clean Data Presentation Review
  result: PASS | CONDITIONAL | FAIL
  evidence task: <one sentence>
  integrity gates: <passed>/<applicable>
  core criteria: <passed>/<applicable>
  advanced criteria applied: <IDs or none>
  material changes: <if edits were authorized>
  unresolved findings: <criterion ID, evidence, and repair>
  verification: <formats, sizes, and states checked>
```

The result is designed to be reviewable, repeatable, and useful in a real delivery workflow—not merely inspirational.

---

Clean Data Presentation is an independent project and is not affiliated with or endorsed by Edward Tufte or Graphics Press.
