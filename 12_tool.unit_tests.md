# Make use of unit tests

## Goals

Improve code quality and enable change

## Description

Manual testing is boring, error-prone, time consuming and therefore expensive. This leads to bad test coverage, bugs slipping in and people growing reluctant to changing things that already work (or seem to work). Unit tests allow to establish trust towards a code base and enable fearless change. They can also be used to guide the creation of new APIs by providing a test bed. Automated unit tests can be nicely combined with dynamic testing tools such as Valgrind or the AddressSanitizer.

## Environment

All

## Platform

All

## Implementation effort

Very low for green field projects. Establishing unit tests for an existing legacy code base can be a struggle.

## Applicability

\-

## Caveats

- Don't create tests that only run on a special target device (these are integration tests).

## See also

- [Continuous Integration keeps your project healthy](https://toolbox.basyskom.com/3)

## Implementation hints

- Don't get to orthodox about what constitutes a unit, but avoid to create tests that are actually integration tests.
- Make sure your tests execute quickly so developers will actually run them as part of their build process.
- Make sure individual tests are self-contained and do not rely on the post conditions of tests being executed earlier.
