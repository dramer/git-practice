# git-practice

A sandbox for practicing the everyday git flow: **branch → commit → push → pull request → review → merge**. Break things here, not in a real project.

## Why this repo is public

- **So `main` can be protected.** GitHub's free plan only allows branch protection on public repos, and practicing against a protected `main` is the whole point: a direct push to `main` is refused, so every change has to come through a pull request.
- **So teammates can join easily.** Anyone can read it and clone it; to push branches and review, ask the owner to add you as a collaborator.

Because anyone on the internet can read it:

> **Made-up content only.** Never put real work code, company or system names, customer or member data, passwords, keys or tokens here. Our real work lives on our own company server, not on GitHub.

**Your email is public too.** Every commit shows its author's email. Before your first commit here, use your GitHub "noreply" address for this repo (GitHub → Settings → Emails shows it; tick "Keep my email addresses private"):

```bash
git config user.email "<id>+<your-username>@users.noreply.github.com"
```

(No `--global`: it applies to this repo only.)

## The rules on `main`

| Rule | What it means for you |
|---|---|
| Pull request required | `git push` straight to `main` is refused. Push a branch and open a pull request instead. |
| 1 approval from someone else | A teammate approves your pull request. You can't approve your own. |
| New pushes reset approvals | If you change the branch after an approval, it needs approving again. |
| No force push, no deleting `main` | `main`'s history can't be rewritten or removed. |

The repo owner can merge their own pull requests without an approval, for solo practice. Their direct pushes to `main` are still refused.

## Recommended git settings (once per computer)

```bash
git config --global init.defaultBranch main
git config --global push.autoSetupRemote true   # first push of a new branch just works
git config --global pull.rebase false           # git pull merges
git config --global fetch.prune true            # deleted server branches disappear locally
git config --global core.autocrlf input         # Mac/Linux; use "true" on Windows
```

## How to practice

1. **Get the repo** (once):
   ```bash
   git clone https://github.com/dramer/git-practice.git
   cd git-practice
   ```
2. **Start from an up-to-date `main`:**
   ```bash
   git switch main && git pull
   ```
3. **Make a branch** named after you and what you're doing:
   ```bash
   git switch -c practice-<yourname>-first-change
   ```
4. **Change something.** Add or edit your own file in `practice/`, for example `practice/<yourname>.md`. Using your own file means you won't collide with anyone else.
5. **Commit and push:**
   ```bash
   git add practice/<yourname>.md
   git commit -m "Add <yourname>'s practice file"
   git push
   ```
6. **Open a pull request**, either by clicking the "Compare & pull request" banner on the repo page, or:
   ```bash
   gh pr create --fill
   ```
   The description box fills in from the template. Answer its questions.
7. **Ask a teammate to review.** They open the pull request, read the **Files changed** tab, leave a comment, and approve.
8. **Merge it** with the green button, then **Delete branch**.
9. **Tidy up on your computer:**
   ```bash
   git switch main && git pull && git branch -d practice-<yourname>-first-change
   ```

## Things worth trying

- **See the protection work:** commit on `main` and `git push`. GitHub refuses it. Undo with `git reset --hard origin/main`.
- **Review someone else's pull request:** comment on a line, request a change, then approve after they fix it.
- **Make a merge conflict on purpose:** two people edit the same line of the same file on two branches, then merge both. Resolve it in your editor.
- **Change a branch after approval** and watch the approval reset.

Have fun, and break things here.
