# Cadabra for VS Code

Language support for [Cadabra](https://github.com/abradb/cadabra) database schema files (`.cadabra`).

## Features

- Syntax highlighting for `.cadabra` files
- Custom file icon in explorer and tabs
- Code snippets for all block types
- Bracket matching, auto-closing, and code folding
- Comment toggling (`#` and `/* */`)

## Snippets

| Prefix    | Description                 |
| --------- | --------------------------- |
| `db`      | Database connection block   |
| `table`   | Table with id column        |
| `column`  | Column definition           |
| `columnv` | Column with varchar type    |
| `columnc` | Column with comment         |
| `id`      | Serial primary key          |
| `idbig`   | Bigint identity primary key |
| `created` | created_at timestamp column |
| `updated` | updated_at timestamp column |
| `index`   | Index definition            |
| `fk`      | Foreign key constraint      |
| `enum`    | Enum type                   |
| `check`   | Check constraint            |

## Example

```cadabra
db "postgres" {
  host     = "localhost"
  port     = 5432
  user     = "postgres"
  password = env("DB_PASSWORD")
  name     = "myapp"
}

table "users" {
  column "id" {
    type        = serial
    primary_key = true
  }
  column "email" {
    type     = "varchar(255)"
    not_null = true
    unique   = true
  }
}
```

## Install

Search "Cadabra" in the VS Code extensions marketplace, or:

```
ext install cadabra.cadabra-vscode
```

## Build from Source

Requires Node.js 16+.

```bash
# Clone the repo
git clone https://github.com/abradb/cadabra-vscode.git
cd cadabra-vscode

# Install vsce (VS Code Extension CLI)
npm install -g @vscode/vsce

# Package the extension
vsce package

# Install locally (use the generated .vsix filename)
code --install-extension cadabra-vscode-*.vsix
```

### Development

To iterate without re-packaging, symlink the extension into VS Code:

```bash
ln -s "$(pwd)" ~/.vscode/extensions/cadabra.cadabra-vscode
```

Reload VS Code (`Cmd+Shift+P` > "Developer: Reload Window") after making changes.

## Links

- [Cadabra CLI](https://github.com/abradb/cadabra)
- [Report issues](https://github.com/abradb/cadabra-vscode/issues)
