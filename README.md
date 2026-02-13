 GPT_2

This repository contains the Week 5 GPT-2 fine-tuning notebook and run-metrics workflow.

## Latest run results (inline)

### Final metrics by run

| Run | AMP requested | AMP active | Checkpointing | Train time (sec) | Val perplexity |
|---|---:|---:|---:|---:|---:|
| baseline_fp32 | No | No | No | 1215.12 | 33.026 |
| mixed_precision | Yes | No | No | 1453.52 | 32.926 |
| amp_plus_checkpointing | Yes | No | Yes | 1654.75 | 32.425 |

- **Best validation perplexity:** `32.425` (`amp_plus_checkpointing`)
- **Fastest run:** `baseline_fp32` at `1215.12 sec`
- **CPU note:** AMP was requested for two runs but inactive (`use_amp_active = false`) in this saved CPU execution.

### Training log snapshots (from notebook output)

```text
[baseline_fp32] epoch 0 step 1/300 loss 4.9786
[baseline_fp32] epoch 0 step 50/300 loss 4.3684
[baseline_fp32] epoch 0 step 100/300 loss 3.1455
[baseline_fp32] epoch 0 step 150/300 loss 3.8088
[baseline_fp32] epoch 0 step 200/300 loss 3.8336
[baseline_fp32] epoch 0 step 250/300 loss 3.6804
[baseline_fp32] epoch 0 step 300/300 loss 3.7823
```

```text
[mixed_precision] epoch 0 step 1/300 loss 4.3242
[mixed_precision] epoch 0 step 50/300 loss 3.8912
[mixed_precision] epoch 0 step 100/300 loss 3.7188
[mixed_precision] epoch 0 step 150/300 loss 4.1064
[mixed_precision] epoch 0 step 200/300 loss 3.6311
[mixed_precision] epoch 0 step 250/300 loss 3.3621
[mixed_precision] epoch 0 step 300/300 loss 3.5245
```

```text
[amp_plus_checkpointing] epoch 0 step 1/300 loss 4.4466
[amp_plus_checkpointing] epoch 0 step 50/300 loss 3.8051
[amp_plus_checkpointing] epoch 0 step 100/300 loss 4.0113
[amp_plus_checkpointing] epoch 0 step 150/300 loss 4.1325
[amp_plus_checkpointing] epoch 0 step 200/300 loss 3.3475
[amp_plus_checkpointing] epoch 0 step 250/300 loss 3.8197
[amp_plus_checkpointing] epoch 0 step 300/300 loss 3.2242
```

### Sample generation result

- **Smoothed BLEU:** `0.10832996189306149`
- **Prompt:**
  `Homarus gammarus , known as the European lobster or common lobster , is a species of clawed lobster from the eastern Atlantic Ocean , Mediterranean Sea`
- **Reference continuation:**
  `and parts of the Black Sea . It is closely related to the American lobster , H. americanus . It may grow to a length of 60 cm`
- **Generated continuation:**
  `, and the Gulf of Mexico . It is a common lobster in the United States , Canada , and Mexico . It is a common lobster in the United`

## Data files

- Notebook source: [`Wk5_run_metrics.ipynb`](./Wk5_run_metrics.ipynb)
- Parsed results JSON: [`run_results.json`](./run_results.json)
- Rendered markdown notebook fallback: [`Wk5_run_metrics.rendered.md`](./Wk5_run_metrics.rendered.md)
