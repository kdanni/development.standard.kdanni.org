# Python Coding Standard

This document outlines the coding standards and best practices for Python development.

## 1. Scope and Maturity
- **Repositories:** This standard applies to all new and actively developed Python repositories.
- **Python Versions:** All code should target Python 3.8 or newer.

## 2. Style and Ergonomics
- **Code Formatting:** All Python code must be formatted with [Black](https://github.com/psf/black) using the default configuration.
- **Import Sorting:** Imports should be automatically sorted using [isort](https://pycqa.github.io/isort/).
- **General Style:** Adherence to [PEP 8](https://www.python.org/dev/peps/pep-0008/) is required.

## 3. Security Defaults
- **Static Analysis:** All code should be scanned for security vulnerabilities using [bandit](https://bandit.readthedocs.io/en/latest/).

## 4. Testing Expectations
- **Framework:** Tests should be written using the [pytest](https://docs.pytest.org/en/stable/) framework.
- **Structure:** Tests should be placed in a `tests` directory at the root of the repository.

## 5. Review Automation
- **CI/CD:** GitHub Actions should be used to automate the running of Black, isort, bandit, and pytest on all pull requests.
