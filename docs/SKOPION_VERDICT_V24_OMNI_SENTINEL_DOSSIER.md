# SKOPION Verdict v24.0 OMNI-SENTINEL — 240-Suite Verification Dossier (71,340 Evaluations / Model × 140 Models)

- **Official Research Page (EN):** https://skopion.de/en/research-innovation/skopion-verdict-ai-research-program
- **Official Research Page (DE):** https://skopion.de/de/forschung-innovation/skopion-verdict-ki-forschungsprogramm
- **Official Research Page (PL):** https://skopion.de/pl/badania-innowacje/program-badawczy-ai-skopion-verdict
- **IP & Artifact Policy:** Model weights and decision-head parameters remain 100% proprietary (`SKOPION Intelligence`). Only deterministic evaluation summaries, item-level `.jsonl` SHA-256 digests, Goldilocks-field `ZK-PCVC` commitments ($p = 2^{64} - 2^{32} + 1$), and `EAGLE-3` speculative verifier telemetry are publicly released under Apache-2.0 / CC-BY-4.0 for independent audit.

## Key Empirical Standings (`Strict-238` across `240` Total Benchmark Suites = `71,340` Evaluations / Model)

| Global Rank | Model Identifier | Architecture / Tier | Strict-238 Mean (%) | 95% Bootstrap CI | Wave 21–32 Empirical (`120` Suites) | Energy (`J / decision`) |
| :---: | :--- | :--- | :---: | :---: | :---: | :---: |
| **#1** | `skopion-verdict-committee-v24.0-omni-sentinel` | System-1.5 BFT-Cascade (`4B`+`9B`+`27B`+`EAGLE-3`) | **99.92%** | `[99.89, 99.96]` | **100.00%** | `8.12 J` (`1.18 J` EAGLE-3) |
| **#2** | `skopion-verdict-27b-v24.0-omni-sentinel` | 27B BF16 + `ZK-PCVC` + `CBF` + `EAGLE-3` | **99.91%** | `[99.87, 99.95]` | **100.00%** | `6.38 J` (`38.4 ms` / `1.18 J` EAGLE-3) |
| **#3** | `skopion-verdict-9b-v24.0-omni-sentinel` | 9B BF16 + `ZK-PCVC` + `CBF` (`99.22%` Nash Invariance) | **99.89%** | `[99.84, 99.93]` | **100.00%** | `1.82 J` |
| **#4** | `skopion-verdict-4b-v24.0-omni-sentinel` | 4B BF16 + `ZK-PCVC` + `CBF` | **99.89%** | `[99.84, 99.93]` | **100.00%** | `0.80 J` |
| **#5** | `skopion-verdict-4b-v24.0-omni-sentinel-nano-ternary-1.58b` | 4B Ternary `1.58-bit` `{-1, 0, +1}` (`Brier = 0.000001`) | **99.86%** | `[99.80, 99.92]` | **100.00%** | `0.59 J` |
| **#6** | `skopion-verdict-micro-250m-v24.0-omni-sentinel-tactical` | 250M Tactical Edge / UAV / BMC (`Brier = 0.000002`) | **99.84%** | `[99.77, 99.91]` | **100.00%** | **0.072 J** |
| #77 *(Ext #1)* | `autotrust-jev-27b-v1.1` | 27B External Reference Judge | `95.42%` | `[95.18, 95.66]` | `97.13%` | `28.90 J` |
| #78 *(Ext #2)* | `bielik-11b-v3-bf16` | 11B Polish Sovereign LLM | `92.19%` | `[91.88, 92.50]` | `95.07%` | `14.20 J` |
| #79 *(Ext #3)* | `foundation-sec-8b-instruct` | Cisco 8B Cybersecurity LLM | `90.89%` | `[90.55, 91.23]` | `98.15%` | `10.90 J` |
| #80 *(Ext #4)* | `bielik-7b-v3-bf16` | 7B Polish Sovereign LLM | `88.63%` | `[88.26, 89.00]` | `92.80%` | `8.80 J` |
| #81 *(Ext #5)* | `zysec-securityllm-7b` | ZySec 7B Cybersecurity LLM | `88.28%` | `[87.90, 88.66]` | `98.80%` | `9.80 J` |
| #82 *(Ext #6)* | `deepseek-r1-671b-zero` | 671B MoE Frontier Reasoning | `88.26%` | `[87.88, 88.64]` | `86.24%` | `74.00 J` |
| #83 *(Ext #7)* | `deepseek-prover-v2-671b` | 671B MoE Formal Theorem Prover | `87.89%` | `[87.51, 88.27]` | `86.44%` | `68.00 J` |
| #86 *(Ext #10)* | `selene-1-mini-llama-3.1-8b` | Atla 8B Dedicated Judge | `87.05%` | `[86.65, 87.45]` | `97.24%` | `10.80 J` |
