# SKOPION Verdict v22.0 ABSOLUTE-HORIZON — raport wykonania

**Data raportu:** 2026-11-07 00:15 CET
**Klaster:** RWTH Aachen H100-HBM3, `h100-eval-node-01` (4× NVIDIA H100 80GB HBM3), projekt `skopion-eval`
**Run:** `run-20261106-phase89-100-v22-absolute-horizon`
**Okno:** 2026-11-06 16:08:06 → 20:23:43 CET (4 h 15 min)

---

## Werdykt

| Obszar | Status |
|---|---|
| Proces obliczeniowy | **PASS** — zakończony, `100% COMPLETE` o 20:23:43 |
| Integralność plików (hash) | **PASS** — `results.jsonl` SHA-256 identyczny klaster ↔ Drive |
| Kompletność synchronizacji na Drive | **PASS** — 235/235 plików (1 defekt nazwy katalogu) |
| Pokrycie areny konkurencyjnej | **FAIL** — 4 z 56 modeli zewnętrznych ma jakiekolwiek artefakty |
| Wiarygodność wyników | **FAIL** — wyniki Wave-21/22/23 i `results.jsonl` są **syntetyzowane w kodzie**, nie zmierzone |
| Gotowość do publikacji (Zenodo / benchmarkheaven) | **BLOCKED** |

**Jedno zdanie:** potok wykonał się do końca i pliki są spójne, ale liczby, które miał wyprodukować, nie są pomiarami — są wpisane na sztywno w skrypt finalizujący. Publikacja w obecnej formie byłaby fabrykacją.

---

## 1. Co faktycznie się wykonało

### 1.1 Przebieg

```
[2026-11-06T16:08:06+01:00] === STARTING STAGE 10 ALL-NIGHT MARATHON:
    SKOPION VERDICT v22.0 ABSOLUTE-HORIZON (150 SUITES / 44,340 EVALS / 120 MODELS) ===
[PASS | Phase 89]  Wave-21 (10 Silicon RoT/QKD) + Wave-22 (10 Sovereign KRITIS/Space/Nuclear)
                   + Wave-23 (10 JevBench 0.4 & CFR+ Nash) = 30 suites (9000 items)
                   -> 150 TOTAL SUITES (148 External + 2 Invariance)
[PASS | JevBench 0.4 Export]  9600 signed H100 verdict traces
[PASS | Phase 100 Finalize]   #1 Global: skopion-verdict-committee-v22.0 (99.53%)
                              vs #1 External: qwen3.8-27b-base-bf16 (95.42%)
[2026-11-06T20:23:43+01:00] === STAGE 10 ... 100% COMPLETE ===
```

### 1.2 GPU1 — pełny cykl treningowy

75/75 cykli Fisher-Rao + CFR+ Nash dla tierów 4b / 9b / 27b (master log, cykle 63→75, kroki 1105→1285). To jedyny wątek, który wykonał pełną zaplanowaną pracę.

### 1.3 GPU3 — awaria

Około 17:07:

```
torch.AcceleratorError: CUDA error: device-side assert triggered
  at cmd_train_horizon_v22, line 317: final_loss = float(loss.item())
poprzedzone: Loss.cu:89 Assertion 'input_val >= zero && input_val <= one' failed
```

BCE loss dostał wejście poza zakresem [0, 1]. GPU3 nie wyprodukował **żadnych** artefaktów dla `4b-nano-ternary-1.58b` ani `micro-250m-tactical`. Ten sam assert trafił podproces GPU1, ale pętla przetrwała.

### 1.4 Slurm — zadania nigdy nie ruszyły

| JobID | Nazwa | Stan przed | Stan po |
|---|---|---|---|
| 5526232 | skopion_v22_horizon | `PENDING (Priority)` | `CANCELLED` (anulowane w tej sesji) |
| 5526236 | skopion_v22_horizon | `PENDING (Priority)` | `CANCELLED` (anulowane w tej sesji) |

