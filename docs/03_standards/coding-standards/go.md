# Go Coding Standard

This document outlines the coding standards and best practices for Go development.

## 1. Scope and Maturity
- **Repositories:** This standard applies to all new and actively developed Go repositories.
- **Go Versions:** All code should target the latest stable version of Go.

## 2. Style and Ergonomics
- **Code Formatting:** All Go code must be formatted with `gofmt`. This is non-negotiable.
- **Linting:** Code should be linted using `golangci-lint`, which aggregates many linters, including `golint` and `govet`.
- **General Style:** Adherence to the principles outlined in [Effective Go](https://go.dev/doc/effective_go) is required.

## 3. Security Defaults
- **Static Analysis:** All code should be scanned for security vulnerabilities using `gosec`.

## 4. Testing Expectations
- **Framework:** Tests should be written using the standard library `testing` package.
- **Structure:** Tests should be in the same package as the code they test, in files named with a `_test.go` suffix.

## 5. Review Automation
- **CI/CD:** GitHub Actions should be used to automate formatting checks (`gofmt -l .`), linting, security scanning, and running tests on all pull requests.
