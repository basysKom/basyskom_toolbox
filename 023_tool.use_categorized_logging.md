# Categorized Logging

## Goals

Flexible, unified logging for both C++ and QML.

## Description

Logging with `qDebug`/`qWarning`/`qCritical` isn't flexibel enough. Most of the time a developer wants to get logs only from an area in the code that's causing a problem.

Setting up categorized logging in a way that logs are generated on a class/functionality/module level will allow to filter for specific messages, which makes finding issues or even understanding the application data flow or structure much easier, especially for large code bases.

## Environment

Qt/QML

## Platform

C++/QML (Qt >= 5.2, Qt >= 5.8 for QML); `QT_LOGGING_RULES` since 5.3)

## Implementation effort

Minimal to medium depending on how the categories are structured.

## Applicability

Figure out if there is an established logging framework to be used within a project. A lot of customers use their own (bad!) logging.

New projects: `qDebug()` and friends can be disabled (does not compile anymore) with `DEFINES += QT_NO_DEBUG_STREAM`. This is probably not feasible for existing projects as it can generate a lot of work. `qDebug()` can also serve a different purpose (printf-debugging) and might still be wanted.

## Caveats

\-

## See also

\-

## Implementation hints

Make use of Qt's logging classes

```cpp
// in a header
Q_DECLARE_LOGGING_CATEGORY(driverUsb)
 
// in one source file
Q_LOGGING_CATEGORY(driverUsb, "driver.usb")
 
// the actual output line will only be shown if driverUsb category is enabled
qCDebug(driverUsb) << "Some debug message";
```


```qml
import QtQml 2.11
 
LoggingCategory {
    id: category
    name: "my.category.name"
}
 
console.log(category, "log message")
```
