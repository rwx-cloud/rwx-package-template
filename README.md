# example-org/example-package

A short description of what this package does.

## Usage

Basic usage:

```yaml
tasks:
  - key: example
    call: example-org/example-package 1.0.0
    with:
      required-param: my-value
```

With all parameters:

```yaml
tasks:
  - key: example
    call: example-org/example-package 1.0.0
    with:
      required-param: my-value
      optional-param-with-default: custom-value
      optional-param: another-value
```

## Output Values

Output values are optional.

| Name | Description |
| --- | --- |
| `result` | Description of the output value |

Access outputs from a calling task:

```yaml
tasks:
  - key: example
    call: example-org/example-package 1.0.0
    with:
      required-param: my-value

  - key: use-output
    use: example
    run: echo "Result is $RESULT"
    env:
      RESULT: ${{ tasks.example.values.result }}
```
