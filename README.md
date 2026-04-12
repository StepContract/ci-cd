# ci-cd
StepContract CI/CD repository. Here, find reusable CI/CD components (testing, container build/push, deploy, commitlint, semantic-release).

## Reusable workflows

### Semantic release

Use `.github/workflows/semantic-release.yml` as a reusable workflow from application repositories.

```yaml
jobs:
  release:
    uses: stepcontract/ci-cd/.github/workflows/semantic-release.yml@main
    secrets:
      github_token: ${{ secrets.GITHUB_TOKEN }}
```

If the caller repository needs custom semantic-release plugins or package-manager setup, pass an `install_command` and keep the semantic-release config in that repository.
