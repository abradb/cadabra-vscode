# Contributing to Cadabra for VS Code

Thanks for your interest in contributing to the Cadabra VS Code extension.

## Getting Started

```bash
git clone https://github.com/abradb/cadabra-vscode.git
cd cadabra-vscode
```

No dependencies to install. This is a declarative extension with no TypeScript or JavaScript runtime code.

## Testing Locally

Symlink the extension into VS Code:

```bash
ln -s "$(pwd)" ~/.vscode/extensions/abradb.cadabra-vscode
```

Reload VS Code (`Cmd+Shift+P` then "Developer: Reload Window") after making changes.

## Project Structure

```
syntaxes/       TextMate grammar for syntax highlighting
snippets/       Code snippets
icons/          File icons (light and dark variants)
package.json    Extension manifest
language-configuration.json   Brackets, comments, folding
```

## Commit Messages

We use [Conventional Commits](https://www.conventionalcommits.org/) to auto-generate changelogs and version bumps.

| Prefix   | Meaning         | Version bump |
| -------- | --------------- | ------------ |
| `feat!:` | Breaking change | Major        |
| `feat:`  | New feature     | Minor        |
| `fix:`   | Bug fix         | Patch        |
| `chore:` | Maintenance     | None         |

## Pull Requests

1. Fork the repo
2. Create a branch: `feat/your-feature` or `fix/your-fix`
3. Make your changes
4. Test locally by symlinking and reloading VS Code
5. Commit with a conventional commit message
6. Open a PR against `main`

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
