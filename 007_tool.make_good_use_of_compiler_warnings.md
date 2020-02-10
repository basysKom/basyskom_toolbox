# Make good use of compiler warnings

## Goals

Let the compiler warn you about problems

## Description

Modern C and C++ compilers help you to catch problems early on by emitting warnings at compile time. Make sure warnings are enabled for your project. Often there are temptations to disable them ("we have so many of them", ...). Warnings are not binary, in addition to the different warning levels, individual warnings can be specifically enabled or concisely suppressed. Don't throw out the baby with the bath water – make sure to properly configure warnings.

## Environment

C and C++

## Platform

All

## Implementation effort

Low

## Applicability

All types of projects.

Existing projects: Review the project settings - make sure warnings are enabled.

## Caveats

Existing projects where warnings had been disabled for a long time can generate hundreds of warnings. This should be addressed It is dangerous (and potentially expensive) to work like that.

Potential way to use warning in such projects:

* Enable `-Wall`
* Selectively disable warnings which are very noisy and not too serious.
* Review the rest.
* Communicate with the stakeholders and fix the most serious.
* Cut down on the number of disabled warnings over time.

## See also

* [Treat warnings as error](https://toolbox.basyskom.com/11)

## Implementation hints

GCC/Clang:

```
    -Wall -Wextra
```

Visual Studio:
```
    /Wall
```