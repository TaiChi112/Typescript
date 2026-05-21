```markdown
# TYPESCRIPT Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and workflows found in a TypeScript codebase without a specific framework. It covers file organization, code style, commit conventions, and automated workflows—especially for managing dependencies across multiple packages. The guide also outlines how to write and organize tests in this environment.

## Coding Conventions

### File Naming
- **Style:** camelCase
- **Example:**  
  ```
  userService.ts
  apiClient.test.ts
  ```

### Imports
- **Style:** Relative imports
- **Example:**  
  ```typescript
  import { fetchData } from './apiClient';
  ```

### Exports
- **Style:** Named exports
- **Example:**  
  ```typescript
  export function fetchData() { ... }
  export const API_URL = 'https://...';
  ```

### Commit Messages
- **Convention:** Conventional commits
- **Prefix example:** `build`
- **Example:**  
  ```
  build: update dependencies for axios and next in all packages
  ```

## Workflows

### Dependency Upgrade Across Multiple Packages
**Trigger:** When a new version of a dependency is released and needs to be applied across many packages/repos.  
**Command:** `/upgrade-dependencies`

1. **Detect outdated dependencies** in multiple project directories.
2. **Update `package.json`** with new dependency versions in each affected directory.
3. **Update lock files** (`package-lock.json`, `pnpm-lock.yaml`) in each directory.
4. **Commit all changes together** with a detailed changelog.

**Files involved:**
- `**/package.json`
- `**/package-lock.json`
- `**/pnpm-lock.yaml`

**Example:**
```sh
/upgrade-dependencies
```
This command will automatically scan all packages, update dependencies, refresh lock files, and commit the changes.

## Testing Patterns

- **Framework:** Unknown (not detected)
- **File pattern:** `*.test.*`
- **Example:**
  ```
  apiClient.test.ts
  ```
- **Typical structure:** Test files are placed alongside the modules they test, using the `.test.ts` suffix.

## Commands

| Command               | Purpose                                                      |
|-----------------------|--------------------------------------------------------------|
| /upgrade-dependencies | Upgrade dependencies across all packages and update lockfiles |

```