---
title: Craft Better Commit Messages with Conventional Commits and Visual Labels
published: false
description: Learn how conventional commit messages can transform your Git workflow and discover GitHub Commit Labels, a powerful tool that adds visual context to your commit history.
tags: github, productivity, git, tools
---

## Craft Better Commit Messages with Conventional Commits and Visual Labels

Have you ever looked at a project's commit history and struggled to understand what changes were made and why? Or spent hours trying to find a specific feature addition or bug fix among hundreds of vague commit messages? You're not alone. The way we document our code changes can make the difference between a maintainable, collaborative project and a confusing mess of undocumented changes.

In this post, we'll explore the power of good commit messages through conventional commits and introduce you to GitHub Commit Labels - a nifty tool that transforms your commit history into an easy-to-navigate, visually informative timeline that both humans and tools can understand.

### Why Good Commit Messages Matter

When we think about documentation, we often focus on READMEs, inline comments, and API docs. But commit messages are arguably your project's most important documentation:

- **They tell a story**: Well-structured commits create a narrative of how your project evolved
- **They save time**: Clear messages make it easy to find when and why changes were introduced
- **They streamline debugging**: Good commit messages help you quickly identify potential sources of bugs
- **They facilitate collaboration**: New team members can understand the codebase's evolution
- **They enable automation**: Structured messages can power release notes, changelogs, and semantic versioning

The difference between `"Fixed stuff"` and `"fix(authentication): resolve token expiration issue causing random logouts"` is enormous. The latter immediately tells you what component was affected, what the issue was, and what user impact it had.

### Enter Conventional Commits

Conventional Commits is a specification for adding human and machine-readable meaning to commit messages. It's a simple set of rules that creates a standardized format:

```
type(scope): description

[optional body]

[optional footer(s)]
```

Let's break it down:

- **Type**: Categorizes the change (e.g., `feat`, `fix`, `docs`, `style`, `refactor`)
- **Scope**: Specifies what part of the codebase was changed (optional)
- **Description**: A short summary of the changes
- **Body**: Detailed explanation of the changes (optional)
- **Footer**: Information about breaking changes or issue references (optional)

Here are some examples:

```
feat(auth): implement OAuth2 authentication flow

fix(api): handle rate limiting errors

docs(readme): add installation guide

style(button): improve hover effects

refactor!(parser): rewrite parser logic (breaking change)
```

The exclamation mark in the last example indicates a breaking change – immediately signaling to other developers that this commit requires attention during updates.

Adopting conventional commits offers several advantages:

- **Automatic versioning**: Tools can determine the next semantic version based on commit types
- **Automated changelogs**: Generate release notes directly from commits
- **Searchable history**: Easily find all bug fixes or feature additions
- **Clearer communication**: Everyone understands the purpose of each commit
- **Onboarding friendly**: New contributors can learn the project patterns

But as powerful as conventional commits are, they're still just text. What if we could make them even more visual and intuitive?

### Introducing GitHub Commit Labels

GitHub Commit Labels is a userscript that transforms conventional commit messages into beautiful, color-coded labels directly in your GitHub interface. It automatically detects commit types and adds visually appealing labels to make your commit history more readable at a glance.

