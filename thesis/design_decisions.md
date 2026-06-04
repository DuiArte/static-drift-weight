# Design decisions

Each decision is published as a *choice and its trade-off*, without the numeric
setting that implements it.

| Decision | Choice | Trade-off | Published? |
|---|---|---|---|
| Drift control | tolerance bands, not calendar rebalance | lower turnover vs slower mean-reversion | choice yes, band width **no** |
| Universe | liquid, broad asset classes | breadth vs depth | yes |
| Risk ceiling | per-asset caps | discipline vs upside capture | choice yes, cap level **no** |
| Cost model | net + screen before trade | realism vs simplicity | yes |
| Review cadence | infrequent, rule-triggered | stability vs responsiveness | yes |

The pattern: the *type* of decision and its reasoning are public; the *number* that
operationalizes it is private, because the number is the position.

> Placeholder draft.
