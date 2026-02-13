# GPT_2

This repository contains the Week 5 GPT-2 fine-tuning notebook and run-metrics workflow.

## Latest run results (from notebook output)

Machine-readable results are checked in here: [`run_results.json`](./run_results.json).

| Run | AMP requested | AMP active | Checkpointing | Train time (sec) | Val perplexity |
|---|---:|---:|---:|---:|---:|
| baseline_fp32 | No | No | No | 1215.12 | 33.026 |
| mixed_precision | Yes | No | No | 1453.52 | 32.926 |
| amp_plus_checkpointing | Yes | No | Yes | 1654.75 | 32.425 |

> Note: in this saved run, AMP was requested for two runs but not active (`use_amp_active = false`), which is expected on CPU-only execution.

## Sample generation result

- **Smoothed BLEU:** `0.10832996189306149`
- **Prompt:**
  `Homarus gammarus , known as the European lobster or common lobster , is a species of clawed lobster from the eastern Atlantic Ocean , Mediterranean Sea`
- **Reference continuation:**
  `and parts of the Black Sea . It is closely related to the American lobster , H. americanus . It may grow to a length of 60 cm`
- **Generated continuation:**
  `, and the Gulf of Mexico . It is a common lobster in the United States , Canada , and Mexico . It is a common lobster in the United`

## Open notebook files

- Notebook source: [`Wk5_run_metrics.ipynb`](./Wk5_run_metrics.ipynb)

## Notebook scope

The run-metrics workflow includes:

- dependency setup,
- WikiText-2 data loading and cleaning,
- tokenization and sequence chunking,
- GPT-2 training runs,
- metric/evaluation helpers,
- output artifact export.
