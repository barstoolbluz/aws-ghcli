# Flox Environment: GitHub + AWS with 1Password Integration

## Overview

This Flox environment sets up a development workspace with `git`, `gh`, and `awscli2`, integrating with 1Password for secure credential management. It ensures seamless authentication for GitHub and AWS by wrapping CLI commands to retrieve tokens and keys dynamically from 1Password.

## Installed Packages

- `gitFull`: Full Git installation.
- `gh`: GitHub CLI.
- `awscli2`: AWS CLI v2.
- `_1password`: Required for credential retrieval.
- `gum`: Lightweight interactive shell utilities.

## How It Works

- On activation, the environment checks for an active 1Password session.
- If not authenticated, it prompts for 1Password login and stores the session token.
- Wrapper functions redefine `git`, `gh`, and `aws` to pull credentials from 1Password dynamically:
  - `git` auto-injects GitHub tokens for operations like `push`, `pull`, `clone`, etc.
  - `gh` runs with GitHub authentication from 1Password.
  - `aws` retrieves AWS credentials from 1Password and injects them as environment variables.

## Usage

### Activate the Environment

```
flox activate
```