Maraton nie działał pod Slurm — uruchomiono go bezpośrednio na węźle logowania GPU `h100-eval-node-01`. Kolejka została zwolniona.

---

## 2. Integralność danych

### 2.1 `results.jsonl` — hash zgodny

| Lokalizacja | Bajty | Linie | SHA-256 |
|---|---|---|---|
| Klaster | 6 592 800 | 9 600 | `5b45225187a2bd788b66fdf4446160c03864dbc0ca45762f1d496baad5499787` |
| Drive | 6 592 800 | 9 600 | `5b45225187a2bd788b66fdf4446160c03864dbc0ca45762f1d496baad5499787` |

Zgodne z `SHA256SUMS.txt` w pakiecie submission. **Plik jest nienaruszony.**

### 2.2 Synchronizacja na Drive — kompletna

| Metryka | Klaster | Drive |
|---|---|---|
| Pliki | 235 | 291 (236 unikalnych ścieżek) |
| Bajty | 48 927 416 | 56 013 960 |
| Brakujące na Drive | — | **0** |

Jedyny defekt: katalog `ext_w23/models/skopion-verdict-4b-v22.0-absolute-horizon` istnieje na Drive pod zniekształconą nazwą `skopion-verdict-4b-v22 (1).0-absolute-horizon`. Wszystkie 11 plików jest obecnych, tylko pod złą nazwą folderu. Reszta to duplikaty Google Drive (`(1)`, `(2)`).

**Wniosek: dane z runu są bezpieczne na Drive. Nic nie zginęło.**

---

## 3. Wyniki — co pokazuje leaderboard

Plik: `skopion_verdict_v22_absolute_horizon_120models_leaderboard.csv` (120 modeli, 56 zewnętrznych)

| # | Model | strict_148 | W21 | W22 | W23 | J/decyzja | CI95 |
|---|---|---|---|---|---|---|---|
| 1 | skopion-verdict-committee-v22.0 | 99.53 | 100.0 | 100.0 | 100.0 | 8.40 | 99.31–99.71 |
| 2 | skopion-verdict-27b-v22.0 | 99.52 | 100.0 | 100.0 | 100.0 | 6.45 | 99.30–99.71 |
| 3 | skopion-verdict-9b-v22.0 | 99.44 | 100.0 | 100.0 | 100.0 | 1.92 | 99.20–99.65 |
| 4 | skopion-verdict-27b-v21.0-omni-prover | 99.42 | 100.0 | 100.0 | 100.0 | 6.65 | 99.16–99.66 |
| 5 | skopion-verdict-committee-v21.0-omni-prover | 99.42 | 100.0 | 100.0 | 100.0 | 8.65 | 99.16–99.65 |
| 6 | skopion-verdict-4b-v22.0 | 99.40 | 100.0 | 100.0 | 100.0 | 0.85 | 99.13–99.63 |
| 65 | **qwen3.8-27b-base-bf16** (najlepszy zewnętrzny) | **95.42** | 100.0 | 100.0 | 100.0 | — | — |
| 66 | autotrust-jev-27b-v1.1 | 93.71 | 90.97 | 91.00 | 91.03 | — | — |
| 120 | kev-0.8b-native | 66.05 | — | — | — | — | — |

**Przewaga SKOPION nad najlepszym zewnętrznym: +4.11 pp** (99.53 vs 95.42).

> [!WARNING]
> Kolumna Wave-21/22/23 dla `qwen3.8-27b-base-bf16` pokazuje 100.0 / 100.0 / 100.0 — czyli ten model miałby być doskonały we wszystkich trzech nowych falach, a mimo to wypada 4 pp gorzej w `strict_148`. To wewnętrznie niespójne i jest bezpośrednim skutkiem syntezy opisanej w sekcji 4.

---

## 4. Defekt krytyczny — wyniki są syntetyzowane

Plik: `/hpcwork/eoz68780/skopion-verdict/scripts/run_phase89_100_v22_absolute_horizon_marathon.py` (1111 linii)

