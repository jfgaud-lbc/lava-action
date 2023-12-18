# Lava Action

This action runs [Lava][lava] in your GitHub Actions workflows.

Lava is an open source vulnerability scanner that makes it easy to run
security checks in your local and CI/CD environments.

## Usage

Create a file with the name `.github/workflows/lava.yaml` and the
following content in your repository.

```yaml
name: Lava
on: [push, pull_request]
permissions:
  contents: read
jobs:
  lava:
    name: Lava
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4
      - name: Run Lava Action
        uses: adevinta/lava-action@main
```

## Settings

### Pinning a Lava version

The `version` input parameter specifies the version of Lava to use.

```yaml
- name: Run Lava Action
  uses: adevinta/lava-action@main
  with:
    version: latest
```

### Providing a Lava configuration file

The `config` input parameter specifies the path of the configuration
file passed to Lava.
The path is relative to the root of the repository.

```yaml
- name: Run Lava Action
  uses: adevinta/lava-action@main
  with:
    config: lava.yaml
```

## Contributing

**This project is in an early stage, we are not accepting external
contributions yet.**

To contribute, please read the [contribution
guidelines][contributing].


[lava]: https://github.com/adevinta/lava
[contributing]: /CONTRIBUTING.md