![preview1](https://raw.githubusercontent.com/nazdridoy/github-commit-labels/main/previews/preview1.png)

#### Key Features

- 🏷️ Adds beautiful labels to conventional commit messages
- 🎨 GitHub-style design that matches the platform
- 🌓 Automatic theme detection (light, dark, and dark dimmed)
- 💬 Informative tooltips showing detailed descriptions
- 👆 Toggle button to quickly show/hide labels
- 📤 Export/Import configurations for team sharing
- ⚙️ Fully customizable through a user-friendly configuration panel
- 🔄 Supports multiple aliases for each commit type
- 🎯 Works on commit history and single commit pages
- ⚠️ Special highlighting for BREAKING CHANGES

The result is a commit history that tells you, at a glance, what kind of changes each commit contains:

- 🟢 **Green** for new features and additions
- 🟣 **Purple** for bug fixes
- 🔵 **Blue** for documentation changes
- 🟠 **Orange** for build and deployment updates
- 🔴 **Red** for breaking changes

With GitHub Commit Labels, you can see the big picture of your project's evolution without reading each commit message in detail.

### Getting Started with GitHub Commit Labels

Installation is straightforward:

1. Install a userscript manager:
   - [Tampermonkey](https://www.tampermonkey.net/) (Recommended)
   - [Greasemonkey](https://addons.mozilla.org/en-US/firefox/addon/greasemonkey/)
   - [Violentmonkey](https://violentmonkey.github.io/)

2. Install the script:
   - [Install from Greasy Fork](https://greasyfork.org/en/scripts/526153-github-commit-labels)

That's it! Now visit any GitHub repository with conventional commits to see the transformation:

- [Refined GitHub Sandbox](https://github.com/refined-github/sandbox/commits/conventional-commits/)
- [nGPT](https://github.com/nazdridoy/ngpt/commits/main/)
- [Kokoro TTS](https://github.com/nazdridoy/kokoro-tts/commits/main)

![commit-history](https://raw.githubusercontent.com/nazdridoy/github-commit-labels/main/previews/commit-history.png)

Not seeing labels? GitHub Commit Labels works with conventional commit formats. If a repository doesn't use them, you won't see any labels. But don't worry - you can start using conventional commits in your projects today!

### Customizing Your Experience

GitHub Commit Labels is highly customizable through its configuration panel:

![preview2](https://raw.githubusercontent.com/nazdridoy/github-commit-labels/main/previews/preview2.png)

To access it:
1. Click on your userscript manager's icon and select "GitHub Commit Labels" > "Configure Commit Labels"
   
   OR
   
2. On any GitHub commit history page, look for the ⚙️ gear icon button in the lower right corner of the screen

Here you can:
- Add/remove commit types
- Edit aliases
- Change emojis
- Modify colors
- Toggle prefix removal
- Enable/disable tooltips
- Show/hide floating toggle button
- Export/Import your configuration

The default configuration supports over 20 commit types, including:

- **Feature**: `feat`, `feature`
- **Added**: `added`, `add`
- **Fix**: `fix`, `bugfix`, `fixed`
- **Documentation**: `docs`, `doc`, `documentation`
- **Style**: `style`, `css`
- **Refactor**: `refactor`
- **Performance**: `perf`, `performance`
- **Test**: `test`, `tests`, `testing`
- **Build**: `build`
- **Chore**: `chore`
- **Revert**: `revert`
- **Security**: `security`
- And many more!

You can add your own custom types or modify existing ones to match your team's workflow.

### Start Writing Better Commit Messages

Ready to improve your own commit messages? Here are some tips:

1. **Be specific**: Explain what changed and why
2. **Use the imperative mood**: Write "Add feature" not "Added feature"
3. **Keep the first line under 50 characters**: This ensures good formatting in various Git tools
4. **Reference issues**: Link to issue numbers when applicable
5. **Focus on impact**: Explain the "why" not just the "what"
6. **Be consistent**: Stick to your chosen convention

Following these guidelines alongside conventional commits will dramatically improve your repository's readability.

### Integration with nGPT: AI-Generated Conventional Commits

Want to generate perfect conventional commit messages automatically? [nGPT](https://github.com/nazdridoy/ngpt) provides a powerful CLI tool that can analyze your changes and create well-formatted commits.

```bash
# After staging your changes with git add, run:
ngpt -g
```

nGPT will analyze your git diff and generate a conventional commit message like:

```
feat(auth): implement OAuth2 authentication flow

- [feat] Create new AuthService class to handle token management
- [feat] Implement login/logout functionality in UserController
- [feat] Add configuration options for OAuth providers
- [Update] Update user model to store OAuth tokens
- [feat] Add unit tests for authentication flow
```

When this commit appears in GitHub, GitHub Commit Labels will automatically add a visually appealing "Feature" label next to the commit message.

Want to learn more about nGPT and its other powerful features? Check out the full article: [Supercharge Your Workflow: AI Chatbots, CLI Magic, and Smarter AI Usage with nGPT](https://dev.to/nazdridoy/supercharge-your-workflow-ai-chatbots-cli-magic-and-smarter-ai-usage-with-ngpt-mhg).

### Conclusion: A More Beautiful, Functional Git History

Conventional commits and GitHub Commit Labels together transform the way you interact with your Git history. They turn a wall of text into a visually meaningful timeline that can be understood at a glance, searched by type, or used to automate releases.

By adopting these practices, you:
- Make your repository more maintainable
- Improve team communication
- Enable powerful automation
- Create a foundation for better software versioning
- Make your GitHub interface more beautiful and functional

Whether you're maintaining a personal project or working on a large team, investing in better commit messages pays dividends in productivity and clarity.

Ready to get started? Install GitHub Commit Labels today and begin writing more meaningful commits. Your future self and team members will thank you.

For more information, visit the [GitHub Commit Labels repository](https://github.com/nazdridoy/github-commit-labels).

### Additional Resources

- [Conventional Commits](https://www.conventionalcommits.org/)
- [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)
- [A Note About Git Commit Messages](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
- [nGPT COMMIT_GUIDELINES](https://github.com/nazdridoy/ngpt/blob/main/COMMIT_GUIDELINES.md)
