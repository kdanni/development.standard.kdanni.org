# JavaScript Coding Standard

This document outlines the coding standards and best practices for JavaScript development.

## 1. Scope and Maturity
- **Repositories:** This standard applies to all new and actively developed JavaScript repositories.
- **JavaScript Versions:** All code should target ECMAScript 2021 (ES12) or newer.

## 2. Style and Ergonomics
- **Code Formatting:** All JavaScript code must be formatted with [Prettier](https://prettier.io/) using the default configuration.
- **Linting:** Code should be linted using [ESLint](https://eslint.org/) with a recommended ruleset.
- **General Style:** Adherence to a consistent style guide, such as the Airbnb JavaScript Style Guide, is encouraged.

## 3. Security Defaults
- **Static Analysis:** All code should be scanned for security vulnerabilities using ESLint plugins like `eslint-plugin-security`.

## 4. Testing Expectations
- **Framework:** Tests should be written using a modern testing framework like [Jest](https://jestjs.io/) or [Mocha](https://mochajs.org/).
- **Structure:** Tests should be placed in a `__tests__` or `tests` directory at the root of the repository, and test files should be named with a `.test.js` or `.spec.js` suffix.

## 5. Review Automation
- **CI/CD:** GitHub Actions should be used to automate the running of Prettier, ESLint, and tests on all pull requests.
