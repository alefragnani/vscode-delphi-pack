# Delphi Extension Pack for VS Code

Always reference these instructions first and fall back to additional search or terminal commands only when project files do not provide enough context.

## Project Overview

This repository provides a Visual Studio Code Extension Pack for Delphi development.

It does not implement runtime extension logic. Instead, it bundles related extensions via the `extensionPack` manifest field so users can install a curated Delphi toolset in one step.

## Technology Stack

- Language: JSON
- Runtime: VS Code Extension Pack manifest
- Bundler: None (manifest-only)
- Linting: None (manual JSON validation)
- Testing: Manual validation (manifest and extension IDs)

## Working Effectively

This project is metadata-driven and has no TypeScript source/build pipeline.

Typical workflow:

1. Edit `package.json` metadata or `extensionPack` IDs.
2. Validate JSON syntax and extension IDs.
3. Review README/CHANGELOG consistency.

## Build and Development Commands

There are no required npm build/lint/test scripts in this repository.

Validation is primarily manifest-level:

- `package.json` structure and syntax
- `extensionPack` IDs correctness
- Marketplace metadata correctness (`name`, `publisher`, `engines`, `categories`)

## Testing and Validation

Manual validation checklist:

1. Ensure all IDs in `extensionPack` use `publisher.extensionName` format.
2. Ensure listed extensions are intended and still valid.
3. Verify `engines.vscode` and category remain correct for extension-pack type.
4. Check README and CHANGELOG reflect pack changes.

## Project Structure and Key Files

```
package.json              # Full extension-pack definition
README.md                 # User-facing pack description
CHANGELOG.md              # Release notes
images/                   # Marketplace icon assets
```
## Coding Conventions and Patterns

### Indentation

- We spaces, not tabs.
- Use 4 spaces for indentation.

### Naming Conventions

- Keep extension IDs lowercase and exact.
- Keep metadata fields accurate and aligned with Marketplace requirements.

### Code Quality

- Keep JSON formatting consistent with existing file style.

## Extension Features and Configuration

Core feature is the `extensionPack` array in `package.json`.

When adding or removing extensions:

1. Confirm the ID is correct.
2. Verify the extension aligns with Delphi development scope.
3. Update documentation/changelog accordingly.

## Dependencies and External Tools

- No runtime dependencies.
- No external tooling required for normal maintenance.

## Troubleshooting and Known Limitations

- If pack installation misses an extension, verify ID spelling and publisher.
- If marketplace metadata looks incorrect, verify `displayName`, `description`, `categories`, and icon fields.
- As an extension pack, this repository cannot fix behavior inside bundled extensions.

## CI and Pre-Commit Validation

Before committing:

1. Validate `package.json` syntax.
2. Confirm `extensionPack` IDs.
3. Ensure README/CHANGELOG updates are complete when pack content changes.

## Common Tasks

Add a bundled extension:

1. Append extension ID to `extensionPack`.
2. Update release notes.
3. Verify metadata remains accurate.

Remove a bundled extension:

1. Remove extension ID from `extensionPack`.
2. Document removal in changelog.
3. Recheck remaining IDs and scope.


