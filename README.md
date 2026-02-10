# beadstest
This repository was created to demonstrate my onboarding experience with beads.

## Setup

```
uv init beadstest
```
```
cd beadstest
```
```
git add * .*
```
```
git commit --all --message "Initial commit"
```
```
vim README.md
# added this initial content
```


### Github
Create the repo and copy the "push existing repo content.."


## Beads
```
bd init
```
```
  Repository ID: 0a048cfe
  Clone ID: c66ab5dc7835acb9
Contributing to someone else's repo? [y/N]:
  ✓ Created AGENTS.md with landing-the-plane instructions

✓ bd initialized successfully!

  Backend: sqlite
  Database: .beads/beads.db
  Issue prefix: beadstest
  Issues will be named: beadstest-<hash> (e.g., beadstest-a3f2dd)

Run bd quickstart to get started.

⚠ Setup incomplete. Some issues were detected:
  • Git Hooks: Missing 1 recommended hook(s)
  • Sync Divergence: 1 sync divergence issue(s) detected
  • Git Working Tree: Uncommitted changes present
  • Version Tracking: Version tracking not initialized
  • Sync Branch Config: sync-branch not configured

Run bd doctor --fix to see details and fix these issues.

git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.README.md.swp
	.beads/
	.gitattributes
	AGENTS.md
```

Hmmmm, so what's next? `bd quickstart`, `bd doctor --fix`, or commit these files?

```
git add .beads/ .gitattributes AGENTS.md README.md
gcam "Add initial beads artifacts"
ggpush
```

OK, let's try the `bd doctor --fix`:
```
bd doctor --fix

Fixable issues:
  1. Git Hooks: Missing 1 recommended hook(s)
  2. Git Working Tree: Uncommitted changes present
  3. Sync Branch Config: sync-branch not configured
  4. Merge Artifacts: 2 temporary merge file(s) found

This will attempt to fix 4 issue(s). Continue? (Y/n):
```
```
Applying fixes...

Fixing Git Hooks...
✓ Git hooks installed successfully

Installed hooks:
  - pre-commit
  - post-merge
  - pre-push
  - post-checkout
  - prepare-commit-msg
  ✓ Fixed

Fixing Git Working Tree...
  ⚠ No automatic fix available for Git Working Tree
  Manual fix: Commit or stash changes, then follow AGENTS.md: git pull --rebase && git push

Fixing Sync Branch Config...
  ⚠ Add 'sync-branch: beads-sync' to .beads/config.yaml

Fixing Merge Artifacts...
  Removed beads.left.jsonl
  Removed beads.left.meta.json
  Removed 2 merge artifact(s)
  ✓ Fixed

Fix summary: 2 fixed, 0 errors

bd doctor v0.49.6  ──────────────────────────────────────────  ✓ 76 passed  ⚠ 2 warnings  ✖ 0 errors

  ⚠  1. Git Working Tree: Uncommitted changes present
        M README.md
?? .README.md.swp
        └─ Commit or stash changes, then follow AGENTS.md: git pull --rebase && git push
  ⚠  2. Sync Branch Config: sync-branch not configured
        Multi-clone setups should configure sync-branch for safe data synchronization
        └─ Run 'bd migrate sync beads-sync' to set up sync branch workflow
```

Hmmmm warnings, but no errors. am I good to go?
```
bd doctor --fix

Fixable issues:
  1. Git Upstream: Ahead of upstream by 1 commit(s)
  2. Sync Branch Config: sync-branch not configured

This will attempt to fix 2 issue(s). Continue? (Y/n):

Applying fixes...

Fixing Git Upstream...
  ⚠ No automatic fix available for Git Upstream
  Manual fix: Run 'git push' (AGENTS.md: git pull --rebase && git push)

Fixing Sync Branch Config...
  ⚠ Add 'sync-branch: beads-sync' to .beads/config.yaml

Fix summary: 0 fixed, 0 errors

bd doctor v0.49.6  ──────────────────────────────────────────  ✓ 76 passed  ⚠ 2 warnings  ✖ 0 errors

  ⚠  1. Git Upstream: Ahead of upstream by 1 commit(s)
        Branch: main, upstream: origin/main
        └─ Run 'git push' (AGENTS.md: git pull --rebase && git push)
  ⚠  2. Sync Branch Config: sync-branch not configured
        Multi-clone setups should configure sync-branch for safe data synchronization
        └─ Run 'bd migrate sync beads-sync' to set up sync branch workflow
```


