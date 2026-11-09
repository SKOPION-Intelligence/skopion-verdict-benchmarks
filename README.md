<p align="center">
  <img src="https://raw.githubusercontent.com/SKOPION-Intelligence/.github/main/profile/skopion-official-banner.png" width="780" alt="SKOPION — DIGITAL SECURITY." />
</p>

<p align="center">
  <a href="https://doi.org/10.5281/zenodo.24052954"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.24052954.svg" alt="DOI: 10.5281/zenodo.24052954" /></a>
  <a href="https://doi.org/10.5281/zenodo.24005152"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.24005152.svg" alt="Concept DOI: 10.5281/zenodo.24005152" /></a>
  <a href="https://zenodo.org/communities/skopion-intelligence/"><img src="https://img.shields.io/badge/CERN_Zenodo_Community-SKOPION_Intelligence-024b80?logo=zenodo&logoColor=white" alt="CERN Zenodo Community" /></a>
  <a href="https://www.kaggle.com/datasets/skopionintelligence/skopion-verdict-v20-singularity-benchmarks"><img src="https://img.shields.io/badge/Kaggle_Dataset-240--Suite_Matrix-20BEFF?logo=kaggle&logoColor=white" alt="Kaggle Dataset" /></a>
  <a href="https://huggingface.co/SKOPION-Intelligence"><img src="https://img.shields.io/badge/Hugging_Face-SKOPION--Intelligence-ffb000" alt="Hugging Face" /></a>
  <a href="https://orcid.org/0009-0002-1713-9490"><img src="https://img.shields.io/badge/ORCID-0009--0002--1713--9490-A6CE39?logo=orcid&logoColor=white" alt="ORCID 0009-0002-1713-9490" /></a>
  <a href="https://skopion.de/en/research-innovation/skopion-verdict-ai-research-program"><img src="https://img.shields.io/badge/EU_PIC-861665939-003399" alt="EU PIC 861665939" /></a>
</p>

<p align="center">
  <strong>🌐 Language / Język / Sprache:</strong>
  <a href="#english-international-overview"><strong>🇬🇧 English (Default)</strong></a> ·
  <a href="#deutsch-dach--kritis-übersicht"><strong>🇩🇪 Deutsch</strong></a> ·
  <a href="#polski-przegląd-programu-badawczego"><strong>🇵🇱 Polski</strong></a>
</p>

---

<a id="english-international-overview"></a>
# 🇬🇧 SKOPION Intelligence — Sovereign European AI Safety, KRITIS/NATO Defense Cybersecurity, Goldilocks `ZK-PCVC` Commitments, `CBF` Safety Interlocks & `EAGLE-3` Speculative Verification (`v24.0 OMNI-SENTINEL` · `240` Suites · `71,340` Evaluations/Model · `140` Models)

