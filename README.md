# NLW - Barcode Generator

This project was helded in the 1st edition of 2024 of Rocketseat NLW.
The idea is simple, generate an barcode image after receiving a product-code.


## Config
1. Virtual Env
```shelll
1. pip install virtualenv
2. python -m venv .venv
```
2. Linter for python
```shell
1. pip install pylint
```
```generate linter config file```
```shell
2. pylint --generate-rcfile > .pylintrc
```

3. Python Pre-commit
3.1 Create a filename
```shell
touch .pre-commit-config.yaml or echo '' > .pre-commit-config.yaml
```
3.2 Append this info
```yaml
repos:
  - repo: local
    hooks:
      - id: pylint
        name: pylint
        entry: pylint
        language: system
        types: [python]
        args:
          [
            "-rn", # Only display messages
            "-sn", # Don't display the source
            "--rcfile=.pylintrc", # Link to your config file
            "--load-plugins=pylint.extensions.docparams", # Load an extension
          ]
```
3.3 Install the configurations
```shell
pre-commit install
```