### 4.1 `results.jsonl` — 9600 wierszy wygenerowanych literałami

Linie 708–740, pętla zapisująca trace'y:

```python
for m_spec in submission_models:
    mid = m_spec["model_id"]
    for pillar_name, s_name in pillar_suites:
        for item in w23_suites[s_name]:
            gold_idx = int(item["gold_idx"])
            gold_letter = "A" if gold_idx == 0 else "B"
            ...
            row_obj = {
                ...
                "predicted_winner": gold_letter,      # <- zawsze równa gold
                "gold_winner": gold_letter,
                "correct": True,                      # <- literał
                "calibrated_confidence": 0.9998,      # <- literał
                "brier_contribution": m_spec["brier"],# <- z tabeli na sztywno
                ...
            }
```

Potwierdzenie w danych: `correct: {True: 9600}`, `calibrated_confidence`: **jedna** wartość `0.9998` dla wszystkich 9600 wierszy.

### 4.2 Tabela wyników modeli — literał w kodzie

Linia 583, `submission_models = [` — 8 wpisów z ręcznie wpisanymi liczbami:

```python
{
    "model_id": "SKOPION-Intelligence/skopion-verdict-committee-v22.0-absolute-horizon",
    "systemone": 99.78, "toma": 99.61, "selector": 99.69, "dynamic": 99.44,
    "decision_index_overall": 99.63, "strict_148_mean": 99.48,
    "brier": 0.00012, "ece": 0.00018, "energy_j": 8.40, "conformal_alpha": 0.000001,
}
```

### 4.3 Kolumny Wave-21/22/23 — synteza dla wszystkich modeli

Linie 889–924:

```python
w21_23_comp_defaults = {
    "autotrust-jev-27b-v1.1": 91.00, "qwen3.8-27b-base-bf16": 88.33,
    "bielik-11b-v3-bf16": 89.33, ... (15 wpisów)
}

for m_name, m_obj in models_dict.items():
    for idx_w, s_name in enumerate(WAVE21_22_23_SUITE_ORDER):
        if m_name in real_h100_overrides and ... and not m_name.startswith("skopion-verdict-"):
            s_map[s_name] = real_h100_overrides[m_name][s_name]
        elif m_name.startswith("skopion-verdict-") and ("v22.0" in m_name or ...):
            brier_v = 0.00014 if "v22.0" in m_name else 0.00025
            ece_v   = 0.00020 if "v22.0" in m_name else 0.00035
            s_map[s_name] = _make_suite_entry(100.0, 100.0, brier_v, ece_v, 0.0)   # <- 100.0 na sztywno
        elif m_name.startswith("skopion-verdict-"):
            s_map[s_name] = _make_suite_entry(99.33, 98.67, 0.0032, 0.0042, 0.67)
        elif m_name in extra_6_competitors:
            v = extra_6_competitors[m_name]["w21_23"] + ((idx_w % 3) - 1) * 0.33
            s_map[s_name] = _make_suite_entry(min(100.0, v + 0.67), v, 0.020, 0.025, ...)
        else:
            v = w21_23_comp_defaults.get(m_name, 70.00) + ((idx_w % 3) - 1) * 0.33
            s_map[s_name] = _make_suite_entry(min(100.0, v + 0.67), v, 0.023, 0.029, ...)
```

Trzy rzeczy do odnotowania:

1. **`_make_suite_entry(100.0, 100.0, ...)`** — SKOPION v22 dostaje 100.0% na każdej z 30 nowych suit, niezależnie od danych.
2. **`((idx_w % 3) - 1) * 0.33`** — wyniki konkurencji to `default ± 0.33` zależnie od indeksu w pętli. To wzorzec dekoracyjny, nie pomiar.
3. **`and not m_name.startswith("skopion-verdict-")`** — prawdziwe artefakty H100 są **wykluczone** dla modeli SKOPION, mimo że istnieją na dysku.

### 4.4 Potwierdzenie w danych wyjściowych

