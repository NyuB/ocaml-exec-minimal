# {{ cookiecutter.name }}

{{ cookiecutter.description }}

## Development

- run the tests: `make test`
- update the tests' expectations: `make test-promote`
- format source code: `make fmt`

## Installation

Run `make install` to build and copy `{{ cookiecutter.main_name }}` to your system. Installation folder is specified with the variable `INSTALL_ROOT` (default to `~/bin`), e.g.

`make install INSTALL_ROOT=/usr/custom/bin`
