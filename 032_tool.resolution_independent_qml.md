# Resolution indepedent QML

## Goals
Creating UI code, that can run on various display sizes with different resolutions

## Description
When creating a QtQuick application it is probable that its target device and its display will be completely different from the development machine.
As a result, it is important to create the UI code in a way, that it is able to scale well across different display hardware.

## Environment
QML

## Platform
All

## Implementation effort
Medium

## Applicability
Always

## Caveats
- Resolution independence should be a goal from the start of the implementation phase
- Converting a fixed resolution application to allow scaling can be costly

## See also

- [QML best practices](https://toolbox.basyskom.com/8)

## Implementation hints
Implementation is dependent on what kind of devices the application needs to run on. Some of the following questions can be used as guidance:

- which types of devices need to be supported (example: smartwatch, mobile device, embedded device, desktop hardware, tv)
- which resolutions need to be supported
- which aspect ratios need to be supported

General advice:

- Although generally inadvisable: if the UI code contains item placement with absolute coordinates and fixed widths and heights, the application can be scaled to other display resolutions by using the environment variables `QT_AUTO_SCREEN_SCALE_FACTOR` and `QT_SCALE_FACTOR`
implement the UI using anchor based layouts and by placing elements with Positioner items like Row, Column, Grid, RowLayout, ColumnLayout, etc.
- consider implementing the UI using file selectors: this allows to switch the actual UI code based on specific selectors. As an example: the screen layout for the application running on a smartwatch might be completely different from an application running on a desktop PC
- it can be very beneficial to do element sizing and placement in QML by using some kind of unit format instead of pixels.

See:

- https://doc.qt.io/qt-5/highdpi.html
- https://doc.qt.io/qt-5/scalability.html
