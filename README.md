# action-generate-unmanic-plugin-repo
A GitHub action that automatically generates a built git `repo` branch from a source directory and push the contents of that git branch back to the remote repository hosted on GitHub.

The intention of this action is to easily publish your Unmanic repository whenever the default branch is updated.

## Inputs

### `python_version` 

**Optional** - Python version for building [Default `3.11`].

### `node_version` 

**Optional** - Node version for building [Default `20`].

### `deploy_repo` 

**Optional** - If set to `false`, the repository will be built but **not** pushed back to the `origin/repo` branch [Default `true`].

### `github_token` 

**Optional** - A personal access token (PAT) used to fetch tag and publish the release [Default: `${{ github.token }}`].

## Example usages

Generate the plugin repository and publish it back to GitHub as a `repo` branch.
```yaml
- name: Generate and Publish Unmanic Plugin Repository
  uses: Josh5/action-generate-unmanic-plugin-repo@master
```

Generate the plugin repository without publishing it back to GitHub.
```yaml
- name: Generate Unmanic Plugin Repository
  uses: Josh5/action-generate-unmanic-plugin-repo@master
  with:
    deploy_repo: 'false'
```
