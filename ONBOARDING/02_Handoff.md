# Upstream Edits

**Project:** `L_TRLX`  
**Tier:** TIER_5_WORLD_NEURO_EMBODIED  
**Identity:** Upstream `carperai/trlx` @ `3340c2f3a56d` (MIT)

## Applied patches

| Patch | Target | Kind | Behaviour change | Test |
| --- | --- | --- | --- | --- |
| `L_TRLX-egress-001` | `UPSTREAM/trlx/_anticloud_egress.py` | behaviour | with ANTICLOUD_OFFLINE=1, any socket connection to a hosted frontier API raises EgressDenied instead of dialling out | `tests/upstream/test_egress_guard.py::test_frontier_host_denied_when_offline` |

Each patch is judged on behaviour, not on volume. A patch that only
writes to the ledger is not counted; `anticloud audit-edits` excludes it
and the project is reported as unimproved rather than as improved.
