# Treat compiler warnings as errors

## Goals

Prevent problematic code from silently "creeping" in.

## Description

Modern C and C++ compilers are quite good at generating warnings for problematic issues. By default, a warning will not stop the compiler from generating code. Consider to treat compiler warnings as errors to prevent issues from creeping into your code base.

## Environment

C, C++, Qt

## Platform

All

## Implementation effort

Minor, given that your project is already compiling without warnings.

## Applicability

All projects with a clearly defined target toolchain.

## Caveats

* Treating warnings as errors can be a considerable headache if there is a large range of toolchains/platforms to support as warnings generated might change over time.
* Do not enable "warning as errors" for releases that are consumed by an undefined and wide-ranging user base (for example when releasing software within your organization, to customers or as open source).

## See also

* [Make good use of compiler warnings](https://toolbox.basyskom.com/7)
* [Avoid deprecated Qt](https://toolbox.basyskom.com/1)

## Implementation hints

* gcc/clang: `-WError`
* Visual Studio:  `/WX` switch or „Treat Warnings as Errors“ in project properties
* Newer compiler versions tend to emit more warnings. The same compiler targeting a different platform might generate slightly different warnings. Make sure  there is a central build flag as an escape hatch. Have a CI system in place to enforce "warnings as errors" for your officially supported toolchain(s).
