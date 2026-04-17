# SP8192 Per-Layer GPTQ Clip

This directory holds the Phase 3 per-layer GPTQ clipping ablation on top of the
best validated Phase 3 runtime stack.

Code base:
- `2026-04-17_SP8192_ParallelResidualOnly`

Runtime stack carried forward from the best passing run:
- `PARALLEL_RESIDUAL_START=7`
- `LOOP_START=3`
- `ENABLE_LOOPING_AT=0.35`
- `QK_GAIN_INIT=5.25`
- `MATRIX_LR=0.026`
- `MUON_WD=0.095`
- `EMA_DECAY=0.9965`
- `WARMDOWN_FRAC=0.75`

Intent:
- keep the Run 5 architecture and optimizer stack unchanged
- split GPTQ clipping by weight family instead of using one shared matrix clip
- test `ATTN_CLIP_SIGMAS=13.0` and `MLP_CLIP_SIGMAS=12.0`

Packed execution path:
- `train_gpt.py`

Editable source:
- `train_gpt_human.py`
