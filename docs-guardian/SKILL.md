---
name: docs-guardian
description: Protects and audits the pristine `docs/` folder against accidental AI modifications, additions, or deletions, to prevent something called context-poisoning
---

# Docs Guardian Skill

This skill enforces strict read-only integrity on the project's `docs/` directory.

## Workflow Instructions

When invoked or prior to suggesting/applying code modifications that interact with documentation, perform the following procedure:

### 1. Initialize Baseline (If Manifest Missing)
If `docs.manifest.json` does not exist in the root directory:
1. Scan all files inside `docs/` recursively.
2. Compute the SHA-256 hash for every file.
3. Create `docs.manifest.json` with the file list and their corresponding hashes.

```json
{
  "docs_path": "docs/",
  "created_at": "<ISO-TIMESTAMP>",
  "files": {
    "docs/architecture.md": "<SHA-256-HASH>",
    "docs/api-spec.pdf": "<SHA-256-HASH>"
  }
}
