# setup-strucpp

GitHub Action to download and configure [STruC++](https://github.com/Autonomy-Logic/STruCpp) (IEC 61131-3 Structured Text to C++ compiler).

Auto-detects runner OS/architecture, downloads the correct release binary, caches it, and adds it to PATH.

## Usage

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: Autonomy-Logic/setup-strucpp@v1
  - run: strucpp source.st -o output.cpp
```

### Run tests

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: Autonomy-Logic/setup-strucpp@v1
  - run: strucpp source.st -o output.cpp --test test.st
```

### Pin a specific version

```yaml
- uses: Autonomy-Logic/setup-strucpp@v1
  with:
    version: '0.1.4'
```

## Inputs

| Input     | Description                              | Default    |
|-----------|------------------------------------------|------------|
| `version` | STruC++ version (e.g., `0.1.4`)         | `latest`   |
| `token`   | GitHub token for downloading releases    | `github.token` |

## Outputs

| Output    | Description                              |
|-----------|------------------------------------------|
| `version` | Installed STruC++ version                |
| `path`    | Path to STruC++ installation directory   |

## Supported Platforms

| Runner OS  | Architecture |
|------------|-------------|
| Linux      | x64, arm64  |
| macOS      | x64, arm64  |
| Windows    | x64, arm64  |
