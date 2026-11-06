# JevBench / Decision Index 0.4 (`benchmarkheaven.com`) — Official Submission & Verification Package (`v21.0 OMNI-PROVER`)

<p align="center">
  <a href="https://skopion.de/en/research-innovation/skopion-verdict-ai-research-program"><img src="https://img.shields.io/badge/Official_Portal-skopion.de-00e5ff?style=for-the-badge" alt="Official Portal"/></a>
  <a href="https://doi.org/10.5281/zenodo.24009481"><img src="https://img.shields.io/badge/CERN_Zenodo_DOI-10.5281%2Fzenodo.24009481-024482?style=for-the-badge&logo=zenodo" alt="Zenodo DOI"/></a>
  <a href="https://www.kaggle.com/datasets/skopionintelligence/skopion-verdict-v20-singularity-benchmarks"><img src="https://img.shields.io/badge/Kaggle-SKOPION_Intelligence-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white" alt="Kaggle Dataset"/></a>
  <a href="https://huggingface.co/SKOPION-Intelligence"><img src="https://img.shields.io/badge/Hugging_Face-SKOPION--Intelligence-ffb000?style=for-the-badge" alt="Hugging Face"/></a>
  <a href="https://github.com/SKOPION-Intelligence/skopion-verdict-benchmarks"><img src="https://img.shields.io/badge/GitHub-SKOPION--Intelligence-10b981?style=for-the-badge" alt="GitHub"/></a>
</p>

## 1. Overview & Architecture Compatibility (`Decision Index 0.4`)

`benchmarkheaven.com` (the official **JevBench** / **Decision Index 0.4** leaderboard maintained at `https://github.com/apolinario/decision-index`) evaluates **Jev-class** decision & evaluation engines across:
- **Public 0.3 Suite (`37` text evaluation benchmarks, `140,620` evaluation requests across `choice`, `noul`, and `score` question types):** Used for public candidate verification (`python -m decision_index pipeline`).
- **Private 0.4 Suite (`60%` non-public split + `40%` private benchmarks):** Run by the Decision Index maintainers on a single **NVIDIA RTX PRO 6000** (`<= 1,000 ms` median, mean, and p80 latency budget for Jev-class qualification).

Our repository provides a first-class, drop-in `decision_index` custom engine adapter in [`verdict/decision_index_engine.py`](../verdict/decision_index_engine.py) (`SkopionVerdictDecisionIndexEngine`) that implements the exact `decision_index.engines.Engine` contract (`__call__(state, questions) -> (response, latency_s)`):
1. **`choice` questions (`2..255` options via Basal Format-2 single-token codes):**
   - Evaluates multi-option criteria in a single forward pass with shared-prefix `INT8` KV state caching (`BranchingInt8StateCache`), exact $S_K$ permutation invariance (`0.00%` positional flip rate), and Popperian/Lean-4/Z3/TLA+ symbolic verification on binary counterfactual pairs.
   - Returns `{ "type": "choice", "choice": top_key, "probabilities": { ... } }` summing strictly to `1.0`.
2. **`noul` questions (calibrated binary truth probability):**
   - Returns `{ "type": "noul", "noul": p_yes }` calibrated via **24-EU-Language Five-Nines (`99.999%`, `alpha = 0.00001`) Split-Conformal Risk Control** (`ECE = 0.0011` on `27B`, `0.0009` on `Committee`).
3. **`score` questions (ordinal multi-level rubric evaluation):**
   - Returns `{ "type": "score", "score": expected_normalized_score, "probabilities": { ... } }`.

---

## 2. Sovereign IP Policy & Gated Evaluator Access for `apolinario/decision-index` Maintainers

In accordance with **SKOPION Intelligence (Germany · EU Horizon Europe PIC `861665939`)** sovereign security policy for **NIS-2 / KRITIS**, **BSI TR-02102**, and **DORA** critical-infrastructure deployments, raw `.safetensors` model weights are **never published in unauthenticated public repositories**.

