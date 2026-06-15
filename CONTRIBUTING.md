# Contribution Guidelines

Thanks for helping improve this repository.

This project uses `README.md` as the single source of truth for latent-action papers, systems, implementations, probes, and open problems. Keep additions concise, citable, and aligned with the topic-first taxonomy.

## What To Update

When adding or editing an entry:

1. Update the matching section in [`README.md`](README.md).
2. Add or update the matching row in the section's `### Models at a glance` table when the entry is a model or system.
3. Add a full item under `### Entries` only once. Use short cross-links elsewhere.
4. Preserve the section ordering rule: core entries first when marked, then chronological order by year.
5. Keep uncertain candidates out of the main list until the paper, code, or C1/C2 justification is clear; use the PR notes or an issue to discuss them first.

## Inclusion Checklist

Before adding a paper, confirm:

- [ ] **C1: Label-free action inference.** The action representation is learned from action-free or weakly labeled video through reconstruction, prediction, flow, contrast, or structural constraints.
- [ ] **C2: Action-interface usage.** The latent is used as an action: world-model conditioning, VLA/policy pretraining, decoding to executable controls, cross-embodiment transfer, or post-training action refinement.
- [ ] The entry is not already covered under another section.
- [ ] Any relaxed criterion is explicitly labeled `[Borderline]`.

## Entry Format

Use this format for model entries:

```markdown
- **NAME** — *Full Paper Title*. VENUE YEAR.
  [![arXiv](https://img.shields.io/badge/arXiv-ID-b31b1b.svg)](https://arxiv.org/abs/ID) [![Code](https://img.shields.io/badge/Code-GitHub-black.svg)](code-link)
  `repr: ...` `obj: ...` `data: ...` `use: ...`
  One sentence on what is genuinely new about how latent actions are learned, structured, evaluated, or used.
```

Rules:

- Prefer official project, arXiv, conference, and code links.
- Link to the arXiv `abs` page, not the PDF.
- Keep descriptions factual and compact.
- Use badges in this order when available: `arXiv`, `Paper`, `Project`, `Code`, `Dataset`.
- Avoid duplicate full entries. One paper or system should have one primary home.
- If a tag value does not exist yet, propose it in the PR notes.

## Tag Vocabulary

| Axis | Allowed values |
|---|---|
| `repr:` | `discrete-VQ` · `discrete-FSQ` · `discrete-token` · `continuous` · `hybrid` · `hierarchical` · `structured` |
| `obj:` | `IDM+FDM` · `world-model` · `flow` · `contrastive` · `structured` · `supervised-IDM` |
| `data:` | `robot` · `human-video` · `game/sim` · `driving` · `ego` · `mixed` · `web-video` |
| `use:` | `WM-control` · `VLA-pretrain` · `policy-decode` · `cross-embodiment` · `post-train` · `analysis` |

Multiple values per axis are fine. Use `·` as the separator inside a tag.

## Benchmarks And Probes

- Add direct latent-action probes in the relevant section's `### Benchmarks and probes` table.
- Say whether the metric is direct LAM evaluation or downstream task evaluation.
- For downstream benchmarks such as LIBERO, MetaWorld, SimplerEnv, or driving metrics, note the confound: policy/world-model capacity and data scale affect the result.

## Pull Requests

Before opening a PR, check:

1. Rendered Markdown tables still look correct on GitHub.
2. Every new model entry has `repr`, `obj`, `data`, and `use` tags.
3. Primary links resolve and point to official sources when possible.
4. The entry satisfies C1/C2 or is explicitly labeled `[Borderline]`.
5. The `Models at a glance` row and full `Entries` item are consistent.
6. No placeholder owner, repository, or `TODO` link remains in the rendered README.

## Code Of Conduct

Please be respectful and constructive in issues and pull requests.
