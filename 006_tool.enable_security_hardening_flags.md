# Make use of exploit mitigations

## Goals

Make use of exploit mitigations offered by your toolchain to increase the security of your software.

## Description

C and C++ are a dangerous choice for creating network facing software (or software that is processing inputs provided by third party) as they don't enforce memory safety. Simple but hard to catch programming errors can enable an attacker to take control of your application by injecting their own code. Modern toolchains are offering code generation techniques that do not prevent the problem in the first place, but they (hopefully) prevent it from being exploited.

While the final system integration might be up to the customer, it is good practice to compile the software with the respective hardening flags enabled.

## Environment

C and C++

## Platform

All, but the number and quality of mitigations offered will differ between toolchains, OS versions and CPU architectures.

## Implementation effort

Low

## Applicability

All software which deals with untrusty third party inputs.

## Caveats

* Try to enable these flags early on as there might be side effects which are easier to track down outside of a release window...
* Mitigations make it harder (sometimes a lot) to exploit a given bug, but they are no 100% protection. Also make sure that OS-level mitigations are also enabled.
* Some mitigation have a performance impact.

## See also

\-

## Implementation hints

GCC/Clang:

```
    -D_FORTIFY_SOURCE=1 (compile-time checks)
    -D_FORTIFY_SOURCE=2 -O1 (compile- and run-time checks but might fail on correct code; -O1 or higher strongly advised)
    -Wl,-z,relro
    -Wl,-z,now
    -fstack-protector-strong
    -pie -fPIE
    -Wformat­ -Wformat­-security
```

Visual Studio:

```
    /GS
    /guard:cf
```

These options only provide a baseline, please have a look at the toolchain documentation for details and more mitigations.

For Embedded-Linux scenarios it might be better to globally enable these flags globally during firmware generation.
