# Cadabra for VS Code

Language support for [Cadabra](https://github.com/abradb/cadabra) database schema files (`.cadabra`).

## Features

- Syntax highlighting for `.cadabra` files
- Custom file icon in explorer and tabs
- Code snippets for all block types
- Bracket matching, auto-closing, and code folding
- Comment toggling (`#` and `/* */`)

## Snippets

| Prefix | Description |
|---|---|
| `db` | Database connection block |
| `table` | Table with id column |
| `column` | Column definition |
| `columnv` | Column with varchar type |
| `columnc` | Column with comment |
| `id` | Serial primary key |
| `idbig` | Bigint identity primary key |
| `created` | created_at timestamp column |
| `updated` | updated_at timestamp column |
| `index` | Index definition |
| `fk` | Foreign key constraint |
| `enum` | Enum type |
| `check` | Check constraint |

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

## Links

- [Cadabra CLI](https://github.com/abradb/cadabra)
- [Report issues](https://github.com/abradb/cadabra-vscode/issues)
