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

Low to medium - provided that a project already implements "Proper automatic builds" and has a practical way to manage external dependencies.

## Applicability

A must-have if there is more then one developer involved with the project.

## Caveats

## See also

* [Proper automated builds](https://toolbox.basyskom.com/FIXME_have_we_lost_this_card?)

## Implementation hints

* If "on-premise" is a must have a look into Jenkins or gitlab-ci. If the cloud is an option look into Travis or AppVeyor (for Windows).
* Traditionally the CI configuration of a project was kept separated from the project itself (often even outside of version control). Placing the CI configuration alongside the actual project nowadays supported by a lot of systems and is adding a lot of control and flexibility. Examples are Jenkins pipelines or Travis yaml files.
