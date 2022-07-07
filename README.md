# openapi-generator-action
Github action for the generation process of generating docs and code

Fork of [openapi-generator](https://github.com/wirthual/deutschland-generator-action)

## Inputs

| Input                | Required | Default      | Description                                                       | Example                              |
|----------------------|----------|--------------|-------------------------------------------------------------------|--------------------------------------|
| `openapi-file`       | true     | openapi.yaml | The path to the OpenAPI document to generate a client library for | ./api/openapi.json                   |



## Example

```yaml
on: [push, pull_request]
jobs:
  openapi_generation:
    name: "OpenAPI Generation"
    runs-on: ubuntu-latest
    strategy:
      fail-fast: false
      matrix:
        python-version: ['3.7.8' ]
    steps:
      - name: "Generate deutschland code"
        uses: t-huyeng/openapi-action@latest
        with:
          openapi-file: ${{ github.workspace }}/openapi.yaml
```