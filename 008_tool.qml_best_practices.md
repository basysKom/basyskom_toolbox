# QML Best Practices - DOs and DONTs

## Goals

Develop good QML code. Write future-proof code that is modular, efficient and maintainable.

## Description

QML can help to create modern UIs across different platforms with ease. 
However like with other languages there are pitfalls that might increase the implementation effort, degrade performance or reduce maintainability and code quality.
There are some DO and DONTS that help to avoid this scenario.

## Environment

C++/Qt

## Platform

All Platforms supported by Qt Quick 2 and OpenGL (ES) 2.0 

## Implementation effort

There are many tips that can be implemented straight-away with ease.
Others require a deeper understanding of QML and the application structure. 

## Applicability

All projects using C++ and QML Qt.

## Caveats

* Some C++ classes or QML elements are provided for migrational purposes and therefore deliver mediocre performance:

- C++: QGraphicsProxyWidget, QQuickWidget, QQuickPaintedItem
- QML: QML Canvas, 

## See also

* [QML Best Practices](https://toolbox.basyskom.com/8)

## Implementation hints

There are several rules of thumb that can improve the overall architecture and maintenance:

- An element should always be selfcontained. It should not reference ids that are not instantiated by itself (e.g. root.parent). This allows for modular re-use and easy unit-testing.
- Therefore use context properties sparingly.
- To avoid cross-element references and to ease refactoring use "root" as a root id for each element.
- Stick to declarative coding and keep imperative Javascript snippets minimal.
- Nest QML elements inside a file according to their role - this allows for easier code extensions or gradual refactoring.
- Use the Style Singleton approach for [QML Styling](https://wiki.qt.io/Qml_Styling)
- Stick to [QML Coding Guidelines](https://doc.qt.io/qt-5/qml-codingconventions.html) 
- Use the Loader element to load bigger parts of the application on demand. [QML Loader](https://doc.qt.io/qt-5/qml-qtquick-loader.html)
- Use QObject and its property system to build C++-interfaces to databases, devices or backend libraries.
- Keep the C++ implementation agnostic of the internal QML object tree composition
- The environment variable QSG_VISUALIZE can be helpful to identify performance issues. [Scene Graph Optimizations](https://doc.qt.io/qt-5/qtquick-visualcanvas-scenegraph-renderer.html)
- Do not disable the render thread accidently.
- Use Qt Creator for QML Profiler integration. [QML Profiler](https://doc.qt.io/qtcreator/creator-qml-performance-monitor.html)
- Don't mix Qt/QML patterns with alien patterns (e.g. foreign MVC patterns)
