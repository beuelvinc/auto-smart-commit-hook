# auto-smart-commit-hook
Automated JIRA Issue Key Inclusion in Git Commits  A pragmatically crafted Git hook to streamline the attachment of JIRA issue keys into commit messages for enhanced traceability and workflow automation.

# Git JIRA Hook Integration

This repository includes a custom `prepare-commit-msg` hook for automatically prepending JIRA issue keys to commit messages. This integration ensures clear traceability between code changes and the issues they address without requiring manual entry of the issue keys.

## Getting Started

These instructions will guide you through setting up the custom `prepare-commit-msg` hook so your commit messages will automatically be prepended with the corresponding JIRA issue key when needed.

### Prerequisites

- Git (preferably the latest version)
- A JIRA issue key included in your branch name, when applicable

### Installation

1. Clone your repository to your local machine.
2. Copy the `prepare-commit-msg` script to your project's `.git/hooks/` directory.
3. Your script is now ready for action. The next time you commit with a message, the hook will automatically prepend the JIRA issue ID from your branch name, if applicable.

### Behavior of the Hook Script

The `prepare-commit-msg` hook is structured to:

- Extract a JIRA issue ID from the branch name and append it to the commit message.
- **Avoid duplication**: If the commit message already contains the JIRA issue ID (case-insensitive check), it will not add it again.
- **Branch name dependency**: If your branch name does not contain a JIRA issue ID, the hook will not add anything to the commit message.

An example of a commit command and its resulting commit message with the hook active:


```bash
git commit -m "Add README with setup instructions for prepare-commit-msg hook"
```

JIRA-ID Add README with setup instructions for prepare-commit-msg hook
