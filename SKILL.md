---
name: github-automation-tips
description: "Best practices for GitHub CLI and API automation for agents."
version: 1.0.0
author: Hermes Agent
license: MIT
platforms: [linux, macos, windows]
---

# GitHub Automation Tips

Tips for when `gh` or `git` aren't behaving or aren't available.

## Pitfalls

- **Dependency Management**: When working with automation scripts, rely on `pipx` or `uv` environments. Avoid using global `pip` installs for agent tools.
- **Credential Persistence**: If `gh` is unavailable, ensure `GITHUB_TOKEN` is exported in the environment. If using raw `curl` with API tokens, explicitly note that tokens should be stored in secure locations (never in the prompt/chat history).
- **Tooling Selection**: Prioritize `gh` over `curl` where possible, as `gh` handles authentication, local config, and common workflows significantly more reliably than raw API calls.
- **Installation Issues**: Do not add "gh/git not found" as a permanent skill limitation. Check `gh` status (`gh auth status`) first, and if missing, install it (`sudo apt-get install -y gh`).
