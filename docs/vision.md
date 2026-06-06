# Metagraphed Vision

Metagraphed starts as a registry and status layer, not a node-ops business.

The wedge is simple: Bittensor has a native metagraph for subnet state, but builders still need to know how to consume subnet interfaces in practice. That means public APIs, OpenAPI/Swagger surfaces, dashboards, docs, repositories, endpoint health, schema drift, freshness, and access metadata.

## Positioning

Metagraphed extends the native Bittensor metagraph with public interface and health metadata.

It does not replace protocol state, explorer analytics, subnet docs, validator dashboards, or RPC providers. It sits beside them as an operational interface registry.

## Registry Coverage

The registry is chain-first. Every active Finney netuid should appear from decoded native Bittensor/Subtensor data before any custom subnet integration exists.

This gives Metagraphed complete coverage without pretending every subnet has verified public APIs. Native-only entries are useful as indexable stubs, and curated overlays add interfaces only when they have been reviewed.

Coverage levels:

- `native-only`: active chain subnet with no verified public interface metadata yet;
- `manifested`: curated interface metadata exists;
- `probed`: curated interface metadata exists and at least one safe probe is configured.

Third-party APIs can enrich candidates, labels, and cross-check counts, but they are not canonical for active subnet existence.

## Product Layers

### Native Metagraph Layer

Universal Bittensor state for every subnet:

- netuid;
- subnet identity;
- symbol;
- participant counts;
- registration block;
- mechanism count;
- tempo and block timing.

The MVP intentionally avoids publishing owner keys or validator-sensitive details even when they are chain-public.

### Interface Metagraph Layer

Declarative metadata for public interfaces:

- APIs;
- OpenAPI/Swagger;
- SSE/event streams;
- dashboards;
- source repositories;
- docs;
- JSON-RPC/WSS endpoints;
- public data artifacts;
- rate-limit and auth notes.

### Health Metagraph Layer

Observed status metadata:

- uptime;
- latency;
- status code;
- schema hash;
- schema drift;
- method support;
- archive support;
- freshness;
- error class;
- probe history.

## Domains

- `metagraph.sh` is the primary product surface.
- `subnet.health` is the dedicated health/status/badge surface.

`subnet.health` should be useful on its own, not just a redirect. It can expose short URLs, badges, status JSON, and later provider-health comparisons for each subnet.

## Pilot

The pilot is Allways SN7 plus Gittensor SN74.

Allways gives Metagraphed a concrete public API surface: swaps, events, crown data, miners, leaderboard, reliability, protocol state, and SSE.

Gittensor gives Metagraphed a different operational shape: repositories, bounties, contribution surfaces, emissions metadata, maintainer-cut metadata, mirror freshness, and public-safe aggregate metrics.

## Funding Path

Gittensor emissions should fund software stewardship, review, registry maintenance, and contributor coordination.

Recurring infra costs should be separate milestones: hosted mirrors, cache layers, load-balanced public subnet access, Bittensor lite/archive nodes, and other OPEX-heavy work.

## Public-Safety Boundary

Metagraphed must not ingest or publish:

- secrets;
- wallet paths;
- private keys;
- private dashboards;
- validator-only flows;
- token-gated data;
- credentialed GitHub flows;
- user-specific operational state.

Everything in the MVP should be public, read-only, and safe to probe.

## Intake Boundary

Community submissions and third-party discovery go into a candidate queue first.

Schema-valid means the submission can be reviewed. It does not mean the interface is verified or published. Promotion into a curated overlay requires maintainer review of source support, public accessibility, auth/rate-limit labels, and probe safety.
