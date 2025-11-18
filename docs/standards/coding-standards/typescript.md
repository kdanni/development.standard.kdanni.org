# TypeScript Coding Standard

This document outlines the coding standards and best practices for TypeScript development.

## 1. Scope and Maturity
- **Repositories:** This standard applies to all new and actively developed TypeScript repositories.
- **TypeScript Versions:** All code should target the latest stable version of TypeScript.

## 2. Style and Ergonomics
- **Code Formatting:** All TypeScript code must be formatted with [Prettier](https://prettier.io/) using the default configuration.
- **Linting:** Code should be linted using [ESLint](https://eslint.org/) with the `@typescript-eslint/parser` and recommended TypeScript-specific rules.
- **Type Safety:** `tsconfig.json` should have `strict` mode enabled.

## 3. Security Defaults
- **Static Analysis:** All code should be scanned for security vulnerabilities using ESLint plugins like `eslint-plugin-security`.

## 4. Testing Expectations
- **Framework:** Tests should be written using a modern testing framework that supports TypeScript, such as [Jest](https://jestjs.io/) with `ts-jest`.
- **Structure:** Tests should be placed in a `__tests__` or `tests` directory at the root of the repository, and test files should be named with a `.test.ts` or `.spec.ts` suffix.

## 5. Review Automation
- **CI/CD:** GitHub Actions should be used to automate type checking, formatting, linting, and running tests on all pull requests.
