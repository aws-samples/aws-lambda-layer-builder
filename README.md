# AWS Lambda Layer Builder


If you've ever needed to build a Lambda layer
quickly and easily, this tool is for you.


## Prerequisites

*  [Docker](https://www.docker.com/products/docker-desktop)
*  [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)


## Installation

Copy the `make-layer` file to a location on your path, e.g. `cp make-layer /usr/local/bin/`.

Download and install with a single command by copying and pasting the following into a terminal:

```bash
INSTALL_LOC=/usr/local/bin/make-layer; curl https://raw.githubusercontent.com/aws-samples/aws-lambda-layer-builder/main/make-layer > $INSTALL_LOC; chmod +x $INSTALL_LOC
```


## Usage

This tool can either take a list of packages to include in the layer,
or a package manifest file valid for the specified runtime. It assumes
the AWS CLI is already properly configured.

Run `make-layer` without parameters for full usage instructions.

### Manifest File

```bash
make-layer NAME RUNTIME MANIFEST
```

*  `NAME` is a valid Lambda layer name (letters, numbers, hyphens, and underscores)
*  `RUNTIME` is a valid Lambda runtime identifier (e.g. `nodejs14.x`, `python3.8`)
*  `MANIFEST` is the full path and filename of a valid manifest file. The following
   types are supported:
   *  Node.js: [`package.json`](https://docs.npmjs.com/files/package.json/)
   *  Python: [`requirements.txt`](https://pip.pypa.io/en/stable/user_guide/#requirements-files)

If the manifest file is not found the parameters are presumed to be explicit package names.

### Explicit List

```bash
make-layer NAME RUNTIME PACKAGE_1 [PACKAGE_2] ...
```

*  `PACKAGE_1`, `PACKAGE_2`, etc. are the packages to be installed.

## To-Do

*  Add parameter for AWS profile to use (currently uses default, or honors AWS_PROFILE)
*  Add support for additional runtimes


## Contributing

Pull requests are welcomed. Please review the [Contributing Guidelines](CONTRIBUTING.md)
and the [Code of Conduct](CODE_OF_CONDUCT.md).


## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.


## Authors

*  Drew Mullen (drmullen@amazon.com)
*  Jud Neer (judneer@amazon.com)


## License

This project is licensed under the MIT-0 License. See the [LICENSE](LICENSE) file for details.
