# All-Subnet Registry Model

Metagraphed covers every active Finney subnet through two separate data layers.

## Native Snapshot

`registry/native/finney-subnets.json` is generated from decoded Bittensor SDK data.

It is canonical for:

- active netuid existence;
- root/system versus application subnet classification;
- chain subnet name and symbol;
- participant count;
- tempo;
- registration block;
- mechanism count;
- capture block and source metadata.

It is not the place for docs URLs, dashboards, public APIs, or probe rules.

## Curated Overlays

`registry/subnets/*.json` contains hand-reviewed interface metadata.

Overlays are canonical for:

- public APIs;
- OpenAPI/Swagger surfaces;
- SSE/event streams;
- dashboards;
- docs;
- repositories;
- data artifacts;
- read-only probe rules.

An overlay must reference a netuid that exists in the native snapshot unless it is explicitly marked pending.

## Candidate Queue

`registry/candidates` is for unverified public interface candidates from community submissions or third-party discovery.

Candidates are never treated as verified surfaces. They must pass maintainer review before being promoted into `registry/subnets`.

## Generated Artifacts

`public/metagraph/subnets.json` lists every active chain subnet.

`public/metagraph/surfaces.json` lists only curated/verified public interface surfaces.

`public/metagraph/coverage.json` summarizes chain coverage, curated overlays, native-only stubs, probed subnets, and candidate counts.

`public/metagraph/subnets/{netuid}.json` exposes per-subnet static detail artifacts for app and API consumers.