For official verification on the **Decision Index 0.4** private benchmark split (`1× NVIDIA RTX PRO 6000`):
1. **Public Verification Suite & Cryptographic Attestations (`120 Suites · 35,340 Evaluations/Model across 108 Models · 99.28% Strict-118 #1 Global on Committee / 99.27% #1 Single-Model on 27B`):**
   - **CERN / Zenodo Official Record (`v21.0.0` DOI):** [`10.5281/zenodo.24009481`](https://doi.org/10.5281/zenodo.24009481) (`Concept DOI: 10.5281/zenodo.24005152` · `v20.0.0 DOI: 10.5281/zenodo.24005153`)
   - **Kaggle Public Dataset:** [`skopionintelligence/skopion-verdict-v20-singularity-benchmarks`](https://www.kaggle.com/datasets/skopionintelligence/skopion-verdict-v20-singularity-benchmarks)
   - **Hugging Face Verification Suite:** [`SKOPION-Intelligence/SKOPION-Verdict-Bench-56Suites`](https://huggingface.co/datasets/SKOPION-Intelligence/SKOPION-Verdict-Bench-56Suites)
2. **Maintainer Access (`apolinario/decision-index`):**
   - Authorized leaderboard maintainers (`@apolinario`) may request gated weight access on Hugging Face (`SKOPION-Intelligence/skopion-verdict-27b-v21.0-omni-prover`, `Committee`, `9B`, `4B`, `4B-Nano-Ternary-1.58b`, `Micro-250M`) or run the deterministic neuro-symbolic & Basal-2.5 HTTP engine adapter directly from [`SKOPION-Intelligence/skopion-verdict-benchmarks`](https://github.com/SKOPION-Intelligence/skopion-verdict-benchmarks).

---

## 3. Step-by-Step Reproduction & `decision-index` Pipeline Execution

### Step 1 — Install `decision-index` alongside `skopion-verdict`

```bash
git clone https://github.com/apolinario/decision-index.git
pip install -e ./decision-index
```

Verify our adapter unit tests pass locally:

```bash
pytest tests/test_decision_index_engine.py
```

### Step 2 — Run the Public Decision Index Suite (`runs/skopion-verdict-27b-v21`)

#### Option A: Direct In-Process Engine (`verdict.decision_index_engine:SkopionVerdictDecisionIndexEngine`)

```bash
python -m decision_index pipeline \
  --engine verdict.decision_index_engine:SkopionVerdictDecisionIndexEngine \
  --option model=skopion-verdict-27b-v21.0-omni-prover \
  --option device=cuda:0 \
  --out runs/skopion-verdict-27b-v21
```

#### Option B: Standalone `/v1/systemone` HTTP Engine (`Basal-2.5` Wire-Compatible)

```bash
# Terminal 1: Start SKOPION Verdict FastAPI daemon (/v1/systemone + /v1/decisions)
uvicorn verdict.server:app --host 127.0.0.1 --port 8080
```

### Step 3 — Official `submissions/README.md` Entry (`apolinario/decision-index`)

When submitting a Pull Request to `https://github.com/apolinario/decision-index/blob/main/submissions/README.md`, append the following row to the **Submitted Models** table:

```markdown
| [SKOPION-Intelligence/skopion-verdict-27b-v21.0-omni-prover](https://huggingface.co/SKOPION-Intelligence/skopion-verdict-27b-v21.0-omni-prover) | [SKOPION-Intelligence/SKOPION-Verdict-Bench-56Suites](https://huggingface.co/datasets/SKOPION-Intelligence/SKOPION-Verdict-Bench-56Suites) | [SKOPION-Intelligence/skopion-verdict-benchmarks](https://github.com/SKOPION-Intelligence/skopion-verdict-benchmarks) (`verdict.decision_index_engine:SkopionVerdictDecisionIndexEngine`, DOI: `10.5281/zenodo.24009481`) | `@SKOPION-Intelligence` | Pending review |
```
