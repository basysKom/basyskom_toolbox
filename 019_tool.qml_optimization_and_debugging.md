# UI optimization and debugging hints

## Goals

Optimize and debug QML code for performance reasons

## Description

Some useful hints for debugging and optimizing UI (performance) issues

## Environment

QML

## Platform

Qt/QML

## Implementation effort

Minimal

## Applicability

Depends on what kind of issues are encountered:

- for issues regarding component compilation during runtime using the qtquickcompiler will reduce or solve some performance bottlenecks. Those come up in certain scenarios in which the system is under high CPU load.
- for rendering performance issues visualizing the scene graph to pinpoint clipping/batching might be a good approach. A close look should also be taken on shader usage.
- Observe general load of the system. If the system is under constant CPU load the UI performance will most likely never be optimal.

## Caveats

There are various hardware/software combinations that can lead to potential performance issues, especially on low powered hardware.

Running the software on the actual hardware is required.

## See also

\-

## Implementation hints

Explicitly enable QtQuick compiler by adding (for Qt < 5.11):

```
CONFIG += qtquickcompiler
```

Useful hints for visualizing the QtQuick scene graph can be found here http://doc.qt.io/qt-5/qtquick-visualcanvas-scenegraph-renderer.html

All available environment variables regarding the scene graph:
- `QSG_ANTIALIASING_METHOD`
- `QSG_DISTANCEFIELD_ANTIALIASING`
- `QSG_FIXED_ANIMATION_STEP`
- `QSG_RENDERER_BATCH_NODE_THRESHOLD`
- `QSG_RENDERER_BATCH_VERTEX_THRESHOLD`
- `QSG_RENDERER_BUFFER_STRATEGY`
- `QSG_RENDERER_DEBUG`
- `QSG_RENDER_LOOP`
- `QSG_SANITY_CHECK`
- `QSG_VISUALIZE`
