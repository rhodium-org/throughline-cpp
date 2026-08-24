# throughline-cpp

The **Google C++ Style Guide** expressed as a
[throughline](https://pypi.org/project/throughline/) **source** — a standalone,
grounded requirements graph that a consuming project composes with
[throughline-compose](https://github.com/rhodium-org/throughline-compose).

This repository holds no code. It is a directory of small YAML items with permanent
UIDs, validated by `tl check`. Consumers import it under a namespace and reference
its rules as `cpp:SR-0001`.

It is one of a family of **orthogonal** language and concern sources: compose it
alongside a concern source (e.g. `throughline-backend`) so a project's C++ code is
grounded in both at once.

## Status

<!-- tl:count type == 'user_requirement' -->
9
<!-- tl:end --> sections and
<!-- tl:count type == 'system_requirement' -->
67
<!-- tl:end --> style rules, published to [`docs/spec.md`](docs/spec.md):

- `INT-0001` — the root intent (why the guide exists), `normative: false`.
- Each major guide section as a `user_requirement` that `derives_from` the intent.
- Every individual rule as a `system_requirement` that `implements` its section,
  carrying the guide reference in `attrs.source_ref`.

The counts above are rendered from the live graph by the `tl:count` directive, so
they cannot drift.

## Editions — dated tags

The guide is a living document. A material revision is cut as a dated tag on this
repo (e.g. `v2026-08`); a consumer pins the ref it wants.

## Composing it

```toml
[[sources]]
namespace = "cpp"
url = "https://github.com/rhodium-org/throughline-cpp"
ref = "v2026-08"
```

Then reference a rule from your own items:

```yaml
links:
- target: cpp:SR-0011           # Google C++ Style Guide: mark single-argument constructors explicit
  type: satisfies
```

`tl-compose check` resolves the reference; bare `tl check` fails fast and points you
at `tl-compose`.

## Local checks

```sh
pip install throughline
tl check --strict     # the graph must stay sound
tl docs --check       # docs/spec.md must match the graph
```

## Provenance

The Google C++ Style Guide is © Google, licensed CC BY 3.0. See [NOTICE](NOTICE)
and https://google.github.io/styleguide/cppguide.html. This repository is Apache-2.0 for
its structure and tooling; the reproduced rule text remains Google's.
