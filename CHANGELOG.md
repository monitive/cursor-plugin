# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- Renamed the plugin to `monitive` (display name "Monitive") and the bundled MCP server entry to `monitive`.
- Pointed the bundled manifest, the install deeplink, and the README at https://api.monitive.com/mcp. The former `api.uptimemonitoring.com` host is a deprecated alias that stops serving on 2027-01-31.
- Pointed `homepage` at https://monitive.com/docs/mcp/ and `repository` at https://github.com/monitive/cursor-plugin.
- Renamed the documented API key variable to `MONITIVE_API_KEY`.

## [0.1.0] - 2026-06-06

### Added

- Initial public release of the Cursor plugin for the UptimeMonitoring MCP server.
- Bundled Cursor manifest pointing at https://api.uptimemonitoring.com/mcp.
- OAuth 2.1 (auto-discovered by Cursor for the remote server) as the default auth; Bearer API key documented as a fallback for trusted server-to-server use.
- README with one-click install deeplink and manual-install instructions.

### Notes

The Cursor Marketplace listing is pending submission; until it is published, install via the README instructions.
