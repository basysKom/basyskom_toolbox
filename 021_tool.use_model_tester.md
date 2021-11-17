# Use QAbstractItemModelTester for custom models

## Goals

Detect/Avoid a certain set of errors in subclasses of QAbstractItemModel.

## Description

QAbstractItemModelTester can be used to detect common errors in the implementation of models based on QAbstractItemModel with very little effort and even before they appear in the form of a visible bug.

## Environment

Qt

## Platform

All

## Implementation effort

Very minimal

## Applicability

- When implementing new models
- As part of test suites
- In debug sessions

## Caveats

Citing the documentation: *While QAbstractItemModelTester is a valid help for development and testing of custom item models, it does not (and cannot) catch all possible problems in QAbstractItemModel subclasses. Notably, it will never perform meaningful destructive testing of a model, which must be therefore tested separately.*

## See also

\- 

## Implementation hints

`QAbstractItemModelTester` can be used in two ways:

- In unit tests
- Directly in the running application (introduces testlib-dependency). Should be disabled for release builds. At least `QAbstractItemModelTester::FailureReportingMode::Fatal` should not be used in release builds

Both ways are described in the [documentation](https://doc.qt.io/qt-5/qabstractitemmodeltester.html)
