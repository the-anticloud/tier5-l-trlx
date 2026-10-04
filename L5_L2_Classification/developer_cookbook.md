# Developer Cookbook — L_TRLX
**Stack:** Python 3.11, trlx 0.x, PyTorch 2.10+, DeepSpeed ZeRO, PAX 27B, AIOSS_FORMAT
**Domain:** TRLX: distributed RLHF training framework for PAX 27B with Anticloud reward signals

## TRLX RLHF training
```python
import trlx
from l_trlx import AnticloudRLHFConfig

config = AnticloudRLHFConfig(
    model_path="./pax-27b-fp16.safetensors",
    reward_fn_path="./anticloud_reward_fn.py",
    deepspeed_config="./deepspeed_zero3.json",
    aioss_chain="./trlx.aioss"
)

trainer = trlx.train(
    reward_fn=config.reward_fn,
    prompts=config.load_prompts("./anticloud_rlhf_prompts.jsonl"),
    config=config.trlx_config
)
trainer.save_pretrained("./pax-27b-rlhf-checkpoint/")
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```
