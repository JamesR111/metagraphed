# Candidate Surfaces

This directory is for unverified subnet interface candidates discovered from third-party sources or community submissions.

Candidate entries are not published as verified registry surfaces. They must stay separate until maintainer review confirms:

- the public URL is live;
- auth and rate-limit requirements are labeled;
- source docs support the claim;
- the probe is safe and read-only;
- no secrets, private dashboards, credentialed flows, or validator-sensitive data are included.

Allowed states:

- `schema-invalid`
- `schema-valid`
- `maintainer-review`
- `verified`
- `stale`
- `rejected`

Only `verified` candidates should be promoted into curated subnet overlays under `registry/subnets`.
