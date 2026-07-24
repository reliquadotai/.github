# Security policy

Reliquary coordinates public network data, model artifacts, and operator
software. Please report vulnerabilities privately and give maintainers a
reasonable opportunity to investigate before disclosure.

## Supported scope

Security fixes are prioritized for:

- the current default branch of
  [`reliquadotai/reliquary`](https://github.com/reliquadotai/reliquary);
- the latest published release of
  [`reliquadotai/reliquary-fleet`](https://github.com/reliquadotai/reliquary-fleet);
- the public website and proof surfaces at
  [`reliqua.ai`](https://www.reliqua.ai/).

Ledger, Forge, and the standalone Protocol repository are historical or
reference implementations. Reports are welcome, but fixes may be documentation
or archival notices rather than new releases.

## Report privately

1. Use the canonical repository's
   [private vulnerability-reporting form](https://github.com/reliquadotai/reliquary/security/advisories/new).
2. If that form is unavailable, open a minimal issue in the affected
   repository titled `Private security contact requested`. Include no exploit,
   secret, vulnerable endpoint, wallet address, or reproduction detail.
3. Wait for a maintainer to establish a private channel before sharing
   technical details.

A useful private report includes:

- affected repository, version, commit, or deployment surface;
- impact and the assumptions required to reproduce it;
- minimal reproduction steps or proof of concept;
- whether live systems, funds, credentials, or private data may be at risk;
- suggested mitigations, if known;
- a safe way to coordinate disclosure.

## Research and testing boundaries

Do not:

- access or move wallet funds;
- extract credentials, private prompts, raw completions, or personal data;
- degrade Subnet 81, validators, miners, archives, or public services;
- submit destructive payloads to live infrastructure;
- retain data beyond what is necessary to demonstrate the issue.

Use local fixtures or isolated test infrastructure whenever possible. Stop
testing if you encounter secrets, private data, or a credible risk to network
availability.

## What happens next

Maintainers will validate scope, assess severity, coordinate remediation, and
agree on disclosure timing with the reporter. Public credit is offered when
requested and safe. Duplicate reports, automated scan output without a
demonstrated impact, and reports outside the supported scope may receive a
shorter response.

Public security design notes and incident reports live in the canonical
repository's
[`docs/security`](https://github.com/reliquadotai/reliquary/tree/main/docs/security)
directory.
