# Deploy Guide — L_TRLX
**Tier:** TIER_5_WORLD_NEURO_EMBODIED | **Stack:** Python 3.11, trlx 0.x, PyTorch 2.10+, DeepSpeed ZeRO, PAX 27B, AIOSS_FORMAT
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, trlx 0.x, PyTorch 2.10+, DeepSpeed 0.14+. Multi-GPU (A100) for practical training speed.

## Environment
Multi-GPU (4x+ A100) for practical PAX 27B RLHF. DeepSpeed ZeRO-3 required for model sharding.

## AIOSS Integration
```bash
aioss init --module L_TRLX --output ./l_trlx.aioss
aioss append --chain ./l_trlx.aioss --payload ./output.bin --module L_TRLX
aioss verify --chain ./l_trlx.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="L_TRLX",
    aioss_chain="./L_TRLX.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./L_TRLX.aioss --verbose
python -m L_TRLX.tests.smoke
```
