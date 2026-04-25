# Reliquary

> Run the model, prove you did, publish the receipt. Anyone verifies in milliseconds.

**Reliquary** is a proof-carrying inference + RL training subnet on Bittensor. Every miner completion ships with a cryptographic sketch of the forward pass; a four-validator mesh re-runs the proof at sampled positions in milliseconds; verified rollouts feed an autonomous GRPO trainer that publishes signed policy deltas back to miners.

`testnet · netuid 462 · live since 2026-04-21`

## Live snapshot

| | |
|---|---|
| validators (mesh) | 4 (3× RTX PRO 6000 Blackwell + 1× H100) |
| miners (real model) | Qwen2.5-3B-Instruct, M=8 sampled rollouts |
| in-zone rate (rolling) | 0.60 |
| mean reward | 0.875 |
| accepted / total | 35 / 40 |
| cross-GPU determinism digest | `4de1918431de9f26…` |

Public audit (no auth, no operator cooperation needed):
- [HTML index](https://pub-954f95c7d2f3478886c8a8ff7a4946e0.r2.dev/audit/index.html)
- [JSON index](https://pub-954f95c7d2f3478886c8a8ff7a4946e0.r2.dev/audit/index.json)

## What's in the org

| Repo | Role |
|---|---|
| [`reliquary-ledger`](https://github.com/reliquadotai/reliquary-ledger) | Inference runtime — 9-stage verifier, validator mesh, policy consumer |
| [`reliquary-forge`](https://github.com/reliquadotai/reliquary-forge) | Training runtime — DAPO/GRPO trainer, distillation lane |
| [`reliquary-protocol`](https://github.com/reliquadotai/reliquary-protocol) | Shared crypto, canonical bytes, bridge envelopes |
| [`reliquary-web`](https://github.com/reliquadotai/reliquary-web) | Marketing site + proof explorer ([reliqua.ai](https://reliqua.ai)) |
| [`relica-dashboard`](https://github.com/reliquadotai/relica-dashboard) | Miner-telemetry dashboard |

## What's empirically true

- **Cross-GPU bit-exactness.** 4 hosts, 90 samples, identical sketch digests across A100 / Blackwell / H100. One commitment, four independent verifications, zero drift.
- **Mesh consensus under attack.** 256 verdicts, 1 simulated malicious validator across 4 nodes. Malicious validator gated cleanly at 1.0 disagreement; honest 3 produced bit-identical outputs.
- **Closed-loop RL.** Forge GRPO publishes signed `CheckpointAttestation + PolicyCommitment`; miners hot-swap deltas at `effective_at_ledger_window` after signature + smoke-hash + reparam-guard checks.
- **Reparam guard.** RMSNorm × Linear scale exploits caught before any delta touches the cached model.

## Read the spec, run the audit yourself

- [Protocol paper](https://github.com/reliquadotai/reliquary-ledger/blob/main/docs/paper/reliquary_protocol_paper.md)
- [Empirical audit reports](https://github.com/reliquadotai/reliquary-ledger/tree/main/docs/audit)
- [Validator quickstart](https://github.com/reliquadotai/reliquary-ledger/blob/main/docs/validator-quickstart.md)
- [Miner quickstart](https://github.com/reliquadotai/reliquary-ledger/blob/main/docs/miner-quickstart.md)

## License

MIT across the public repos. 

---

`mit · reliquadotai · 2026 · ledger · forge · one protocol`
