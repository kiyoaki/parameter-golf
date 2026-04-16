# SP8192 Parallel Residual Only

This directory holds the first Phase 2 ablation on top of the verified
`2026-04-05_SP8192_GPTQ-Embeddings_SDClip_Loop45x2` baseline.

Base:
- upstream `2026-04-05_SP8192_GPTQ-Embeddings_SDClip_Loop45x2`

Intent:
- add GPT-J style parallel residuals only
- keep all other baseline defaults unchanged

Primary env override for the run:
- `PARALLEL_RESIDUAL_START=7`

Packed execution path:
- `train_gpt.py`

Editable source:
- `train_gpt_human.py`
