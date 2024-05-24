# action-setup-awslim

This action sets up a [`fujiwara/awslim`](https://github.com/fujiwara/awslim)

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
          awslim-version: v0.0.1
          
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

### Inputs

| Name             | Description                                     | Default  |
|:-----------------|:------------------------------------------------|:---------|
| `awslim-version` | The version of `awslim` to use.                 | `latest` |
| `awslim-gen`     | The value of `AWSLIM_GEN` environment variable. | -        |
| `gen-yaml-path`  | The path to `gen.yaml` file.                    | -        |

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