# The AddressSanitizer helps you to root out memory issues

## Goals

Ship software that is free from leaks and lingering memory corruption bugs.

## Description

In C and C++ it is easy to introduce issues such as memory leaks, bounds violations or use-after-frees. Both languages do not enforce memory safety, which means that programming errors can damage the internal memory management structures of a process leading to hard-to-find bugs and security issues. These issues might go undetected during development and test. The AddressSanitizer built into GCC, Clang and recently Visual Studio helps you to catch these early on by instrumenting your code with strict checks.

## Environment

C++/Qt

## Platform

The best supported platform is probably X86_64/Linux with either GCC or clang but other platforms/toolchain combinations can also work.

- [Supported platforms for clang](https://clang.llvm.org/docs/AddressSanitizerhtml#supported-platforms)

## Implementation effort

Minimal, if your software (or a sub-set like for example the unit tests) already run on X86_64/Linux.

## Applicability

All projects using C and C++.

## Caveats

- While the AddressSanitizer is significantly faster than Valgrind it still slows down program execution.
- The AddressSanitizer introduces a significant memory overhead.

## See also

- [Use Valgrind or MemorySanitizer](https://toolbox.basyskom.com/15)

## Implementation hints

- Consider to just enable the AddressSanitizer for all debug builds.
- Not all code in a program needs to be compiled with the AddressSanitizer, partial application is possible.
