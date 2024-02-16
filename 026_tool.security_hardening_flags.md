# Security hardening flags

## Goals
Make use of exploit mitigations offered by your toolchain to increase the security of your software.

## Description
C and C++ are a dangerous choice for creating network facing software (or any software that is processing inputs provided by a potentially malicious third-party) as they don't enforce memory safety. Simple errors can lead to catastrophic results. Modern toolchains are offering so called mitigations. These do not prevent a problem to be triggered, but they (hopefully) prevent a problem from being exploited.

While the final system integration might be up to the customer, it is good practice to compile the software with the respective hardening flags enabled.

## Environment
C/C++

## Platform
All (???)

## Implementation effort
Minimal

## Applicability
Consider these for software that is network facing (or processing inputs controlled by a third-party)

## Caveats
Do not enable these flags late in the project as there might be side effects (at least not without talking to the customer).

## See also

## Implementation hints
GCC/Clang:

```
    -D_FORTIFY_SOURCE=1 (compile-time checks)
    -D_FORTIFY_SOURCE=2 -O1 (compile- and run-time checks but might fail on correct code; -O1 or higher strongly advised)
    -fstack-protector
    -Wformat -Wformat-security
    -pie -fPIE
    -Wl,-z,relro
    -Wl,-z,now
```

Visual Studio:

```
    ?? /RTC? /GS?, Control Flow Guard?
```