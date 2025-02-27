[<img src="https://img.shields.io/npm/v/eslint-plugin-filename-export?style=for-the-badge">](https://www.npmjs.com/package/eslint-plugin-filename-export)
<img src="https://img.shields.io/npm/dt/eslint-plugin-filename-export?style=for-the-badge" >
[<img src="https://img.shields.io/bundlephobia/minzip/eslint-plugin-filename-export?style=for-the-badge">](https://bundlephobia.com/package/eslint-plugin-filename-export)

# eslint-plugin-filename-export

This plugin enforces that the filename matches to a named export. This rule ignores index files, spec/test files, types files, and files with no named exports, and currently has no configuration options.

## Installation

Install with your package manager of choice:

```bash
pnpm i -D eslint-plugin-filename-export
```

Add to your ESLint config:

```json
{
  "plugins": ["eslint-plugin-filename-export"],
  "rules": {
    "filename-export/match-named-export": "error",
    "filename-export/match-default-export": "error"
  }
}
```

## Rules

`filename-export/match-named-export` - Enforces that the filename matches to a named export.
`filename-export/match-default-export` - Enforces that filenames match the name of the default export.

These rules ignore index files, test/spec files, and files that have no relevant exports by default. Additionally, files with a default export will be ignored by the `match-named-export` rule.

If you want to add additional filename exemptions, use the ESLint's builting filename overrides.

## Options

Both of these rules have the following available options:

- `casing`:
  - `strict`: Filenames much match in case to the exports
  - `loose`: Filenames do not need to match case (`default`)

These can be passed as a second item in an array to the rule as follows

```json
"filename-export/match-named-export": [
  "error",
  {
    "casing": "strict"
  }
]
```

## Roadmap

This plugin is mainly being produced for personal use. If you are interested in using it, but need additional features, please open an issue and I will consider adding them.
