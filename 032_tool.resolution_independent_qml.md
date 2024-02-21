# Resolution indepedent QML

## Goals
Creating UI code that can run on various display sizes with different resolutions

## Description
When creating a QtQuick application it is probable that its target device and its display will be completely different from the development machine.
As a result, it is important to create the UI code in a way, that the UI is able to scale well across different display hardware.

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

- which types of devices need to be supported (example: smartwatch, mobile device, embedded device, desktop hardware, TV)
- which resolutions need to be supported
- which aspect ratios need to be supported
- will the application run in full screen or windowed mode?
- will the application run in portrait or landscape mode and can you switch between them during runtime?

General advice:

- implement the UI using anchor based layouts and by placing elements with positioner items like Row, Column, Grid, RowLayout, ColumnLayout, etc.
- consider implementing the UI using file selectors: this allows to switch the actual UI code based on specific selectors. As an example: the screen layout for the application running on a smartwatch might (or probably should) be completely different from an application running on a desktop PC
- it can be very beneficial to do element sizing and placement in QML by using some kind of unit format instead of pixels.
- Although generally inadvisable: if the UI code contains item placement with absolute coordinates and fixed widths and heights, the application can be scaled to other display resolutions by using the environment variables `QT_AUTO_SCREEN_SCALE_FACTOR` and `QT_SCALE_FACTOR`

For further information take a look into the Qt articles regarding the topic:

- https://doc.qt.io/qt-6/scalability.html
- https://doc.qt.io/qt-6/highdpi.html
- https://www.qt.io/blog/responsive-layouts-in-qt
