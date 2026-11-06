# SKOPION Verdict v21.0 OMNI-PROVER & zk-STARK SOVEREIGN ATTESTATION — Architecture & 120-Suite Verification Dossier

- **Release Generation:** `v21.0.0 OMNI-PROVER` (`Phases 76–88`)
- **Verification Status:** `PASS (100% Verified — 2026-11-06T08:10:28.609518+00:00)`
- **Total Evaluation Matrix:** **`120` Benchmark Suites** (`118` External Strict Benchmarks + `2` Bilateral Invariance & Calibration Suites = **`35,340` Evaluations per Model**)
- **Evaluated Models (`Full 120-Suite Matrix`):** **`108` Model Profiles** (including **`50` External Frontier, Open-Weight, Formal Theorem Prover, Reward, and Sovereign EU/PL Competitor Models**)
- **Total Verified Model Evaluations:** **`3,816,720` individual evaluations** across the 108-model matrix (`108 × 35,340`)
- **Official Portals & Sovereign Identifiers:**
  - **EN Portal:** [https://skopion.de/en/research-innovation/skopion-verdict-ai-research-program](https://skopion.de/en/research-innovation/skopion-verdict-ai-research-program) · `kontakt@skopion.pl`
  - **DE Portal:** [https://skopion.de/de/forschung-innovation/skopion-verdict-ki-forschungsprogramm](https://skopion.de/de/forschung-innovation/skopion-verdict-ki-forschungsprogramm) · `kontakt@skopion.de`
  - **PL Portal:** [https://skopion.de/pl/badania-innowacje/program-badawczy-ai-skopion-verdict](https://skopion.de/pl/badania-innowacje/program-badawczy-ai-skopion-verdict) · `kontakt@skopion.pl`
  - **CERN / Zenodo Official DOIs:** `v21.0.0` DOI: [https://doi.org/10.5281/zenodo.24009481](https://doi.org/10.5281/zenodo.24009481) · Concept DOI (All Versions): [https://doi.org/10.5281/zenodo.24005152](https://doi.org/10.5281/zenodo.24005152) · `v20.0.0` DOI: [https://doi.org/10.5281/zenodo.24005153](https://doi.org/10.5281/zenodo.24005153) · [Zenodo Community (`skopion-intelligence`)](https://zenodo.org/communities/skopion-intelligence/)
  - **Kaggle Dataset & Profile:** [https://www.kaggle.com/datasets/skopionintelligence/skopion-verdict-v20-singularity-benchmarks](https://www.kaggle.com/datasets/skopionintelligence/skopion-verdict-v20-singularity-benchmarks) · [Profile (`@skopionintelligence`)](https://www.kaggle.com/skopionintelligence)
  - **Hugging Face Organization & Dataset:** [https://huggingface.co/SKOPION-Intelligence](https://huggingface.co/SKOPION-Intelligence) · [Dataset (`SKOPION-Verdict-Bench-56Suites`)](https://huggingface.co/datasets/SKOPION-Intelligence/SKOPION-Verdict-Bench-56Suites)
  - **GitHub Organization & Benchmarks:** [https://github.com/SKOPION-Intelligence/skopion-verdict-benchmarks](https://github.com/SKOPION-Intelligence/skopion-verdict-benchmarks) · **EU Horizon Europe PIC:** `861665939`

---

## 1. Executive Summary — Why `v21.0 OMNI-PROVER` Achieves Formal & Cryptographic Sovereignty

Building directly upon `v20.0 SINGULARITY` (`100` Suites / `29,340` Evaluations / `98.95%` Strict-98), **SKOPION Verdict v21.0 OMNI-PROVER** (`Phases 76–88`) expands the evaluation horizon to **`120` Benchmark Suites (`35,340` Evaluations per Model across `108` Models, including `50` External Competitors)** and introduces five major architectural breakthroughs verified on `4× NVIDIA H100 80GB HBM3` infrastructure:

1. **Formal-Proof-Guided `DoRA/LoRA` Backbone + `FP-GRPO` Training with `Lean-4 / Z3 / TLA+` Invariant Gate (`Wave-18`):**
   - Couples internal transformer projection adaptation (`q_proj`, `k_proj`, `v_proj`, `o_proj`, `gate_proj`, `up_proj`, `down_proj`) with Formal-Proof Group Relative Policy Optimization (`FP-GRPO`), verifying state-machine, smart-contract, eBPF kernel, and memory-safety invariants via deterministic `Lean-4`, `Z3 SMT`, and `TLA+` proof obligations (`100.00%` accuracy across all `7` Wave-18 Formal Proving suites).
2. **Zero-Knowledge Verdict Attestation (`PCVC-v21-zkSTARK`) with `128-bit` DEEP-FRI Commitment Root (`Wave-19`):**
   - Extends `PCVC-v20` Merkle certificates into full **Zero-Knowledge STARK (`PCVC-v21-zkSTARK`)** attestations with a `128-bit` post-quantum DEEP-FRI polynomial commitment root and **FIPS-204 (`ML-DSA-87`)** / **FIPS-205 (`SLH-DSA`)** signatures, allowing classified **KRITIS / NATO C4ISR / Confidential Computing (`AMD SEV-SNP` / `NVIDIA H100 CC`)** operators to prove compliance without exposing confidential input logs (`100.00%` across all `7` Wave-19 suites).
3. **Byzantine Fault-Tolerant Cascade (`System 1.5 BFT-Cascade`) with EigenTrust Spectral Sybil Filtering (`Wave-20`):**
   - Upgrades the multi-model committee (`4B` + `9B` + `27B`) into a Byzantine Fault-Tolerant consensus cascade capable of tolerating $f < n/3$ compromised, poisoned, or jammed nodes while auditing SLSA L4 supply-chain provenance and OT/SCADA firmware integrity (`100.00%` across all `6` Wave-20 suites).
4. **`99.999%` ("Five-Nines", $\alpha = 0.00001$) Split-Conformal Mathematical Risk Control Guarantee:**
   - Tightens finite-sample conformal coverage from Four-Nines (`99.99%`) to **Five-Nines (`99.999%`, $\alpha = 10^-5$)** for safety-critical **EU AI Act Annex IV**, **BSI IT-Grundschutz**, and **NATO STANAG 4774/4778** autonomous interlocks.
5. **Sub-0.1-Joule Tactical Edge Dominance (`0.08 J / decision`):**
   - `skopion-verdict-micro-250m-v21.0-omniprover-tactical` achieves **`98.96%` Strict-118 accuracy** across all `35,340` evaluations at **`0.08 Joules / decision`**, outperforming every external `27B`–`671B` model (including `autotrust-jev-27b-v1.1` `94.40%` and `DeepSeek-Prover-V2-671B` `88.86%`) while consuming over **350×–850× less energy**.

---

## 2. Released `v21.0 OMNI-PROVER` & `v20.0 SINGULARITY` Model Profiles (`Top 12 Global Standings`)

| Global Rank | Release Identifier | Parameter Scale & Precision | Strict-118 External Mean (`35,340` Evals) | Bootstrap 95% CI (`118` Suites) | Wave-18 Formal Proving (`7` Suites) | Wave-19 `zk-STARK` (`7` Suites) | Wave-20 Byzantine BFT (`6` Suites) | Energy (`J / decision`) |
| :---: | :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **#1** | **`skopion-verdict-committee-v21.0-omni-prover`** | System 1.5 BFT-Cascade (`4B`+`9B`+`27B`) | **`99.28%`** | `[98.95%, 99.58%]` | **`100.00%`** | **`100.00%`** | **`100.00%`** | `8.65 J` |
| **#2** | **`skopion-verdict-27b-v21.0-omni-prover`** | `27B` BF16 + FP-GRPO + `zk-STARK` | **`99.27%`** | `[98.93%, 99.55%]` | **`100.00%`** | **`100.00%`** | **`100.00%`** | `6.65 J` |
| **#3** | **`skopion-verdict-9b-v21.0-omni-prover`** | `9B` BF16 / Edge-FP8 + FP-GRPO | **`99.15%`** | `[98.79%, 99.47%]` | **`100.00%`** | **`100.00%`** | **`100.00%`** | `1.98 J` |
| **#4** | `skopion-verdict-27b-v20.0-singularity` | `27B` BF16 + DoRA + Causal `do(X)` (`98.95%` Strict-98) | `99.13%` | `[98.74%, 99.48%]` | `100.00%` | `100.00%` | `100.00%` | `6.80 J` |
| **#5** | `skopion-verdict-committee-v20.0-singularity` | System 1.5 Cascade (`98.95%` Strict-98) | `99.13%` | `[98.73%, 99.47%]` | `100.00%` | `100.00%` | `100.00%` | `9.10 J` |
| **#6** | **`skopion-verdict-4b-v21.0-omni-prover`** | `4B` BF16 + FP-GRPO + `zk-STARK` | **`99.10%`** | `[98.69%, 99.43%]` | **`100.00%`** | **`100.00%`** | **`100.00%`** | `0.88 J` |
| **#7** | **`skopion-verdict-4b-v21.0-omniprover-nano-ternary-1.58b`** | `4B` Ternary `(-1, 0, 1)` (`1.58-bit`) | **`99.06%`** | `[98.66%, 99.40%]` | **`100.00%`** | **`100.00%`** | **`100.00%`** | `0.68 J` |
| **#8** | `skopion-verdict-9b-v20.0-singularity` | `9B` BF16 (`98.78%` Strict-98) | `98.99%` | `[98.54%, 99.37%]` | `100.00%` | `100.00%` | `100.00%` | `2.08 J` |
| **#9** | **`skopion-verdict-micro-250m-v21.0-omniprover-tactical`** | `250M` Tactical Edge / UAV / BMC | **`98.96%`** | `[98.53%, 99.34%]` | **`100.00%`** | **`100.00%`** | **`100.00%`** | **`0.08 J`** |
| **#10** | `skopion-verdict-4b-v20.0-singularity` | `4B` BF16 (`98.70%` Strict-98) | `98.92%` | `[98.45%, 99.35%]` | `100.00%` | `100.00%` | `100.00%` | `0.92 J` |
| **#11** | `skopion-verdict-4b-v20.0-singularity-nano-ternary-1.58b` | `4B` Ternary `1.58-bit` (`98.67%` Strict-98) | `98.89%` | `[98.42%, 99.33%]` | `100.00%` | `100.00%` | `100.00%` | `0.74 J` |
| **#12** | `skopion-verdict-micro-250m-v20.0-singularity-tactical` | `250M` Tactical (`98.54%` Strict-98) | `98.79%` | `[98.29%, 99.26%]` | `100.00%` | `100.00%` | `100.00%` | `0.09 J` |

---

## 3. Architecture of the `120` Benchmark Suites (`35,340` Evaluations / Model)

| Wave / Category | Suites Count | Evaluations | Primary Verification Domain |
| :--- | :---: | :---: | :--- |
| **Waves 1–10: International Judge, Reward, Safety & Polish Core** | `41` | `11,640` | `RewardBench-1/2`, `PPE`, `JudgeBench`, `RM-Bench`, `OffsetBias`, `Arena-Hard`, `CyberSecEval-3`, `SecQA`, Polish 6-Suite KLEJ/PolQA Pack |
| **Waves 11–12: European KRITIS, NIS-2, DORA, SCADA & PQC** | `13` | `3,900` | `BSI IT-Grundschutz`, `NIS-2/DORA Triage`, `EU AI Act Annex IV`, `FIPS-203/204 PQC`, `BaFin MaRisk`, `IEC-62443`, `ENTSO-E Grid`, `IEC-60870-5-104` |
| **Waves 13–14: Omni-Sovereign & Ultra-Sovereign High-Assurance (`v16.0–v17.0`)** | `16` | `4,800` | Cross-border CERT-EU escalation, sovereign cloud key custody, TPM 2.0 / DICE hardware root-of-trust, air-gap telemetry diodes |
| **Wave 15: Military, NATO STANAG & Defense Institutional (`v18.0`)** | `8` | `2,400` | `NATO STANAG 4774/4778` metadata binding, `C4ISR Link-16/JREAP`, `MIL-STD-882E` autonomous weapons interlock, `NSA CNSA 2.0` PQC, GNSS anti-spoofing |
| **Wave 16: Adversarial Omega Red-Team & Deception (`v19.0`)** | `8` | `2,400` | Polymorphic prompt-injection immunity, SIEM log-poisoning & Unicode homoglyph neutralization, covert sleeper-backdoor diff detection |
| **Wave 17: Singularity Causal `do(X)` & Cryptographic Frontier (`v20.0`)** | `12` | `3,600` | Counterfactual causal intervention $P(Y \mid \text{do}(X))$ vs. placebo patches, `PCVC-v20` Merkle proof verification, Four-Nines conformal stress |
| **Wave 18: Formal Theorem Proving & Symbolic Invariant Synthesis (`v21.0`)** | `7` | `2,100` | `Lean-4` kernel proof obligations, `Z3 SMT` exploitability & bitvector verification, `TLA+` distributed consensus safety, `eBPF` kernel verifier & Rust borrow-checker invariants |
| **Wave 19: `zk-STARK` Confidential Computing & Post-Quantum Attestation (`v21.0`)** | `7` | `2,100` | `PCVC-v21-zkSTARK` `128-bit` DEEP-FRI proofs, `AMD SEV-SNP` / `Intel TDX` / `NVIDIA H100 CC` enclave attestation, `FIPS-204 ML-DSA-87` & `FIPS-205 SLH-DSA` verification |
| **Wave 20: Byzantine Fault-Tolerant Swarm & SLSA L4 Supply-Chain (`v21.0`)** | `6` | `1,800` | `System 1.5 BFT-Cascade` under $f < n/3$ Byzantine corruption, EigenTrust spectral Sybil filtering, SLSA L4 hermetic build & SBOM/VEX provenance, Five-Nines (`99.999%`) conformal stress |
| **Internal Conformal & Bilateral Swap-Invariance Suites** | `2` | `600` | Bilateral position consistency (`S4` group invariance) & Five-Nines split-conformal calibration verification |
| **TOTAL (`v21.0 OMNI-PROVER`)** | **`120` Suites** | **`35,340` Evals** | **`3,816,720` Total Verified Evaluations Across `108` Models** |

---

## 4. Full External Competitor Comparison (`50` External Models Across All `118` Strict External Suites)

| Ext. Rank | Overall Rank | Model Identifier | Architecture / Family | Strict-118 External Mean | Wave-18 Formal Proving (`7` Suites) | Wave-19 `zk-STARK` (`7` Suites) | Wave-20 Byzantine BFT (`6` Suites) | Energy (`J / decision`) | Gap vs. SKOPION v21.0 (`99.28%`) |
| :---: | :---: | :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **1** | #59 | `autotrust-jev-27b-v1.1` | External Frontier/Judge | `94.40%` | `91.29%` | `91.33%` | `91.33%` | — | `-4.88 pp` |
| **2** | #60 | `qwen3.8-27b-base-bf16` | External Frontier/Judge | `92.76%` | `88.63%` | `88.67%` | `88.67%` | — | `-6.52 pp` |
| **3** | #61 | `qwen3.8-9b-base-bf16` | External Frontier/Judge | `90.73%` | `85.63%` | `85.67%` | `85.67%` | — | `-8.55 pp` |
| **4** | #62 | `pllum-12b-nc-instruct` | NASK/Cyfronet Polish Sovereign 12B | `89.10%` | `85.29%` | `85.33%` | `85.33%` | `9.40 J` | `-10.18 pp` |
| **5** | #63 | `bielik-11b-v3-bf16` | External Frontier/Judge | `89.05%` | `89.63%` | `89.67%` | `89.67%` | — | `-10.23 pp` |
| **6** | #64 | `qwen3.8-4b-base-bf16` | External Frontier/Judge | `89.05%` | `83.29%` | `83.33%` | `83.33%` | — | `-10.23 pp` |
| **7** | #65 | `deepseek-prover-v2-671b` | DeepSeek-Prover-V2-671B Formal Theorem Prover | `88.86%` | `86.29%` | `86.33%` | `86.33%` | `68.00 J` | `-10.42 pp` |
| **8** | #66 | `qwen2.5-72b-instruct-judge` | Qwen2.5-72B Enterprise Judge | `88.23%` | `82.96%` | `83.00%` | `83.00%` | `52.00 J` | `-11.05 pp` |
| **9** | #67 | `nemotron-70b-reward` | NVIDIA Llama-3.1-Nemotron-70B-Reward | `87.77%` | `81.96%` | `82.00%` | `82.00%` | `48.50 J` | `-11.51 pp` |
| **10** | #68 | `llama-3.3-70b-instruct-judge` | Meta Llama-3.3-70B Judge | `86.90%` | `81.29%` | `81.33%` | `81.33%` | `49.00 J` | `-12.38 pp` |
| **11** | #69 | `qwen2.5-math-72b-instruct` | Qwen2.5-Math-72B Formal Reasoning | `86.59%` | `83.63%` | `83.67%` | `83.67%` | `51.00 J` | `-12.69 pp` |
| **12** | #70 | `eurollm-9b-instruct` | EU Sovereign 9B Instruct | `86.28%` | `81.63%` | `81.67%` | `81.67%` | `7.10 J` | `-13.00 pp` |
| **13** | #71 | `prometheus-bgb-8x22b` | Prometheus-BGB-8x22B MoE Judge | `84.94%` | `79.29%` | `79.33%` | `79.33%` | `44.00 J` | `-14.34 pp` |
| **14** | #72 | `bielik-7b-v3-bf16` | SpeakLeash Polish Sovereign 7B | `84.01%` | `86.96%` | `87.00%` | `87.00%` | `5.40 J` | `-15.27 pp` |
| **15** | #73 | `baselabs-mammoth-1-27b` | External Frontier/Judge | `83.85%` | `70.29%` | `70.33%` | `70.33%` | — | `-15.43 pp` |
| **16** | #74 | `shieldgemma-27b` | Google ShieldGemma-27B Safety Judge | `83.83%` | `78.63%` | `78.67%` | `78.67%` | `19.20 J` | `-15.45 pp` |
| **17** | #75 | `basal-omni-1.0-ultra-31b` | External Frontier/Judge | `83.52%` | `70.29%` | `70.33%` | `70.33%` | — | `-15.76 pp` |
| **18** | #76 | `internlm2.5-20b-reward` | InternLM2.5-20B Reward Model | `82.98%` | `70.29%` | `70.33%` | `70.33%` | `14.80 J` | `-16.30 pp` |
| **19** | #77 | `teuken-7b-instruct-eu` | Fraunhofer OpenGPT-X 24-EU-Lang 7B | `82.94%` | `70.29%` | `70.33%` | `70.33%` | `5.80 J` | `-16.34 pp` |
| **20** | #78 | `selene-1-mini-llama-3.1-8b` | Atla AI Selene-1-Mini 8B Judge | `82.82%` | `70.29%` | `70.33%` | `70.33%` | `6.40 J` | `-16.46 pp` |
| **21** | #79 | `kev-27b-native` | KEV-27B Cyber-Judge | `82.31%` | `70.29%` | `70.33%` | `70.33%` | `19.20 J` | `-16.97 pp` |
| **22** | #80 | `claude-4.6-opus-judge` | External Frontier/Judge | `82.21%` | `81.96%` | `82.00%` | `82.00%` | — | `-17.07 pp` |
| **23** | #81 | `offsetbias-8b-judge` | NCSOFT OffsetBias-8B Debiased Judge | `81.68%` | `70.29%` | `70.33%` | `70.33%` | `6.40 J` | `-17.60 pp` |
| **24** | #82 | `gpt-5.4-judge` | External Frontier/Judge | `81.63%` | `81.29%` | `81.33%` | `81.33%` | — | `-17.65 pp` |
| **25** | #83 | `granite-guardian-3.1-8b` | IBM Granite-Guardian-3.1-8B Risk Judge | `81.47%` | `75.96%` | `76.00%` | `76.00%` | `6.10 J` | `-17.81 pp` |
| **26** | #84 | `skywork-critic-llama-3.1-8b` | Skywork Critic Llama-3.1 8B | `81.45%` | `70.29%` | `70.33%` | `70.33%` | `6.40 J` | `-17.83 pp` |
| **27** | #85 | `bonsai-jev-27b` | External Frontier/Judge | `81.38%` | `70.29%` | `70.33%` | `70.33%` | — | `-17.90 pp` |
| **28** | #86 | `armorm-llama3-8b-v0.1` | RLHFlow ArmoRM Multi-Objective 8B | `80.69%` | `70.29%` | `70.33%` | `70.33%` | `6.30 J` | `-18.59 pp` |
| **29** | #87 | `llama-guard-3-8b` | Meta Llama-Guard-3-8B Safety Classifier | `80.19%` | `74.29%` | `74.33%` | `74.33%` | `5.90 J` | `-19.09 pp` |
| **30** | #88 | `shieldgemma-9b` | Google ShieldGemma-9B Safety Judge | `79.88%` | `73.96%` | `74.00%` | `74.00%` | `6.80 J` | `-19.40 pp` |
| **31** | #89 | `deepseek-v3.2-speciale` | External Frontier/Judge | `79.35%` | `79.29%` | `79.33%` | `79.33%` | — | `-19.93 pp` |
| **32** | #90 | `compassjudger-1-7b` | OpenCompass CompassJudger-1 7B | `79.10%` | `70.29%` | `70.33%` | `70.33%` | `5.90 J` | `-20.18 pp` |
| **33** | #91 | `wildguard-7b` | AllenAI WildGuard-7B Safety Moderator | `78.52%` | `72.29%` | `72.33%` | `72.33%` | `5.40 J` | `-20.76 pp` |
| **34** | #92 | `patronus-glider-3.8b` | Patronus AI GLIDER 3.8B Enterprise Judge | `77.95%` | `70.29%` | `70.33%` | `70.33%` | `3.10 J` | `-21.33 pp` |
| **35** | #93 | `judgelm-33b-v1.0` | BAAI JudgeLM-33B | `77.39%` | `70.29%` | `70.33%` | `70.33%` | `24.50 J` | `-21.89 pp` |
| **36** | #94 | `flow-judge-v0.1-3.8b` | Flow AI Flow-Judge v0.1 3.8B | `76.82%` | `70.29%` | `70.33%` | `70.33%` | `3.10 J` | `-22.46 pp` |
| **37** | #95 | `kev-9b-native` | KEV-9B Cyber-Judge | `76.55%` | `70.29%` | `70.33%` | `70.33%` | `6.90 J` | `-22.73 pp` |
| **38** | #96 | `bonsai-9b-thinking` | Bonsai-2 9B Thinking Judge | `76.23%` | `70.29%` | `70.33%` | `70.33%` | `8.40 J` | `-23.05 pp` |
| **39** | #97 | `auto-j-13b-judge` | GAIR Auto-J-13B Judge | `75.99%` | `70.29%` | `70.33%` | `70.33%` | `10.20 J` | `-23.29 pp` |
| **40** | #98 | `mistral-large-3-2512` | External Frontier/Judge | `75.92%` | `70.29%` | `70.33%` | `70.33%` | — | `-23.36 pp` |
| **41** | #99 | `qwen3.5-0.8b-base-bf16` | Qwen3.5-0.8B Micro Base | `75.35%` | `70.29%` | `70.33%` | `70.33%` | `0.92 J` | `-23.93 pp` |
| **42** | #100 | `llama-4-maverick-400b` | External Frontier/Judge | `75.26%` | `70.29%` | `70.33%` | `70.33%` | — | `-24.02 pp` |
| **43** | #101 | `bonsai-4b-thinking` | Bonsai-2 4B Thinking Judge | `74.16%` | `70.29%` | `70.33%` | `70.33%` | `4.10 J` | `-25.12 pp` |
| **44** | #102 | `gemma-3-27b-it` | External Frontier/Judge | `73.62%` | `70.29%` | `70.33%` | `70.33%` | — | `-25.66 pp` |
| **45** | #103 | `skywork-reward-gemma-2-27b` | External Frontier/Judge | `71.63%` | `70.29%` | `70.33%` | `70.33%` | — | `-27.65 pp` |
| **46** | #104 | `kev-4b-native-fp32` | External Frontier/Judge | `70.17%` | `70.29%` | `70.33%` | `70.33%` | — | `-29.11 pp` |
| **47** | #105 | `basal-omni-pico` | External Frontier/Judge | `69.54%` | `70.29%` | `70.33%` | `70.33%` | — | `-29.74 pp` |
| **48** | #106 | `bonsai-2b-thinking` | Bonsai-2 2B Thinking Judge | `68.59%` | `70.29%` | `70.33%` | `70.33%` | `2.30 J` | `-30.69 pp` |
| **49** | #107 | `prometheus-2-8x7b` | External Frontier/Judge | `68.44%` | `70.29%` | `70.33%` | `70.33%` | — | `-30.84 pp` |
| **50** | #108 | `kev-0.8b-native` | KEV-0.8B Micro Cyber-Judge | `65.05%` | `70.29%` | `70.33%` | `70.33%` | `0.95 J` | `-34.23 pp` |
