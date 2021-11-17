# Useful Qt-specific defines

## Goals

Use Qt-APIs in the best possible ways. Avoid certain murky areas of the API.

## Description

The Qt API offers a few switches that an application can use to select API-variants at compile time. These API-variants emphasize correctness and/or performance.

## Environment

Qt

## Platform

All

## Implementation effort

Very minimal

## Applicability

New projects: just use it!

Existing projects: Check your build system if they are used. If not, try them and see how big the effort is to make the code compile again.

## Caveats

Existing project where these defines had been disabled for a long time can generate hundreds of compiler errors.

## See also

\- 

## Implementation hints

Add one or more of the defines listed below the table to your build system.

QMake (.pro file):

    DEFINES *= QT_STRICT_ITERATORS

CMake (CMakeLists.txt):

    add_definitions(-DQT_STRICT_ITERATORS)

### Details

#### QT_STRICT_ITERATORS (performance++)

Disables automatic conversion from `iterator` to `const_iterator`.

Here is some code that only wants to read from a container.
```
QString str = ...;
for (QString::const_iterator iter = str.begin(), end = str.end(); iter != end; ++iter) // detaches
```

While iter is of type `QString::const_iterator`, `str.begin()` returns its mutable sibling `QString::iterator`. `iter` is thus converted to the returned type and `str` detaches (creates a copy of the container). To avoid these unnecessary copies, let the compiler bail out on implicit conversions from non-const to const iterators.

Above code can be written correctly as:
```
QString str = ...;
for (QString::const_iterator iter = str.constBegin(), end = str.constEnd(); iter != end; ++iter) // doesn't detach
```
Now `str.constBegin()` is used which returns a `QString::const_iterator` and no conversion takes place.


#### QT_NO_CAST_FROM_ASCII (performance++)
Disables automatic conversions from 8-bit strings `(`char *`)` to unicode QStrings.

In many cases you would use string literals in your code:
```
QApplication::setApplicationName("Embedded World Demo - QML Client"); // API: void setApplicationName(const QString &)
```

In this case, the string literal (UTF-8) will be converted to a `QString` (UTF-16) and the data copied into the `QStringData` representation inside the `QString`.

So to avoid these steps, there is the `QStringLiteral` macro. It creates the `QStringData` object at compile time (there are cases where it is not, but let's not burden our brains with too borderly cases. For all the gory details, see https://woboq.com/blog/qstringliteral.html) so at runtime the created `QString` only has to point to that location.

```
QApplication::setApplicationName(QStringLiteral("Embedded World Demo - QML Client")); // copying and conversion at compile time
```

However, not everyone needs UTF-8/16 strings to do their work. Many methods have QLatin1String overloads, which is just a thin wrapper around `char *`. If so, use it instead of the QString one.

```
if (hostAddressString.contains(QLatin1String("192.168.")))
```

Other candidates for this are (not a complete list):
- `append`
- `endsWith`
- `indexOf`
- `replace`
- `operators like +, +=, <, >=, etc.`


#### QT_NO_CAST_TO_ASCII (performance++)

Disables automatic conversion from unicode `QString` to 8-bit strings (`char *`).

#### QT_NO_CAST_FROM_BYTEARRAY (performance++)

Disables automatic conversions from QByteArray to const `char *` or const void *

#### QT_NO_URL_CAST_FROM_STRING (performance++)

Disables automatic conversions from `QString` (or `char *`) to `QUrl`.

In any code that uses `QUrl`, it can help avoid missing `QUrl::resolved()` calls, and other misuses of QString to `QUrl` conversions.


#### QT_USE_QSTRINGBUILDER (performance++)


The '+' concatenator for `QString` and friends will automatically be performed as the more efficient `QStringBuilder` '%' everywhere.


This define deprecates `QT_USE_FAST_CONCATENATION` and `QT_USE_FAST_OPERATOR_PLUS`.


#### QT_NO_NARROWING_CONVERSIONS_IN_CONNECT (correctness++)

Disables calling a slot with e.g. int parameter with a signal with double parameter.

The new-style, pointer to member function-based connect will check at compile time if the signal’s signature is compatible with the slot’s one. Thus you cannot connect a signal with a `QString` parameter to a slot with an int parameter. There is no implicit conversion between those two. There is however between `double` and `int`.
```
connect(s, &Sender::signalWithDouble,
        r, &Receiver::slotWithInt);    // compiles fine and at run time cuts off the decimal part of the double value (narrowing conversion)
```

This is likely not what you were planning to do. So add this define to your build process to make the above snippet fail at compile time.