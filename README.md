[![GitHub license](https://img.shields.io/github/license/op5dev/current-pr?logo=apache&label=License)](LICENSE "Apache License 2.0.")
[![GitHub release tag](https://img.shields.io/github/v/release/op5dev/current-pr?logo=semanticrelease&label=Release)](https://github.com/op5dev/current-pr/releases "View all releases.")
*
[![GitHub repository stargazers](https://img.shields.io/github/stars/op5dev/current-pr)](https://github.com/op5dev/current-pr "Become a stargazer.")

# Get Current PR Data

Supported event triggers:

- `issue_comment`
- `merge_group`
- `push`
- `pull_request` (of course!)

</br>

### View: [Usage Examples](#usage-examples) · [In/Output Parameters](#parameters) · [Security](#security) · [Changelog](#changelog) · [License](#license)

</br>

## Usage Examples

```yaml
on:
  issue_comment:
  merge_group:
  push:

jobs:
  test:
    runs-on: ubuntu-latest

    permissions:
      pull-requests: read # Required to get PR data.

    steps:
      - id: pr
        uses: op5dev/current-pr@v1
      - run: |
          echo "PR number ${{ steps.pr.outputs.number }}"
          echo "PR branch ${{ steps.pr.outputs.branch }}"
```

</br>

## Parameters

### Inputs

| Name    | Description                                                                |
| ------- | -------------------------------------------------------------------------- |
| `token` | Specify a GitHub token (not required).</br>Default: `${{ github.token }}`. |

</br>

### Outputs

| Name     | Description        |
| -------- | ------------------ |
| `branch` | Current PR branch. |
| `number` | Current PR number. |

</br>

## Security

View [security policy and reporting instructions](SECURITY.md).

</br>

## Changelog

View [all notable changes](https://github.com/op5dev/current-pr/releases "Releases.") to this project in [Keep a Changelog](https://keepachangelog.com "Keep a Changelog.") format, which adheres to [Semantic Versioning](https://semver.org "Semantic Versioning.").

> [!TIP]
>
> All forms of **contribution are very welcome** and deeply appreciated for fostering open-source projects.
>
> - [Create a PR](https://github.com/op5dev/current-pr/pulls "Create a pull request.") to contribute changes you'd like to see.
> - [Raise an issue](https://github.com/op5dev/current-pr/issues "Raise an issue.") to propose changes or report unexpected behavior.
> - [Open a discussion](https://github.com/op5dev/current-pr/discussions "Open a discussion.") to discuss broader topics or questions.
> - [Become a stargazer](https://github.com/op5dev/current-pr/stargazers "Become a stargazer.") if you find this project useful.

</br>

### To-Do

- Workflow event triggers like `workflow_dispatch`, and `workflow_run` (fork) will be added in upcoming releases.

</br>

## License

- This project is licensed under the permissive [Apache License 2.0](LICENSE "Apache License 2.0.").
- All works herein are my own, shared of my own volition, and [contributors](https://github.com/op5dev/current-pr/graphs/contributors "Contributors.").
- Copyright 2016-2025 [Rishav Dhar](https://github.com/rdhar "Rishav Dhar's GitHub profile.") — All wrongs reserved.
