# Enable build time checks for your QML files

## Goals

Find QML issues already at build time.

## Description

QML is weakly typed - issues might only show up during runtime when a document is actually loaded. Qt is offering several ways to improve this situation. Use either qmllint or the Qt Quick compiler to catch syntax errors already during build time. Consider adding this to your CI system to make the most out of it.

## Environment

Qt/QML

## Platform

All

## Implementation effort

Low

## Applicability

All QML projects.

## Caveats

Note that both, qmllint and the Qt Quick Compiler can only catch things that do not rely on specific execution context such as syntax errors.

## See also

[Continuous Integration keeps your project healthy](https://toolbox.basyskom.com/3)

## Implementation hints

qmllint has been added with Qt5.4. The Qt Quick compiler has been available in upstream Qt since Qt5.11.

Ideally these tools are run as part of the build process.

Given that you are already using QRCs for your QML documents you can just add `CONFIG+=qtquickcompiler` to your project.

For CMake and more details see:  https://doc.qt.io/qt-5/qtquick-deployment.html#ahead-of-time-compilation
