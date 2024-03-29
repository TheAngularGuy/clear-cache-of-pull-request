# clear-cache-of-pull-request

A GitHub action to clear the cache of a pull request.

## Usage

```yaml
on:
  pull_request:
    types: [ closed ]

jobs:
  clear-caches:
    runs-on: ubuntu-latest
    steps:
      - name: Clear caches
        uses: theAngularGuy/clear-cache-of-pull-request@vx.x.x
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
```

## Inputs

| Name         | Description                         | Required | Default                                                   |
|--------------|-------------------------------------|----------|-----------------------------------------------------------|
| github-token | The GitHub token to use             | Yes      | none                                                      |
| branch       | The branch to delete the cache from | No       | `refs/pull/${{ github.event.pull_request.number }}/merge` |

> [!TIP]
> To delete all chaches set the `cache-prefix` input to an empty string `''`.

## Permissions

Make sure to give the permissions for actions write in your job.

## Contributing

Contributions to enhance the Composite action are welcome. If you find issues or have suggestions for improvements,
please open an issue or submit a pull request.
