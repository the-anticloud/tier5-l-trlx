# HF_Leaderboard_Lab_Results

**Project:** `L_TRLX`  
**Tier:** `TIER_5_WORLD_NEURO_EMBODIED`  
**Slug:** `carperai/trlx`  
**Commit:** `3340c2f3a56d`  
**Run:** `2026-09-30T15:07:07.146295+00:00`  

## Isolation Environment

| Field | Value |
| ----- | ----- |
| Platform | `win32` |
| Python | `3.12.10` |
| HF model | `distilbert-base-uncased` |
| HF load time | `4.42s` |
| Inference device | `cpu` |

## Results

**Framework:** [HuggingFace Open LLM Leaderboard (proxy via distilbert-base-uncased)](https://huggingface.co/docs/leaderboards/en/open_llm_leaderboard/archive)

**Model used:** `distilbert-base-uncased`

### Inference Latency (Classification)

| Metric | Value |
| ------ | ----- |
| Avg latency | **47.58 ms** |
| Min latency | 45.02 ms |
| Max latency | 49.95 ms |
| Samples | 5 |

### Real Tokenization Results

| Field | Value |
| ----- | ----- |
| Token count | **35** |
| Tokenization latency | 1.0 ms |
| Classification label | `LABEL_0` |
| Classification score | 0.5887 |
| Classification latency | 222.1 ms |
| Status | **PASS** |

**Input text tokenized:**
```
L_TRLX (carperai/trlx) — 151 files, 17627 source lines, licence MIT, primary language ['Python']
```

**First 20 tokens:**
```
['[CLS]', 'l', '_', 'tr', '##l', '##x', '(', 'carp', '##era', '##i', '/', 'tr', '##l', '##x', ')', '—', '151', 'files', ',', '1762']
```

> Full MMLU/HellaSwag/TruthfulQA/ARC/Winogrande/GSM8K require dedicated GPU.
> These results are CPU inference proxy metrics using distilbert-base-uncased.

---
_Anticloud Benchmark Suite — isolation log — 2026-09-30T15:07:07.146295+00:00_