# Avoid deprecated Qt

## Goals

Avoid deprecated Qt

## Description

A defining quality of Qt is that it provides long-term API stability within a major release (e.g. Qt 5) which historically translates to
roughly 7-8 years. To communicate up-front which APIs (or parts of an
API) might be affected by a change in the next major release, deprecation warnings are added to the headers of Qt as a continuous process. Make sure to enable these deprecation warnings to stay up-to-date how your application might be affected by Qt API changes and to ease the transition to new Qt versions over time.

## Environment

Qt/C++

## Platform

All

## Implementation effort

Very minimal

## Applicability

New projects, new modules within existing projects. As a preparation for a porting effort.

## Caveats

Might conflict with -Werror.

## See also

* [Treat warnings as error](https://toolbox.basyskom.com/11)

## Implementation hints

Variant1: my.pro

```shell
QMAKE_CXXFLAGS += -Wdeprecated
DEFINES += QT_DEPRECATED_WARNINGS
```

Generates one warning for each use of a Qt method marked as deprecated.
Very coarse grained. No specific Qt version can be selected.

Variant2: my.pro

```shell
DEFINES += QT_DISABLE_DEPRECATED_BEFORE=0x050200
```

Removes everything what is deprecated since Qt 5.2 from the headers.

