# python-template
[![Build Status](https://img.shields.io/travis/derek-miller/python-template.svg)](https://travis-ci.org/derek-miller/python-template)
[![Docs Status](https://readthedocs.org/projects/python-template2/badge/?version=latest)](http://python-template2.readthedocs.io/en/latest/?badge=latest)
[![GitHub release](https://img.shields.io/pypi/v/python-template.svg)](https://pypi.python.org/pypi/python-template/)
[![Requires.io](https://img.shields.io/requires/github/derek-miller/python-template.svg)](https://requires.io/github/derek-miller/python-template/requirements/?branch=master)
[![Codecov](https://img.shields.io/codecov/c/github/derek-miller/python-template.svg)](https://codecov.io/gh/derek-miller/python-template)
[![GitHub issues](https://img.shields.io/github/issues/derek-miller/python-template.svg)](https://github.com/derek-miller/python-template/issues)
[![license](https://img.shields.io/github/license/derek-miller/python-template.svg)](https://github.com/derek-miller/python-template/blob/master/LICENSE)

Python library template project.
***

### Install

```bash
pip install python-template
```

Or to manually install, execute the following commands:
```bash
git clone https://github.com/derek-miller/python-template.git
cd python-template
python setup.py install
```
***

## Developers

### Makefile Targets

> Makefile commands will only work inside a [virtualenv](https://virtualenv.pypa.io/en/latest/) or a
[condaenv](http://conda.pydata.org/docs/using/envs.html)

#### `make init`

Initializes the virtualenv with an up-to-date version of setuptools, pip, and
[pip-tools](https://github.com/nvie/pip-tools/).

#### `make install`

Runs [pip-compile] with `requirements/py<current interpreter version>.txt` and produces a compiled requirement file in
the `.cache` directory . The [pip-sync] is ran with the newly compiled requirements file. This makes sure you are
running with the latest release of dependencies, assuming you haven't pinned them in the
`requirements/py<current interpreter version>.txt` file.

#### `make lint`

Runs [pylint] and [pep8] on all packages in the project directory.

#### `make test`

Runs [py.test] tests located inside the tests/ folder and any test files nested in a package in the project directory.
Coverage is only calculated in this target.

#### `make test-unit`

Same as `make test` excluding coverage and tests marked as `integration`.

#### `make test-integration`

Same as `make test` excluding coverage and tests **not** marked as `integration`.

#### `make build`

Builds a wheel using setuptools' bdist_wheel command. Locally builds are tagged with dev (ex 0.1.0+dev). In the travis
build environment the wheel is tagged with the job number (ex. 0.1.0+build1.1).

#### `make clean`

Cleans the project of compiled python files and files generated by the above commands such as build and dist directories.


[pylint]: https://www.pylint.org/
[pep8]: https://pep8.readthedocs.io/en/latest/
[py.test]: http://pytest.org/latest/
[pip-tools]: https://github.com/nvie/pip-tools/#pip-tools--pip-compile--pip-sync
[pip-compile]: https://github.com/nvie/pip-tools/#example-usage-for-pip-compile
[pip-sync]: https://github.com/nvie/pip-tools/#example-usage-for-pip-sync