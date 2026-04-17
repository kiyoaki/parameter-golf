# SP8192 Parallel Residual QK525 TTT

This directory holds the Run 4 code path on top of the verified
`2026-04-05_SP8192_GPTQ-Embeddings_SDClip_Loop45x2` baseline.

Base:
- upstream `2026-04-05_SP8192_GPTQ-Embeddings_SDClip_Loop45x2`

Intent:
- keep the Run 3 stack
- add legal score-first TTT evaluation after quantized sliding-window eval

Primary env overrides for the run:
- `PARALLEL_RESIDUAL_START=7`
- `LOOP_START=3`
- `ENABLE_LOOPING_AT=0.35`
- `QK_GAIN_INIT=5.25`
- `MATRIX_LR=0.022`
- `MUON_WD=0.095`
- `EMA_DECAY=0.9965`
- `WARMDOWN_FRAC=0.72`
- `TTT_ENABLED=1`
- `TTT_LR=0.005`
- `TTT_EPOCHS=3`
- `TTT_MOMENTUM=0.9`
- `TTT_CHUNK_TOKENS=32768`

Packed execution path:
- `train_gpt.py`

Editable source:
- `train_gpt_human.py`
