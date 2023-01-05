# Hatch Test Selection

The Pytest documentation introduces the ability to change both the files
searched for tests and the function names that are considered tests. The Pytest
default is to only look for tests inside `test_*.py` or `*_test.py` files, and
to look for function names prefixed with `test` inside those files. (Pytest also
looks for class names prefixed with `Test` but we will not cover those here).

This repository demonstrates how to choose alternate Pytest file and function
names when using Hatch. Following the suggestions
[here](https://docs.pytest.org/en/7.1.x/example/pythoncollection.html#customizing-test-collection),
we configure Pytest to search all python files for tests. Using the example
[here](https://docs.pytest.org/en/7.1.x/example/pythoncollection.html#changing-naming-conventions)
we consider a test function to be one with a name ending in `_check`. The parts
of the `pytest.ini` file that produce these effects for Pytest look like this:

```
python_files = *.py  # Discover tests in every python file
# Only consider a function to be a test if it ends with '_check'
python_functions = *_check
```

## Installation

To use this you must first install Hatch. The [instructions](https://hatch.pypa.io/latest/install/) are summarized here:

1. I found it easiest to use [Pipx](https://github.com/pypa/pipx) to install
   Hatch: \
  `pipx install hatch`

2. To start a session, run `hatch shell`. The first time you do this it will
   download and install all the necessary packages in a virtual environment.

3. Run `pytest` to see the results.
