# AWS Lambda Layer Builder


If you've ever needed to build a Python Lambda layer
quickly and easily, this tool is for you.


## Prerequisites

*  [Docker](https://www.docker.com/products/docker-desktop)
*  [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)


## Installation

Copy the `make-layer` file to a location on your path, e.g. `cp make-layer /usr/local/bin/`.


## Usage

This tool can either take a list of packages to include in the layer,
or a requirements file. It assumes the AWS CLI is already properly
configured.

Run `make-layer -h` for full usage instructions.

### Explicit List

```python3
make-layer -n LAYER_NAME -p PYTHON_RUNTIME PACKAGE_1 [PACKAGE_2] ..."
```

`LAYER_NAME` is a valid Lambda layer name (letters, numbers, hyphens, and underscores),
`PYTHON_RUNTIME` is a valid Python runtime identifier (e.g. `python2.7`, `python3.8`), and
`PACKAGE_1`, `PACKAGE_2`, etc. are the Python packages to be installed.

### Requirements File

```python3
make-layer -n LAYER_NAME -p PYTHON_RUNTIME -r PATH_TO_REQUIREMENTS_FILE
```

`PATH_TO_REQUIREMENTS_FILE` is the full path and filename of a valid `pip`
[requirements file](https://pip.pypa.io/en/stable/user_guide/#requirements-files).


## To-Do

*  Add parameter for AWS profile to use (currently uses default, or honors AWS_PROFILE)
*  Add support for additional runtimes other than Python (e.g. Node.js)


## Contributing

Pull requests are welcomed. Please lint all changes with `flake8 --max-line-length=120`
before submitting. Also review the [Contributing Guidelines](CONTRIBUTING.md) and
the [Code of Conduct](CODE_OF_CONDUCT.md).


## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.


## Authors

*  Jud Neer (judneer@amazon.com)


## License

This project is licensed under the MIT-0 License. See the [LICENSE](LICENSE) file for details.
