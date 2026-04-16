# Model Comparison Report

- Generated at: 2026-04-15 21:50:05
- Compared models (3):
  - modele_dechets_nano_merged_v1
  - modele_dechets_nano_merged_v2_balanced
  - modele_dechets_nano_finetuned_from_scratch_clean_v2

## Ranking by mAP50-95 (best)

1. modele_dechets_nano_merged_v1 | mAP50-95=0.4717 | Precision=0.5620 | Recall=0.5659 | Best epoch=187
2. modele_dechets_nano_merged_v2_balanced | mAP50-95=0.4629 | Precision=0.7301 | Recall=0.5811 | Best epoch=217
3. modele_dechets_nano_finetuned_from_scratch_clean_v2 | mAP50-95=0.4509 | Precision=0.6692 | Recall=0.5719 | Best epoch=38

## Figure

- reports/comparison_modele_dechets_nano_merged_v1_vs_modele_dechets_nano_merged_v2_balanced_vs_modele_dechets_nano_finetuned_from_scratch_clean_v2_20260415_215004.png

## Table

| Model | Best Epoch | Precision | Recall | mAP50 | mAP50-95 | Final Loss |
| --- | --- | --- | --- | --- | --- | --- |
| modele_dechets_nano_merged_v1 | 187 | 0.5620 | 0.5659 | 0.6095 | 0.4717 | 1.0880 |
| modele_dechets_nano_merged_v2_balanced | 217 | 0.7301 | 0.5811 | 0.6101 | 0.4629 | 1.0906 |
| modele_dechets_nano_finetuned_from_scratch_clean_v2 | 38 | 0.6692 | 0.5719 | 0.6058 | 0.4509 | 1.1618 |
