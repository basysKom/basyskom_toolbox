# Tool UI asset handling

## Goals
Have assets delivered that are high quality and easy to use

## Description
High quality assets are easy to work with, which prevents unnecessary work on the development side (making the project cheaper).

Provide assets in an appropriate format and size. Using bitmap-formats generally improves performance compared to vector images. See https://wiki.qt.io/Performance_tip_Images for additional tip on performace improvements using image assets in qml.


**Metadata:**
The safest approach to work with assets is still to use 'clean' filenames, i.e. ascii chars only, no spaces, no umlauts. This improves portability and makes building, CI and packaging issues less likely.

Use a common naming convention to easily find assets as a developer. E.g.:
```
<component>_<state>.png → button_pressed.png
```

## Environment
Qt/QML

## Platform
All

## Implementation effort
Minimal

## Applicability
HMI focused projects where assets are provided by the customer (or through another service company).

## Caveats
Assets might be provided by a third party which is under no obligation to follow the guidelines.

## See also
\-

## Implementation hints
Set up a streamlined process how assets are provided to ease development and maintenance of the application. Communicate naming conventions, quality and size requirements clearly to the asset provider.

If Qt's resource system is used, consider splitting UI resources (QML files, images/fonts/videos) into separate qrc files. This allows to keep compilation times low, because rcc is invoked for every change to a file that's contained in the resources. You don't want to recompile every resource because one QML file was changes. For large resources (>=10MB) use

```
CONFIG += resources_big
```

to treat these resources seperately.

Compression level of resources can be adjusted by passing appropriate settings to `QMAKE_RESOURCE_FLAGS` (see http://doc.qt.io/qt-6/rcc.html).

Starting with Qt6, you can directly integrate resource management in your CMakeLists files.

```cmake
qt_add_resources(target "resource_name"
    BASE <base_directory> # this will be skipped when referencing the resource from code
    FILES
        <base_directory>/<filename>
)
```

which will take care of the asset management for you. Split resources, by adding multiple sections like the one shown to your CMakeLists. For a more detailed overview of additional parameters, such as `BIG_RESOURCES`, see https://doc.qt.io/qt-6/qt-add-resources.html.