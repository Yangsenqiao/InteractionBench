# Mage-VL-4B InteractionBench artifacts

This directory contains the complete, directly inspectable outputs behind the
Mage-VL-4B `all1060` sliding-window result.

| Evaluation | Items | Total | Accuracy | TA | SC |
|---|---:|---:|---:|---:|---:|
| Qwen3-14B v2 paper judge | 1,060 | **33.668** | 46.856 | 65.454 | 21.034 |
| Multiple-choice items | 688 | **34.903** | 57.916 | 73.912 | 15.364 |

The merged predictions contain 1,060 unique item IDs, zero failed rows, 119,412
polls, and 28,193 emissions.

## Files

- `predictions.jsonl` — merged model emissions and poll latency for all 1,060 items.
- `run_config.json` — exact InteractionBench generation configuration.
- `eval-qwen3-14b-summary.json` — full aggregate paper-protocol scores.
- `eval-qwen3-14b-records.jsonl` — per-item full-evaluation records.
- `eval-mcq-summary.json` — aggregate scores for the 688 MCQ items.
- `eval-mcq-records.jsonl` — per-item MCQ evaluation records.
- `SHA256SUMS` — integrity hashes for every result file.

## Provenance

- InteractionBench base commit: `3bf1601fc17e10848bbe4869d8b1b6b4ba7b16e9`
- InteractionBench dataset revision: `ecef0756250a2bc5e8118186d961ab67e9f4a99c`
- Mage-VL checkpoint revision: `d88b153285f1633a61b2f693c59c8576693af185`
- Judge: `Qwen/Qwen3-14B`, InteractionBench v2 binary prompt
- Runtime: Python 3.12, PyTorch 2.9.1, Transformers 5.7.0, bfloat16, SDPA
- Hardware: 8 × NVIDIA H800

Verify downloads from this directory with:

```bash
sha256sum -c SHA256SUMS
```

See [`docs/MAGE_VL_RESULTS.md`](../../docs/MAGE_VL_RESULTS.md) and
[`scripts/reproduce_mage_vl.sh`](../../scripts/reproduce_mage_vl.sh) for the protocol
and one-command reproduction workflow.
