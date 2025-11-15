# Release Process

This project uses the **release-please** GitHub Action to automate
versioning, changelog generation, git tags, and GitHub Releases.

Releases are always cut from the `main` branch.

Developers usually only need to:

1. Use conventional commit messages.
2. Merge pull requests into `main`.
3. Merge the automatically created **release PR** when they are ready to publish a new version.

---

## Commit Message Rules

`release-please` looks at commit messages and decides how to bump the version.
We follow **Conventional Commits**:

- `feat: ...` → **minor** version bump (`1.2.0` → `1.3.0`)
- `fix: ...` → **patch** version bump (`1.2.3` → `1.2.4`)
- `chore: ...`, `docs: ...`, `refactor: ...`, etc. → no version bump by themselves

Breaking changes:

- Use `feat!: ...` **or**
- Add a `BREAKING CHANGE: ...` footer in the commit body

Either of these will cause a **major** version bump (`1.2.3` → `2.0.0`).

Examples:

- `feat: add dark mode`
- `fix: handle empty config`
- `feat!: remove deprecated API`
- `refactor: cleanup CSS`

---

## Normal Development Workflow

1. **Create a feature branch**

   ```bash
   git checkout -b feature/my-change
   ```

2. **Make changes and commit using conventional commit messages.**
3. **Open a Pull Request into main.**
4. **Get the PR reviewed and merged into main.**
After the merge, release-please will analyze the new commits on main.

## How Releases Are Created

After one or more PRs have been merged into `main`:

1. The release-please bot creates (or updates) a pull request named similar to
`chore: release vX.Y.Z.`
2. This release PR usually contains:

- An updated version in the relevant files (for example `package.json`, etc.)
- An updated `CHANGELOG.md` with entries for the new version

3. When you are ready to publish a new release:

- Review the release PR (changelog, version number).
- Merge the release PR into main.

4. When the release PR is merged, release-please will:

- Create a git tag `vX.Y.Z.`
- Create a GitHub Release named `vX.Y.Z` with the changelog.
- Optionally trigger any other workflows that run on tag push (for example build or deployment workflows, if configured in this repository).

## Forcing / Triggering a Release

Usually you don’t have to do anything special: releases are created whenever there are new merged commits on main and you merge the release PR.

If you want to cut a release now:

- Check if there is already an open chore: release `vX.Y.Z` PR.
  - If yes – review and merge it.
  - If no – you can re-run the release-please GitHub Action for the latest main commit from the Actions tab in GitHub.
