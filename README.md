# action-setup-awslim

This action sets up a [`fujiwara/awslim`](https://github.com/fujiwara/awslim).

[![release](https://github.com/miyamo2/action-setup-awslim/actions/workflows/release.yaml/badge.svg?branch=main)](https://github.com/miyamo2/action-setup-awslim/actions/workflows/release.yaml)
![GitHub Release](https://img.shields.io/github/v/release/miyamo2/action-setup-awslim?label=version)
![GitHub License](https://img.shields.io/github/license/miyamo2/action-setup-awslim)

## Getting Started

### Usage

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: miyamo2/action-setup-awslim@v0

      - name: Run awslim
        run: awslim
```

#### With `awslim` version

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: miyamo2/action-setup-awslim@v0
        with:
          awslim-version: v0.1.0
          
      - name: Run awslim
        run: awslim
```

#### With [`AWSLIM_GEN`](https://github.com/fujiwara/awslim?tab=readme-ov-file#awslim_gen-environment-variable)

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: miyamo2/action-setup-awslim@v0
        with:
          awslim-gen: "ecs,firehose,s3"
          
      - name: Run awslim
        run: awslim
```

#### With [`gen.yaml`](https://github.com/fujiwara/awslim?tab=readme-ov-file#genyaml-configuration-file)

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: miyamo2/action-setup-awslim@v0
        with:
          gen-yaml-path: ".github/your-gen.yml"
          
      - name: Run awslim
        run: awslim
```

#### With `gen.yaml` written inline

added in v0.2.0

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: miyamo2/action-setup-awslim@v0
        with:
          gen-yaml-inline: |
            services:
              s3:
                - GetObject
                - PutObject
              sqs:
          
      - name: Run awslim
        run: awslim
```

### Inputs

| Name              | Description                                 | Default  |
|:------------------|:--------------------------------------------|:---------|
| `awslim-version`  | Version of `awslim` to use.                 | `latest` |
| `awslim-gen`      | Value of `AWSLIM_GEN` environment variable. | -        |
| `gen-yaml-path`   | Path to `gen.yaml` file.                    | -        |
| `gen-yaml-inline` | Can be written gen.yaml with inline.        | -        |

## Support

### fujiwara/awslim

`~v0.1`

### Hosted Runner

| OS      | Support | Note |
|:--------|:--------|:-----|
| Ubuntu  | 〇       | -    |
| macOS   | 〇       | -    |
| Windows | 〇       | -    |

## Contributing

Please feel free to submit issue or PR.

## License

[MIT License](https://github.com/miyamo2/action-setup-awslim/blob/main/LICENSE)