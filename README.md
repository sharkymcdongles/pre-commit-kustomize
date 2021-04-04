# pre-commit-kustomize
pre-commit hook which runs kustomize. This is a system hook, so you need to instlal the binary yourself. Alternatively, you can run this where kustomize already exists e.g. a gitlab-runner using an image containing a kustomize binary.

## Example of .pre-commit-config.yaml for a flux repo with a development folder containing your kustomizations:
```yaml
# See https://pre-commit.com for more information
# See https://pre-commit.com/hooks.html for more hooks
repos:
-   repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v2.4.0
    hooks:
    -   id: check-yaml
        args: [--allow-multiple-documents]
    -   id: check-added-large-files
-   repo: https://github.com/dmitri-lerko/pre-commit-docker-kustomize
    rev: f3a8533
    hooks:
    -   id: kustomize
        name: kustomize-development
        args: [./development]
        verbose: false


Forked from here: https://github.com/dmitri-lerko/pre-commit-docker-kustomize