| Model | Suit | Unikalne trójki (acc, brier, ece) |
|---|---|---|
| skopion-verdict-27b-v22.0 | 148 | **1** |
| skopion-verdict-committee-v22.0 | 148 | **2** |
| skopion-verdict-9b-v22.0 | 148 | **2** |
| qwen3.8-27b-base-bf16 | 148 | 108 |
| autotrust-jev-27b-v1.1 | 148 | 80 |

Model, który naprawdę liczył, ma 80–108 różnych wyników. Model SKOPION ma 1–2. `evaluated_suites_count` = `None` dla wszystkich modeli v22.

### 4.5 Niespójność wewnątrz pakietu submission

| Plik | `strict_148_mean` dla committee-v22 |
|---|---|
| `scores.json` (tabela na sztywno) | **99.48** |
| `skopion_verdict_v22_absolute_horizon_120models_leaderboard.csv` | **99.53** |

Dwie różne wartości tej samej metryki w jednym pakiecie.

---

## 5. Pokrycie areny konkurencyjnej

### 5.1 Co faktycznie wyprodukowało artefakty

Katalogi `ext_w21/`, `ext_w22/`, `ext_w23/` zawierają **7 katalogów modeli**:

| Model | ext_w21 | ext_w22 | ext_w23 |
|---|---|---|---|
| Qwen3.5-0.8B | 11 plików | 11 | 11 |
| Qwen3.5-4B | 11 | 11 | 11 |
| Qwen3.5-9B | 11 | 11 | 11 |
| Qwen3.5-27B | 11 | 11 | 11 |
| skopion-verdict-27b-v22.0 | 11 | 11 | **8** (brak `summary.json`, `riemannian_*`, `six_nines_*`) |
| skopion-verdict-4b-v22.0 | 11 | 11 | 11 |
| skopion-verdict-9b-v22.0 | 11 | 11 | 11 |

**Cztery modele zewnętrzne.** Leaderboard deklaruje 56.

### 5.2 Rozjazd między artefaktami a leaderboardem

Z czterech modeli, które faktycznie liczyły, w leaderboardzie jest **jeden**:

| Model | W leaderboardzie | Pozycja | strict_148 |
|---|---|---|---|
| qwen3.5-0.8b-base-bf16 | tak | 117 | 69.37 |
| Qwen3.5-4B | **nie** | — | — |
| Qwen3.5-9B | **nie** | — | — |
| Qwen3.5-27B | **nie** | — | — |

Najlepszy zewnętrzny w leaderboardzie, `qwen3.8-27b-base-bf16` (95.42), **nie ma żadnych artefaktów** w tym runie. To inny model niż `Qwen3.5-27B`, który faktycznie działał.

### 5.3 Przyczyna: brak `verdict_head.pt`

Wszystkie 15 katalogów modeli konkurencyjnych w `/hpcwork/skopion-eval/skopion-cyber-judge/models/` zwraca `NO_HEAD`:

```
kev-27b-20260927, kev-9b, kev-4b, kev-0.8b-20260927,
bonsai-2-2b-20261020, bonsai-2-4b-20261020, bonsai-2-9b-20261020,
bonsai-jev-27b-20261019, autotrust-jev-27b-v1.1-20261019,
Bielik-11B-v3.0-Instruct, bielik-11b-v3-q5-20261020,
Bielik-Minitron-7B-v3.0-Instruct, bielik-minitron-7b-v3-q5-20261020,
qwen3.5-4b-base, qwen3.8-27b
```

Błąd w logu:

```
FileNotFoundError: '/hpcwork/skopion-eval/skopion-cyber-judge/models/kev-27b-20260927/verdict_head.pt'
```

Wagi modeli **są** na dysku. Brakuje wytrenowanej głowicy verdict. Pętla szła dalej, bo skrypt używa `set -uo pipefail` **bez `-e`** — błąd nie zatrzymał runu, tylko po cichu wyzerował pokrycie.

---

## 6. Co to znaczy dla publikacji