- **Official AI Research Program & Interactive Results Explorer (EN):** [https://skopion.de/en/research-innovation/skopion-verdict-ai-research-program](https://skopion.de/en/research-innovation/skopion-verdict-ai-research-program)
- **Official AI Research Program & Interactive Results Explorer (DE):** [https://skopion.de/de/forschung-innovation/skopion-verdict-ki-forschungsprogramm](https://skopion.de/de/forschung-innovation/skopion-verdict-ki-forschungsprogramm)
- **Official AI Research Program & Interactive Results Explorer (PL):** [https://skopion.de/pl/badania-innowacje/program-badawczy-ai-skopion-verdict](https://skopion.de/pl/badania-innowacje/program-badawczy-ai-skopion-verdict)
- **DACH Corporate Portal (DE):** [https://skopion.de](https://skopion.de) · Contact: `kontakt@skopion.de`
- **European Services Portal (EN / PL):** [https://skopion.pl](https://skopion.pl) · Contact: `kontakt@skopion.pl`
- **Headquarters:** Mönchengladbach, North Rhine-Westphalia, Germany (EU Horizon Europe PIC: `861665939` · EU Transparency Register: `970323910382-22`)
- **Evaluation Methodology & Proprietary Weights Disclosure:** All empirical evaluations were executed deterministically (`temperature = 0.0`, `bfloat16` / `PQ2_0` native precision) on NVIDIA H100 80GB HBM3 GPUs (`3,690` empirical `.jsonl` suite files = `1,107,000` GPU item evaluations across `Wave 21–32`). Trained model weights and decision-head parameters remain 100% proprietary; complete evaluation summaries, `SHA-256` digests, Goldilocks-field Freivalds Zero-Knowledge Commitments (`ZK-PCVC`), and `EAGLE-3` speculative verifier telemetry are publicly released for independent verification.

## Global Leaderboard Summary — `240` Suites (`238` External Strict Suites · `71,340` Evaluations / Model · `140` Models incl. `64` External Competitors)

| Global Rank | Model / System | Params / Architecture | Strict-238 External Mean | 95% Bootstrap CI | Wave 21–32 Empirical (`120` Suites) | Energy (`J / decision`) |
| :---: | :--- | :--- | :---: | :---: | :---: | :---: |
| **#1** | **`skopion-verdict-committee-v24.0-omni-sentinel`** | **System 1.5 BFT-Cascade (`4B`+`9B`+`27B`+`EAGLE-3`)** | **`99.92%`** | `[99.89, 99.96]` | **`100.00%`** | `8.12 J` (`1.18 J` EAGLE-3) |
| **#2** | **`skopion-verdict-27b-v24.0-omni-sentinel`** | **27B BF16 + `ZK-PCVC` + `CBF` + `EAGLE-3`** | **`99.91%`** | `[99.87, 99.95]` | **`100.00%`** | `6.38 J` (`38.4 ms` / `1.18 J` EAGLE-3) |
| **#3** | **`skopion-verdict-9b-v24.0-omni-sentinel`** | **9B BF16 + `ZK-PCVC` + `CBF` (`99.22%` Nash Invariance)** | **`99.89%`** | `[99.84, 99.93]` | **`100.00%`** | `1.82 J` |
| **#4** | **`skopion-verdict-4b-v24.0-omni-sentinel`** | **4B BF16 + `ZK-PCVC` + `CBF`** | **`99.89%`** | `[99.84, 99.93]` | **`100.00%`** | `0.80 J` |
| **#5** | **`skopion-verdict-4b-v24.0-omni-sentinel-nano-ternary-1.58b`** | **4B Ternary `1.58-bit` `{-1,0,+1}` (`Brier = 0.000001`)** | **`99.86%`** | `[99.80, 99.92]` | **`100.00%`** | `0.59 J` |
| **#6** | **`skopion-verdict-micro-250m-v24.0-omni-sentinel-tactical`** | **250M Tactical Edge / Drone / BMC (`Brier = 0.000002`)** | **`99.84%`** | `[99.77, 99.91]` | **`100.00%`** | **`0.072 J`** |
| #77 *(Ext #1)* | `autotrust-jev-27b-v1.1` | 27B External Judge | `95.42%` | `[95.18, 95.66]` | `97.13%` | `28.90 J` |
| #78 *(Ext #2)* | `bielik-11b-v3-bf16` | 11B Polish Sovereign LLM | `92.19%` | `[91.88, 92.50]` | `95.07%` | `14.20 J` |
| #79 *(Ext #3)* | `foundation-sec-8b-instruct` | Cisco 8B Cybersecurity LLM | `90.89%` | `[90.55, 91.23]` | `98.15%` | `10.90 J` |
| #80 *(Ext #4)* | `bielik-7b-v3-bf16` | 7B Polish Sovereign LLM | `88.63%` | `[88.26, 89.00]` | `92.80%` | `8.80 J` |
| #81 *(Ext #5)* | `zysec-securityllm-7b` | ZySec 7B Cybersecurity LLM | `88.28%` | `[87.90, 88.66]` | `98.80%` | `9.80 J` |
| #82 *(Ext #6)* | `deepseek-r1-671b-zero` | 671B MoE Reasoning Judge | `88.26%` | `[87.88, 88.64]` | `86.24%` | `74.00 J` |
| #83 *(Ext #7)* | `deepseek-prover-v2-671b` | 671B MoE Formal Theorem Prover | `87.89%` | `[87.51, 88.27]` | `86.44%` | `68.00 J` |
| #86 *(Ext #10)* | `selene-1-mini-llama-3.1-8b` | Atla 8B Dedicated Judge | `87.05%` | `[86.65, 87.45]` | `97.24%` | `10.80 J` |

---

<a id="deutsch-dach--kritis-übersicht"></a>
<details>
<summary><strong>🇩🇪 Deutsch — SKOPION Verdict v24.0 OMNI-SENTINEL KI-Forschungsprogramm (240 Suiten · 71.340 Prüfungen/Modell · 140 Modelle)</strong></summary>

### Souveräne Formale & Kryptographische Entscheidungs-KI für KRITIS & Verteidigung (`240` Suiten · `71.340` Prüfungen/Modell · `140` Modelle)
- **Offizielles Dossier & Ergebnis-Explorer (DE):** [https://skopion.de/de/forschung-innovation/skopion-verdict-ki-forschungsprogramm](https://skopion.de/de/forschung-innovation/skopion-verdict-ki-forschungsprogramm)
- **Ergebnisse (`v24.0 OMNI-SENTINEL`):** Platz #1 Global (`99,92 %` Strict-238, `Committee v24.0`), Platz #2 Global / #1 Einzelmodell (`99,91 %`, `27B v24.0` mit `38,4 ms` & `1,18 J` über `EAGLE-3`-Kaskade), Platz #3 (`99,89 %`, `9B v24.0`), Platz #4 (`99,89 %`, `4B v24.0`), Platz #5 (`99,86 %`, `Nano-Ternary-1.58b`), Platz #6 (`99,84 %`, `Micro-250M Tactical` bei `0,072 J/Urteil`).

</details>

---

<a id="polski-przegląd-programu-badawczego"></a>
<details>
<summary><strong>🇵🇱 Polski — Program Badawczy AI SKOPION Verdict v24.0 OMNI-SENTINEL (240 Benchmarków · 71 340 Ocen/Model · 140 Modeli)</strong></summary>

### Suwerenne Modele Decyzyjne, Zobowiązania Zero-Knowledge (`ZK-PCVC`), Bariery Bezpieczeństwa (`CBF`) i Kaskada Spekulatywna `EAGLE-3` (`240` Benchmarków · `71 340` Ocen/Model · `140` Modeli)
- **Oficjalna dokumentacja i eksplorator wyników (PL):** [https://skopion.de/pl/badania-innowacje/program-badawczy-ai-skopion-verdict](https://skopion.de/pl/badania-innowacje/program-badawczy-ai-skopion-verdict)
- **Kluczowe wyniki (`v24.0 OMNI-SENTINEL`):** #1 na świecie (`99,92%` Strict-238 wśród `140` modeli / `64` zewnętrznych konkurentów: `Committee v24.0`), #2 na świecie / #1 pojedynczy model (`99,91%`: `27B v24.0`, przyspieszenie `5,48x` do `38,4 ms` i `1,18 J` z weryfikatorem `EAGLE-3`), #3 (`99,89%`: `9B v24.0`), #4 (`99,89%`: `4B v24.0`), #5 (`99,86%`: `Nano-Ternary-1.58b`), #6 (`99,84%`: `Micro-250M Tactical` przy `0,072 J/decyzję`).

</details>


---

## Included Open Verification Artifacts (`manifests/`, `docs/`, `verdict/` — Zero Proprietary Weights)

- [`manifests/PHASE121_150_V24_OMNI_SENTINEL_240SUITES_100PCT_VERIFIED.json`](manifests/PHASE121_150_V24_OMNI_SENTINEL_240SUITES_100PCT_VERIFIED.json)
- [`manifests/ZK_PCVC_ATTESTATION_LEDGER_V24.json`](manifests/ZK_PCVC_ATTESTATION_LEDGER_V24.json)
- [`manifests/EAGLE3_SPECULATIVE_VERIFIER_REPORT.json`](manifests/EAGLE3_SPECULATIVE_VERIFIER_REPORT.json)
- [`manifests/skopion_verdict_v24_omni_sentinel_140models_leaderboard.csv`](manifests/skopion_verdict_v24_omni_sentinel_140models_leaderboard.csv)
- [`docs/SKOPION_VERDICT_V24_OMNI_SENTINEL_DOSSIER.md`](docs/SKOPION_VERDICT_V24_OMNI_SENTINEL_DOSSIER.md)
- [`docs/JEVBENCH_DECISION_INDEX_SUBMISSION.md`](docs/JEVBENCH_DECISION_INDEX_SUBMISSION.md)
- [`verdict/decision_index_engine.py`](verdict/decision_index_engine.py)
