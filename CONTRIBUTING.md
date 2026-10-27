# Contributing Guidelines

Thank you for contributing to this project! These guidelines help us maintain code quality, security, and a consistent development workflow.

All code contributions must go through a Pull Request (PR) review process. Direct pushes to `master` are restricted.

---

## 🌿 1. Branching Strategy

Never push changes directly to `master`.

Create a dedicated branch for each task, using a descriptive name and the appropriate prefix:

| Prefix      | Purpose                                              | Example                  |
| ----------- | ---------------------------------------------------- | ------------------------ |
| `feat/`     | New features                                         | `feat/product-card`      |
| `fix/`      | Bug fixes                                            | `fix/cart-total`         |
| `docs/`     | Documentation                                        | `docs/update-readme`     |
| `refactor/` | Code improvements without changing intended behavior | `refactor/checkout-flow` |
| `test/`     | Adding or updating tests                             | `test/cart-validation`   |
| `chore/`    | Tooling, dependencies, or configuration              | `chore/add-eslint`       |

Example:

```bash
git switch master
git pull origin master
git switch -c feat/product-card
```

If you already have a feature branch, continue working on that branch instead of creating another one unnecessarily.

---

## 🔄 2. Pull Request Workflow

Every contribution must be submitted through a pull request targeting `master`.

### Step 1: Keep your branch up to date

Before opening a PR, fetch the latest changes from the remote repository:

```bash
git fetch origin
```

To incorporate the latest `master` into your feature branch, use:

```bash
git switch feat/product-card
git merge origin/master
```

Replace `feat/product-card` with your actual branch name.

Resolve any merge conflicts before proceeding.

### Step 2: Verify your changes locally

Run the relevant checks before opening a PR.

For projects with the corresponding npm scripts configured, run:

```bash
npm run lint
npm run build
```

Run the project's relevant tests as well, if available.

Do not report checks as passing unless they have actually completed successfully.

### Step 3: Open a pull request

Create a PR from your feature branch into `master`.

Your PR description must explain:

- **What:** What changed?
- **Why:** Why was the change necessary?
- **How:** How was the change implemented?
- **Testing:** What checks or tests were performed?

For UI changes, include screenshots or GIFs when useful.

Keep each PR focused on one feature, fix, or related task. Avoid mixing unrelated changes.

### Step 4: Request a review

- Request at least one eligible team member to review the PR.
- Explain any important implementation decisions.
- Respond to review feedback and make the necessary changes.
- Resolve review conversations once the concern has been addressed.
- Do not resolve a discussion merely to hide an outstanding issue.

If you push new commits after approval, GitHub may dismiss the previous approval according to the repository's configured rules. Review the PR status again before merging.

### Step 5: Merge the pull request

Merge only when all required conditions are satisfied:

- The required approval has been received.
- All required status checks pass.
- Required review conversations are resolved.
- No other repository rules prevent merging.

Use **Squash and merge** when available and agreed upon by the team. This keeps the master branch history concise.

Do not bypass repository protections to merge your own changes.

---

## 🧹 3. Code Quality Standards

All contributions should follow these principles:

- **Consistency:** Follow the project's existing conventions and formatting.
- **Readability:** Write clear, understandable code.
- **DRY:** Avoid unnecessary duplication.
- **Single responsibility:** Keep modules and functions focused.
- **Maintainability:** Prefer straightforward solutions over unnecessary complexity.
- **Scope control:** Avoid unrelated refactoring or changes.
- **Error handling:** Handle expected errors and edge cases appropriately.
- **Type safety:** Follow the project's TypeScript and typing conventions when applicable.

Avoid introducing new dependencies unless they provide a clear benefit. Explain significant dependency additions in the PR description.

---

## 🔐 4. Security Guidelines

Never commit or publish:

- API keys, access tokens, or passwords.
- Database credentials or private connection strings.
- Private certificates or other sensitive credentials.
- `.env` files containing real secrets.
- Personal data or confidential information.

Use environment variables and the project's documented environment configuration instead.

If an example environment file is needed, use placeholder values only, such as those in `.env.example`.

Before committing, check which files will be included:

```bash
git status
git diff --cached
```

Do not assume that a secret is safe because it is not visible in the latest version of a file. If a secret is accidentally exposed, revoke or rotate it immediately and notify the project maintainers.

GitHub secret scanning and push protection may help detect supported secrets when enabled, but they do not guarantee detection of every secret.

For dependency security, address relevant Dependabot alerts and avoid knowingly introducing vulnerable dependencies.

---

## 📝 5. Commit Guidelines

Use clear commit messages that describe the change.

Examples:

```text
feat: add product card
fix: correct cart total
docs: update setup instructions
refactor: simplify checkout flow
test: add cart validation tests
chore: configure eslint
```

Keep commits focused on related changes. Do not include unrelated formatting changes, generated files, local configuration, or secrets.

---

## 🤝 6. Team Collaboration

- Discuss substantial architectural changes with the team before implementation.
- Communicate blockers early.
- Be respectful and constructive during code reviews.
- Explain the reasoning behind requested changes.
- Avoid approving code you have not reviewed adequately.
- Do not merge changes while required checks are failing.
- Ask for clarification when requirements or implementation details are unclear.

Code reviews are intended to improve the codebase and help team members learn, not to criticize individuals.

---

## ✅ 7. Final Checklist

Before requesting a review, confirm the following:

- [ ] My branch follows the naming convention.
- [ ] My PR targets `master`.
- [ ] My changes are focused and relevant to the task.
- [ ] I have reviewed my own diff.
- [ ] I have run the applicable lint, build, and test commands.
- [ ] I have not committed secrets or sensitive data.
- [ ] I have documented important implementation decisions.
- [ ] I have included screenshots for relevant UI changes.
- [ ] I have requested a review from an eligible team member.

Thank you for helping us keep the project reliable, secure, and maintainable!
