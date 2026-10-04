# L5 Narrow / L2 General Classification — L_TRLX
**Platform:** Anticloud | **Tier:** TIER_5_WORLD_NEURO_EMBODIED | **PAX:** 27B
**IP:** USPTO pending 2026, Anticloud FZ LLE, 0-1.gg | **License:** Apache-2.0

## L5 Narrow
L_TRLX provides the distributed RLHF training infrastructure for PAX 27B using the TRL-X framework. Narrow scope: PAX 27B RLHF on Anticloud hardware with Anticloud-domain reward functions. Supports PPO and ILQL algorithms.

## L2 General
L2 General: L_TRLX is the training backbone for all PAX 27B alignment work across tiers. K_SAFERLHF, L_PALRLHF, and L_REEF all build on L_TRLX's distributed training primitives.

## PAX 27B Integration
PAX 27B is the model trained by L_TRLX. Anticloud-domain reward functions (safety, helpfulness, factuality) guide the RLHF optimization. Every training checkpoint is AIOSS-chained.

## AIOSS Audit Chain
Every training step (step hash + model checkpoint hash + reward stats hash + policy gradient norm) is chained: H_n = SHA3-256(H_{n-1} || entry_hash_n || timestamp_n).
Offline-verifiable, tamper-evident, zero cloud dependency.

## Regulatory / Compliance
EU AI Act Art. 15 (AI robustness). ISO/IEC 42001 (AI training governance).
