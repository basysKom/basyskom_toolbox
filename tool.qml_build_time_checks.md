# Enable build time checks for your QML files

## Goals

Find QML issues already at build time.

## Description

QML is weakly typed - issues might only show up during runtime when a document is actually loaded. Qt is offering several ways to improve this situation. Use either qmllint or the Qt Quick compiler to catch errors already during build time. Consider adding this to your CI system to make the most out of it.

## Environment

Qt/QML

## Platform

All

## Implementation effort

FIXME

## Applicability

## Caveats

Note that both can only catch things that do not rely on specific execution context such as syntax errors.

## See also

[Continuous Integration](https://toolbox.basyskom.com/FIXME "CI")

## Implementation hints

qmllint has been added with Qt5.4. The Qt Quick compiler has been available in upstream Qt since Qt5.FIXME.

FIXME: post build step in qmake
