# {{ cookiecutter.project_readme_title }}

[![Project
Status](http://www.repostatus.org/badges/latest/concept.svg)](http://www.repostatus.org/#concept)
[![ci](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions/workflows/ci.yaml/badge.svg)](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions/workflows/ci.yaml)

> {{ cookiecutter.project_short_description }}

## About

TODO

## Dependencies

To build the C++ library, you need to the following dependencies:

- `make`, `meson` and `ninja` as build tools (instead of autotools or cmake)

To run the unit tests, lints and everything you'll need

- [`googletest`](https://github.com/google/googletest), 
- `clang-format` for code formatting,
- `cpplint`, `cppcheck` for static code analysis.

To create documentation files you also need to install 

- `doxygen`

You can install most dependencies using conda.  

## Usage

Clone/download the project and run:

```bash
make
```

This build a shared library called `libcppdev.so` in `build/src/`, an executable called `cppdev` and 
a unit test suite in `build/tests`/

In debug mode:

```bash
make debug
```

To document everything call:

```bash
make docs
```

This builds de

To run unit tests, lints, etc. call:

```bash
make test
make format
make lint
make check
```

## Contributing

Contributions in the form of pull requests are more than welcome. In order to contribute:

1) fork and download the repository,
2) create a branch with the name of your new feature (something like `issue/fix-bug-related-to-something` or `feature/implement-new-feature`),
3) install `{{ cookiecutter.project_slug }}`
4) develop code, commit changes and push it to your branch,
5) submit a pull request :slightly_smiling_face:


## Author

{{cookiecutter.full_name}} <a href="mailto:{{cookiecutter.email}}">{{cookiecutter.email}}</a>

