# alanfullagar.github.io

Portfolio site for `https://alanfullagar.github.io/`.

## Repository Structure

```text
.
|-- index.html
|-- assets/
|   |-- docs/          # CV PDFs
|   |-- icons/         # favicon + touch icon
|   `-- images/        # profile, previews, portfolio visuals
|-- content/
|   `-- blog-post-complete.md   # long-form article kept separate from site page
`-- .github/
    `-- workflows/     # CI checks
```

## Update Workflow

1. Create a branch from `main`: `feat/<change>`.
2. Make changes and test links/assets locally.
3. Commit with clear scope (single logical change per commit).
4. Open a pull request to `main`.
5. Merge only after checks pass.

## Asset Rules

1. Keep binary files in the appropriate `assets/*` folder.
2. Use relative paths from `index.html` (for example `assets/images/profile.jpg`).
3. If a previously shared public URL must keep working, leave a compatibility copy at the old path.

## Common Commands

```powershell
# check changed files
git status

# inspect last commits
git log --oneline -n 5

# push current branch
git push origin HEAD
```
