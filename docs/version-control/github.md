# GitHub CLI 🐙

A quick reference guide for managing GitHub repositories, PRs, issues, and auth directly from your terminal using `gh`.

---

## 1. Authentication & Setup

| Command | Description |
| :--- | :--- |
| `gh auth login` | Authenticate with your GitHub account (interactive prompt) |
| `gh auth status` | Display current authentication status and active account |
| `gh auth logout` | Log out from a GitHub account |
| `gh config set editor <editor>` | Set default text editor for gh (e.g., `gh config set editor vim`) |

---

## 2. Repository Management

| Command | Description |
| :--- | :--- |
| `gh repo create` | Interactively create a new GitHub repository |
| `gh repo create <name> --public --source=. --remote=origin --push` | Create remote repo from local directory, add remote, and push code |
| `gh repo clone <owner>/<repo>` | Clone a remote repository to your local machine |
| `gh repo view` | Display repository description and README in terminal |
| `gh repo view --web` | Open current repository in your default web browser |

---

## 3. Pull Requests (PRs)

| Command | Description |
| :--- | :--- |
| `gh pr create --title "<title>" --body "<body>"` | Create a new pull request |
| `gh pr list` | List open pull requests in current repository |
| `gh pr checkout <pr_number>` | Check out a pull request branch locally |
| `gh pr diff` | View changes in the current pull request |
| `gh pr merge <pr_number> --squash` | Merge a pull request using squash strategy |

---

## 4. Issues & Gists

| Command | Description |
| :--- | :--- |
| `gh issue create --title "<title>" --body "<body>"` | Create a new issue |
| `gh issue list` | List open issues in current repository |
| `gh issue close <issue_number>` | Close a specific issue |
| `gh gist create <file>` | Create a GitHub Gist from a local file |

---

## 5. GitHub Actions & Workflows

| Command | Description |
| :--- | :--- |
| `gh run list` | View recent workflow runs |
| `gh run watch` | Stream live logs of an in-progress workflow run |
| `gh workflow list` | List all workflows in the repository |
