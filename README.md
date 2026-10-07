# Example Catalog Provider — third-party proof for the Governance Provider SDK

Independent Python distribution that registers `example.catalog` through the
public `governance.providers` entry-point group.

This package is a reference/example provider and reusable template. It is not a
vendor certification. Full conformance validates cooperative observable behavior,
not security.

## Capabilities

- `governance_graph`
- `property_observations`

No `metadata_discovery` (therefore not used with `governance check`).

## Requires

Host package: `collibra-governance-automation` **2.0.0** (Provider SDK API `"1"`).

This companion package version remains **0.1.0**. Compatibility is declared by the
provider descriptor (`sdk_compatibility = ">=1,<2"`), not by a pip dependency on
the host.

PyPI publication of the host is **not assumed**. Install the published Git tag:

```bash
pip install "collibra-governance-automation @ git+https://github.com/adrianmartnez/collibra-governance-automation.git@v2.0.0"
pip install .
```

## Install (development)

```bash
python -m venv .venv
source .venv/bin/activate
pip install "collibra-governance-automation @ git+https://github.com/adrianmartnez/collibra-governance-automation.git@v2.0.0"
pip install -e ".[dev]"
pytest
```

## Sample impact

```bash
governance impact \
  --config sample/governance.yaml \
  --namespace demo \
  --changes sample/changes.json \
  --format json
```

Do not pass `--odcs` / `--dbt-manifest` / `--openlineage`.

## Trust

Installed providers are trusted Python dependencies. This package is not sandboxed.

## Links

- Core release: https://github.com/adrianmartnez/collibra-governance-automation/releases/tag/v2.0.0
- Provider SDK docs: https://github.com/adrianmartnez/collibra-governance-automation/tree/v2.0.0/docs/providers
- Author guide: https://github.com/adrianmartnez/collibra-governance-automation/blob/v2.0.0/docs/providers/author-guide.md
- Migration guide: https://github.com/adrianmartnez/collibra-governance-automation/blob/v2.0.0/docs/providers/migration-v1.4-to-v2.md
