# blueskyagent-components

Release artifacts of the BlueSky **local components**: the MCP servers the
BlueSky daemon downloads and runs on customers' computers (see
`docs/specs/harness/2026-10-26-harness-step9-local-components-design.md`
in `blueskyagent-front`).

This repo holds no source code. Each component lives in its own private repo
(`mcp-sql`, …); its CI (`mcp-ci`) builds the native executables per platform,
signs them and publishes them here as a release tagged `<key>-<version>`
(e.g. `mcp-sql-1.0.1`), with the `component.yaml` manifest and the sha256 of
every archive. The daemon only accepts artifacts from this organisation and
verifies the sha256 before extracting anything.

Pre-releases tagged `*-local.*` are local test builds and get deleted.
