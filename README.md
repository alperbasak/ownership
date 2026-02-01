# CODEOWNERS Auto Approve GitHub Action

A GitHub Action that automatically approves pull requests when all CODEOWNERS requirements are met. The bot also intelligently dismisses its approval when required approvals are removed.

## Key Features

- ✅ Auto-approves PRs when author owns all changed files OR required approvals exist
- ✅ Auto-dismisses bot approval when approval requirements are no longer met
- ✅ Handles dismissal events intelligently
- ✅ **Supports large PRs** - Pagination handles up to 3000 files correctly
- ✅ **Concise messages** - Smart grouping keeps comments under 1000 characters
- ✅ Detailed logging for debugging and visibility

## How It Works

1. **PR Created/Updated:** Bot checks if author owns all changed files
2. **Approval Given:** Bot checks if required approvals are present
3. **Approval Dismissed:** Bot re-evaluates and dismisses its own approval if requirements no longer met
4. **Re-approval:** Bot re-approves automatically when requirements are met again

## Configuration

The workflow is configured in `.github/workflows/codeowners-auto-approve.yaml` and requires:
- `BOT_PAT` secret with a GitHub token that has `pull_request` write permissions
- CODEOWNERS file in `.github/CODEOWNERS`
- Bot user must be listed in CODEOWNERS for files it should approve


