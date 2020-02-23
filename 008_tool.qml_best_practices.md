# QML Best Practices - DOs and DONTs

## Goals

Write future-proof QML code that is modular, efficient and maintainable.

## Description

QML can help to create modern UIs across different platforms with ease. But as we all know: with great power comes great responsibility!
Like with other languages there are pitfalls that might increase the implementation effort, degrade performance or reduce maintainability and code quality.

There are some DO and DONTS that help to avoid them.

## Environment

Qt/QML

## Platform

All

## Implementation effort

There are many tips that can be implemented straight-away with ease,
others may require a deeper understanding of QML and the application structure.
But it is always worth to cling to the best practices as it saves you time and trouble.

## Applicability

All projects using C++ and QML Qt.

## Caveats

\-

## See also

\-

## Implementation hints

There are several rules of thumb that can improve the overall architecture and maintenance:

* An element should always be self contained:
  * It should never reference ids that are not instantiated by itself (e.g. root.parent)
  * It should define an API of properties and functions to set dependencies from the outside and access its data
  * Keep the API as small as possible and as large as necessary
  * This allows for modular re-use and easy unit-testing
* Use context properties sparingly
* Use "root" as root id for each element
  * QML will climb up the parent tree and look for the id's if they're not found locally. It might find the same id in a whole different element!
  * Always giving the local root element an id and access its properties via this id avoids unintended cross-element references
  * This eases refactoring and maintainability
* Stick to declarative coding and keep imperative JavaScript snippets minimal.
  * This is OK for prototyping, but should be avoided in production code
  * Avoid using JavaScript in hot spots, prefer C++ functions.
* Keep the UI simple
  * Do not code business logic in QML
  * Avoid complex expressions
  * Enforce encapsulation of UI and business logic
* Create a component framework to create reusable elements
  * Define basic elements with basic behavior. Keep them self contained and encapsulated
  * Nest and use the basic elements inside more complex elements according to their role
  * This allows for easier code extensions or gradual refactoring.
* Use the Style Singleton approach for [QML Styling](https://wiki.qt.io/Qml_Styling)
  * Avoid creating necessary clones of identical objects
* Stick to [QML Coding Guidelines](https://doc.qt.io/qt-5/qml-codingconventions.html)
  * This makes it easy to maintain QML code and read QML code written by others
* Use the Loader element to load bigger parts of the application on demand. [QML Loader](https://doc.qt.io/qt-5/qml-qtquick-loader.html)
* Use QObject and its property system to build C++-interfaces to databases, devices or backend libraries.
  * Once again: As small as possible and as large as necessary
  * Do not expose QObjects without a parent to QML, as the JavaScript garbage collector might clean them up
* Keep the C++ implementation agnostic of the internal QML object tree composition and vice versa
* Use Qt Creator for QML Profiler integration. [QML Profiler](https://doc.qt.io/qtcreator/creator-qml-performance-monitor.html)
