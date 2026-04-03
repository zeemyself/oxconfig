# @zeemyself/oxconfig

Shared default configuration package for:

- `oxfmt` (`.oxfmtrc.json`)
- `oxlint` (`.oxlintrc.json`)

## Install

In any project where you want to reuse these defaults:

```bash
npm install -D @zeemyself/oxconfig oxfmt oxlint
```

## Use with `extends`

### `oxlint`

Create/update your project's `.oxlintrc.json`:

```json
{
  "extends": ["@zeemyself/oxconfig/oxlint"]
}
```

Add local overrides if needed:

```json
{
  "extends": ["@zeemyself/oxconfig/oxlint"],
  "rules": {
    "no-alert": "warn"
  }
}
```

### `oxfmt`

Create/update your project's `.oxfmtrc.json`:

```json
{
  "extends": ["@zeemyself/oxconfig/oxfmt"]
}
```

If your `oxfmt` version does not support `extends`, copy the package config as your local `.oxfmtrc.json`:

```bash
cp ./node_modules/@zeemyself/oxconfig/.oxfmtrc.json ./.oxfmtrc.json
```

## Included defaults

### `.oxfmtrc.json`

- `semi: false`
- `singleQuote: true`
- `tabWidth: 2`
- `trailingComma: "all"`
- `printWidth: 80`

### `.oxlintrc.json`

- Plugins: `react`, `typescript`, `unicorn`, `import`
- Categories:
  - `correctness: warn`
  - `perf: warn`
- Rules:
  - `no-console: off`
  - `no-debugger: warn`
- Environment:
  - `browser: true`
- Ignored paths:
  - `dist`
  - `node_modules`
