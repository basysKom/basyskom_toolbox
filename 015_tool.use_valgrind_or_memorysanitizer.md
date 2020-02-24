# Valgrind or the MemorySanitizer help to ship reliable software

## Goals

Do not rely on uninitialized memory.

## Description

C and C++ don't force you to initialize variables. Uninitialized variables introduce lingering bugs and hard to find random behavior. While modern compilers can warn for some of these issues, Valgrind and/or the MemorySanitizer can find additional ones. Note that both tools are, unlike the compiler, dynamic and rely on code execution and good code coverage. Consider to combine them with unit tests automatically run in a CI system for extra power.

## Environment

C and C++/Qt

## Platform

As a rule of thumb - Valgrind is available for most Unix-like platforms. See https://valgrind.org/info/platforms.html for details.

The MemorySanitizer is currently only available with clang.

## Implementation effort

If a program is already runnable on X86_64/Linux Valgrind can be employed very easily.
While quite powerful - the MemorySanitizer is much harder to deploy. Unlike for example the AddressSanitizer it can't be partially applied to a program.
Rule of thumb: try to use Valgrind first.

## Applicability

## Caveats

* While Valgrind is available for a lot of Unix-like platforms, but practical usage is typically limited by the raw CPU speed of the target. Use on ARM is often not practical.

## See also

* [Continuous Integration](https://toolbox.basyskom.com/3)
* [Unit tests](https://toolbox.basyskom.com/12)

## Implementation hints

* Valgrind can produce false positives especially for third party and system libraries. Valgrind supports to concept of a "suppression file" to selectively mute these. Put your project specific suppression files into version control with the rest of your project.
* Valgrind is also reporting on memory leaks and issues such as various forms of memory corruption.
