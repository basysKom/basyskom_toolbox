# Tool Logging with Categorized Logging

## Goals
Flexible, unified logging for both C++ and QML

## Description
Logging with qDebug/qWarning/qCritical isn't flexibel enough. Most of the time a developer wants to get logs only from an area in the code that's causing a problem.

Setting up categorized logging in a way that logs are generated on a class/functionality/module level will allow to filter for specific messages, which makes finding issues or even understanding the application data flow or structure much easier. Especially in large code bases.

## Environment
Qt/QML

## Platform
C++/QML (Qt >= 5.2, Qt >= 5.8 for QML); `QT_LOGGING_RULES` since 5.3)

## Implementation effort
Minimal to Medium depending on how the categories are structured

## Applicability
Figure out if there is an established logging framework to be used within a project. A lot of customers us their own logging.

New projects: qDebug() and friends can be disabled (so it does not compile anymore) with `DEFINES += QT_NO_DEBUG_STREAM`. This is probably not feasible for existing projects as it can generate a lot of work. Consider that `qDebug()` can also serve a for printf-debugging and might still be wanted. To work around this issue, consider only enabling it in Release builds that are built during pull-requests in your CI.

## Caveats
Additional effort during printf-debugging; you might want to keep `qDebug()` for debugging purposes during development.

## See also
* [QML best practices](https://toolbox.basyskom.com/8)
* [Continuous Integration keeps your project healthy](https://toolbox.basyskom.com/3)

## Implementation hints
Make use of Qt's logging classes

```
// in a header (.h)
Q_DECLARE_LOGGING_CATEGORY(driverUsb)
 
// in one source file (.cpp)
Q_LOGGING_CATEGORY(driverUsb, "driver.usb")
 
// the actual output line will only be shown if driverUsb category is enabled
qCDebug(driverUsb) << "Some debug message";
```


QML
```
import QtQml
 
LoggingCategory {
    id: category
    name: "my.category.name"
}
 
console.log(category, "log message")
```
