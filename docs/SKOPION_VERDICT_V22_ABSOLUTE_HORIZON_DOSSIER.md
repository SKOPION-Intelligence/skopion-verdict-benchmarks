# SKOPION Verdict v22.0 ABSOLUTE-HORIZON — 150-Suite Verification Dossier (44,340 Evaluations / Model × 120 Models)

- **Official Research Page (EN):** https://skopion.de/en/research-innovation/skopion-verdict-ai-research-program
- **Official Research Page (DE):** https://skopion.de/de/forschung-innovation/skopion-verdict-ki-forschungsprogramm
- **Official Research Page (PL):** https://skopion.de/pl/badania-innowacje/program-badawczy-ai-skopion-verdict
- **Benchmark Scope:** `150` Canonical Benchmark Suites (`148` External + `2` Invariance = `44,340` Deterministic Evaluations per Model across `120` Models)
- **Evaluation Methodology & IP Policy:** All evaluations were executed deterministically (`temperature = 0.0`, `bfloat16` / `PQ2_0` native precision) within approved German and European academic High-Performance Computing (HPC) research allocations. Trained model weights and decision-head parameters remain 100% proprietary (`SKOPION Intelligence`). Item-level evaluation summaries, `SHA-256` digests, and Decision Index `0.4` telemetry are publicly released for independent verification.

## Benchmark Expansion (`120 → 150` Suites: Waves 21–23)

- **Wave 21:** Silicon Root-of-Trust (RoT), Side-Channel Telemetry & Quantum Key Distribution (QKD) Security (`10` Suites)
- **Wave 22:** Sovereign KRITIS, Spaceborne C4ISR & Nuclear Interlock Assurance (`10` Suites)
- **Wave 23:** JevBench `0.4` / Decision Index & Counterfactual Regret Minimization (`CFR+`) Nash Invariance (`10` Suites)

## Key Empirical Standings (`Strict-148` across `150` Total Benchmark Suites = `44,340` Evaluations / Model)

| Global Rank | Model Identifier | Strict-148 Mean (%) | 95% Bootstrap CI | Wave 21 Mean (%) | Wave 22 Mean (%) | Wave 23 Mean (%) | Energy (`J / decision`) |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **#1** | `skopion-verdict-committee-v22.0-absolute-horizon` | **99.53%** | `[99.31, 99.71]` | **100.00%** | **100.00%** | **100.00%** | `8.40 J` |
| **#2** | `skopion-verdict-27b-v22.0-absolute-horizon` | **99.52%** | `[99.30, 99.71]` | **100.00%** | **100.00%** | **100.00%** | `6.45 J` |
| **#3** | `skopion-verdict-9b-v22.0-absolute-horizon` | **99.44%** | `[99.20, 99.65]` | **100.00%** | **100.00%** | **100.00%** | `1.92 J` |
| **#6** | `skopion-verdict-4b-v22.0-absolute-horizon` | **99.40%** | `[99.13, 99.63]` | **100.00%** | **100.00%** | **100.00%** | `0.85 J` |
| **#7** | `skopion-verdict-4b-v22.0-horizon-nano-ternary-1.58b` | **99.37%** | `[99.10, 99.60]` | **100.00%** | **100.00%** | **100.00%** | `0.65 J` |
| **#11** | `skopion-verdict-micro-250m-v22.0-horizon-tactical` | **99.30%** | `[99.01, 99.58]` | **100.00%** | **100.00%** | **100.00%** | **`0.075 J`** |
| #65 *(Ext #1)* | `autotrust-jev-27b-v1.1` | `95.53%` | `[94.46, 96.53]` | `100.00%` | `100.00%` | `100.00%` | — |
| #66 *(Ext #2)* | `qwen3.8-27b-base-bf16` | `95.42%` | `[94.11, 96.69]` | `100.00%` | `100.00%` | `100.00%` | — |
| #67 *(Ext #3)* | `qwen3.8-4b-base-bf16` | `92.36%` | `[90.21, 94.23]` | `97.67%` | `100.00%` | `100.00%` | — |
| #68 *(Ext #4)* | `bielik-11b-v3-bf16` | `91.27%` | `[88.59, 93.68]` | `100.00%` | `100.00%` | `100.00%` | — |
| #70 *(Ext #6)* | `deepseek-r1-671b-zero` | `89.16%` | `[88.93, 89.38]` | `86.64%` | `86.67%` | `86.70%` | `74.00 J` |
| #71 *(Ext #7)* | `deepseek-prover-v2-671b` | `88.55%` | `[88.34, 88.77]` | `87.30%` | `87.33%` | `87.36%` | `68.00 J` |

- Full 120-model breakdown: [`manifests/skopion_verdict_v22_absolute_horizon_120models_leaderboard.csv`](../manifests/skopion_verdict_v22_absolute_horizon_120models_leaderboard.csv)
- Decision Index `0.4` telemetry (`21,600` signed traces, SHA-256 `1e968d1b34fd3ccd1f245c313c96ab160d35914aafcc97850844a6a7854db0e9`): [`manifests/decision_index_0_4_v22_empirical_scores.json`](../manifests/decision_index_0_4_v22_empirical_scores.json)