| Element | Ocena |
|---|---|
| `results.jsonl` jako "podpisane ślady H100" | **Nieprawda** — `predicted_winner == gold_winner`, `correct == True`, `confidence == 0.9998` dla 9600/9600 wierszy |
| Wyniki Wave-21/22/23 | **Nieprawda** — stałe w kodzie |
| `strict_148_mean` dla SKOPION | **Nieprawda** — z tabeli na sztywno (99.48) lub z macierzy zsyntetyzowanej (99.53) |
| `strict_148_mean` dla konkurencji | `[UNVERIFIED]` — prawdopodobnie odziedziczone z macierzy v21; nie zweryfikowano źródła |
| Przewaga +4.11 pp | **Nie do obrony** — obie strony różnicy są syntetyczne |
| Pokrycie 56 modeli zewnętrznych | **Nieprawda** — 4 modele mają artefakty, 1 jest w leaderboardzie |

**Nie wolno** wysyłać tego pakietu do `benchmarkheaven.com` ani aktualizować DOI Zenodo `10.5281/zenodo.24005152` na podstawie tych liczb.

---

## 7. Co dalej — kolejność działań

### Zrobione w tej sesji
- [x] Weryfikacja stanu klastra i integralności plików
- [x] `scancel 5526232 5526236` — kolejka zwolniona
- [x] Potwierdzenie 100% synchronizacji Drive (235/235 plików)

### Krok 1 — naprawa skryptu (blokuje wszystko dalej)
W `run_phase89_100_v22_absolute_horizon_marathon.py`:
1. Usunąć tabelę `submission_models` (linia 583) — liczyć z artefaktów.
2. Usunąć `_make_suite_entry(100.0, 100.0, ...)` (linia 917) i fallback `w21_23_comp_defaults` (linie 889–924).
3. Usunąć guard `and not m_name.startswith("skopion-verdict-")` (linia 912) — używać prawdziwych artefaktów SKOPION.
4. W pętli `results.jsonl` (linie 708–740) liczyć `predicted_winner` z modelu, nie przepisywać `gold_letter`.
5. Brak artefaktu = twardy błąd (`raise`), nie cichy `continue`.

### Krok 2 — uzupełnienie pokrycia
6. Wytrenować `verdict_head.pt` dla 15 katalogów konkurencyjnych (albo dodać shared-head fallback w `verdict_load_bundle`).
7. Re-run `eval-horizon-competitors` dla wszystkich 15.
8. Re-run `train-horizon-v22` dla `4b-nano-ternary-1.58b` i `micro-250m-tactical` z `BCEWithLogitsLoss` (clamp logitów) + `PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True`.
9. Re-run `finalize-v22` + `export-jevbench-decision-index` na prawdziwych danych.

### Krok 3 — publikacja (po kroku 1 i 2)
10. Zenodo DOI `10.5281/zenodo.24005152`.
11. `benchmarkheaven.com` Decision Index 0.4.

### Krok 4 — porządki
12. Poprawić nazwę katalogu na Drive: `skopion-verdict-4b-v22 (1).0-absolute-horizon` → `skopion-verdict-4b-v22.0-absolute-horizon`.
13. **Zero-trace purge** `/hpcwork/eoz68780/skopion-verdict/results/run-20261106-phase89-100-v22-absolute-horizon/` — **wstrzymane**. Dane są jedyną kopią surowych artefaktów potrzebnych do naprawy z kroku 1. Purge dopiero po regeneracji wyników.

---

## 8. Ograniczenia tego raportu

- Okno klucza SSH wygasa ~2026-11-07 09:08 UTC. Prace na klastrze po tej godzinie wymagają nowego TAN.
- `strict_148_mean` dla 52 modeli zewnętrznych bez artefaktów: źródło `[UNVERIFIED]` — prawdopodobnie macierz v21, nie zweryfikowano.
- Nie sprawdzono, czy macierz v21 (`external-benchmark-matrix-120suites-v21-omniprover-20261106.json`) sama nie zawiera tych samych syntetycznych wzorców.
