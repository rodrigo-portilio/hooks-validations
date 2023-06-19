# Hooks Validations

## Explanation of Hook Validations

Hooks are scripts that can be executed automatically at certain points in the Git workflow. In this project, two hooks are provided: pre-commit and prepare-commit-message. Let's understand their purposes and how they validate commits.

### pre-commit Hook
The pre-commit hook is executed right before creating a commit. Its purpose is to validate the branch name and ensure it follows a specific pattern. The script checks if the branch name matches the regular expression pattern ^(feature|bugfix|release|hotfix)\/[a-z0-9._-]+$. If the branch name does not match this pattern, the commit is rejected and an error message is displayed, prompting you to change the branch name to a valid format.

### prepare-commit-message Hook
The prepare-commit-message hook is executed after creating a commit message but before the commit is finalized. It validates the commit message to ensure it follows a specific format. The script checks if the commit message matches the regular expression pattern ^(feat|fix|docs|style|refactor|test|chore|perf|other)(\((.)\))?: (.*)[a-zA-Z\s]*+$. If the commit message does not match this format, the commit is rejected, and an error message is displayed, providing an example of a valid commit message format.

## Setting File Permissions

If you are using a MacOS or Linux, you need to execute the following steps first to set the file permissions:

```bash
chmod + x pre-commit
chmod + x prepare-commit-message
```

## Usage

To use this hook in a specific project, folow these steps:

```bash
git congig core.hooksPath <path/to/this/repository>
```

If you want to use this hook globally for all repositories, run the following command:


```bash
git congig --global core.hooksPath <path/to/this/repository>
```

Please make sure to replace <path/to/this/repository> with the actual path to the repository where the hooks are located.