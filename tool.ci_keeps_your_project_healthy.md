# Continuous Integration keeps your project healthy

## Goals

Ensure that the code base stays healthy. Make sure it compiles (for all relevant configurations) and checks are run in a consistent way.

## Description

Continuous Integration ensures that your code base stays healthy by safeguarding that the version in your version control system actually compiles (on all target platforms, for all build variants, with a defined build environment). It also ensures that unit tests are run and provides the base line for creating actual development, test and production releases in a controlled way. These build artifacts are an important foundation for error and crash analysis. A CI system is also an enabler to make the most out of static analysis tools such as clazy or qmllint.

## Environment

All

## Platform

All

## Implementation effort

Highly project dependent.

## Applicability

A must-have if there is more then one developer involved with the project.

## Caveats

## See also

## Implementation hints

If on-premise is a must have a look into Jenkins or gitlab-ci. If the cloud is an option look into Travis or AppVeyor (for Windows).

Put your CI-project description into version control together with the project source itself.
