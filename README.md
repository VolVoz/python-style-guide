# 🐍 Babylon Python Style Guide


This document is constructed from the results of a poll across the Python Team. It is however not "final". **Pull requests welcome** to evolve it over time.


1. [Documentation](#documentation)
2. [Testing](#testing)
3. [Coding style / Linting](#coding-style--linting)
4. [Exceptions](#exceptions)
5. [Code Organisation](#code-organisation)
6. [Python Packaging](#python-packaging)
7. [Design](e#design)


### Documentation

- Each project must have a README file (in markdown or rst format).
- README must provide instructions to: build project, run tests, run project locally, contact team owning it
- Use CONTRIBUTING file to provide any project-specific conventions or how-to details developers need to know when working on the project.


### Testing

- Tests should be written using py.test (https://docs.pytest.org).
- Each project must report [coverage](https://coverage.readthedocs.io) and publish results to [codeclimate](https://codeclimate.com).
- Each project should display coverage & code climate score "badges" in README file.
- Tests should be integration tests where possible. Try not to go overboard with Mocking (vague statement, judge case by case).


### Coding style / Linting

- Each project must have a [flake8](https://pypi.python.org/pypi/flake8) linter.
- Each project must follow [PEP8](https://www.python.org/dev/peps/pep-0008/) (inc. 79 chars limit).
- Docstrings must follow PEP257 (https://www.python.org/dev/peps/pep-0257/).
- Functions with more than 1 parameter must [force keyword arguments](https://www.python.org/dev/peps/pep-3102/).
- All class `__init__` methods must [force keyword arguments](https://www.python.org/dev/peps/pep-3102/).
- Follow Python [EAFP principal](http://python.net/~goodger/projects/pycon/2007/idiomatic/handout.html#eafp-vs-lbyl) where possible.
- Use relative absolute imports within projects, full absolute imports in testing code.

  ```python
  # in testing code
  from project.subpackage import magic_beans
  # in project code
  from .sub_package import magic_beans
  ```
- Don't use single letter variable names, unless within a list comprehension.
- Never put any code in the __init__.py of a module (except namespace stitching imports).


### Exceptions

- Only define custom exceptions when you have a need to catch it specifically.
- Use [standard libary exceptions](https://docs.python.org/3/library/exceptions.html) where possible.
- Always include a descriptive message when an exception is raised.

### Code Organisation

- Project should have a single top-level Python package.
- Project requirements should be split into `requirements.txt` `test_requirements.txt` files etc.


### Python Packaging

- Python Packages must follow [Semantic Versioning](http://semver.org/).
- Reusable (non project specific) code should live in "[babylon-python](https://github.com/Babylonpartners/babylon-python)", or be open-sourced and added to [PyPI](https://pypi.python.org/pypi) (devops have the babylon PyPI credentials).

### Design

- Use Abstract Base Classes to enforce conventions in your projects, where it makes sense.
