# Use clazy to avoid Qt API pitfalls

## Goals

Write good Qt code. Avoid the use of problematic Qt APIs.

## Description

While Qt prides itself on APIs that are consistent and simple to use - there are pitfalls. Parts of an API might turn out to be dangerous in practice or they may yield sub-optimal performance. clazy is a static code analysis tool built on to off the llvm/clang compiler infrastructure. It will issues warnings for Qt specific issues. See https://github.com/KDE/clazy for details and a list of the kind of warnings reported by clazy.

## Environment

C++/Qt

## Platform

Either QtCreator >= 4.6, standalone or upstream clang (note that xcode-clang and android-clang do not work)

## Implementation effort

Very minimal (Qt Creator), small when already using upstream clang, potentially high if a project needs to be ported to upstream llvm/clang first.

## Applicability

All projects using C++ Qt.

## Caveats

* Clazy implements several warnings levels. The higher levels can produce false positives.

## See also

* [Continuous Integration keeps your project healthy](https://toolbox.basyskom.com/3)

## Implementation hints

Usage via Qt Creator is probably the easiest way to get started. Integration into a CI system is probably best done via the standalone version of clazy in combination with a compilation database.
