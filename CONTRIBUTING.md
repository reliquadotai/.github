# Contributing to Reliquary

Thank you for improving Reliquary. This file is the organization-wide default;
a repository's own contributing guide takes precedence when it is more
specific.

## Choose the right repository

| Change | Repository |
| --- | --- |
| Subnet 81 protocol, miner, validator, training, or documentation | [`reliquary`](https://github.com/reliquadotai/reliquary) |
| Fleet monitoring application or packaging | [`reliquary-fleet`](https://github.com/reliquadotai/reliquary-fleet) |
| Organization profile or shared community files | [`.github`](https://github.com/reliquadotai/.github) |
| Earlier Ledger, Forge, or shared-protocol experiments | The corresponding historical repository |

For support and routing help, read [SUPPORT.md](SUPPORT.md). Report
vulnerabilities through [SECURITY.md](SECURITY.md), never through a public bug
report.

## Before opening a change

1. Search existing issues and pull requests.
2. Confirm the behavior against the target repository's current default branch.
3. Open an issue first when the change alters protocol behavior, public data
   semantics, security boundaries, or user-facing claims.
4. Keep credentials, wallet material, private prompts, raw completions, personal
   data, and infrastructure secrets out of issues, commits, fixtures, and logs.

## Evidence standard

Reliquary distinguishes three kinds of statements:

- **Deployed** — demonstrated by canonical source and an identifiable
  deployment or release.
- **Observed** — measured from a named public or sanitized source at a stated
  time.
- **Proposed** — a design, simulation, hypothesis, or planned experiment.

Do not turn an observation into a deployed claim. Do not describe an
experimental mechanism as affecting selection, rewards, or training until the
canonical implementation and deployment evidence agree.

Mutable metrics need a timestamp, provenance, and an appropriate caveat. Keep
evergreen READMEs free of copied live counters; link to the
[dashboard](https://www.reliqua.ai/dashboard), [explorer](https://www.reliqua.ai/explorer),
or [status page](https://www.reliqua.ai/status).

## Development workflow

1. Create a focused branch from the current default branch.
2. Make the smallest coherent change that solves the issue.
3. Add or update tests in proportion to the risk.
4. Run every check required by the target repository.
5. Update operator documentation, examples, and migration notes when behavior
   changes.
6. Open a pull request using the shared template and include reproducible
   evidence.

Avoid drive-by formatting, generated-file churn, unrelated dependency updates,
and silent compatibility changes.

## Pull request quality

A reviewable pull request:

- explains the problem and why the chosen change solves it;
- states what is deliberately out of scope;
- links the issue, design note, deployment receipt, or public evidence;
- lists exact validation commands and results;
- identifies security, privacy, compatibility, and rollout risks;
- includes accessible screenshots or recordings for visual changes;
- distinguishes current production behavior from future work.

By contributing, you agree that your work is provided under the license stated
by the repository receiving the contribution.
