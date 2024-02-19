# Creating a simulation environment

## Goals
Provide a way to run the application code inside a simulation environment, which provides the necessary backend functionality, to allow visualizing every UI state

## Description
In cases where a complex HMI has to be implemented and the system architecture is too complex to be run on each development PC, a good approach is to create a backend simulator. 
The simulator can provide an environment in which the QML code can be executed. By mocking every functionality that the backend provides, every state of the UI can be visualized, before the whole system is fully developed. 

This actually allows the UI development to start visualizing and iterating before the backend is fully developed or accessible to the developers. Additionally, it enables testing the HMI extensively and might even result in valuable feedback for the design team early on.

## Environment
C++/QML

## Platform
All

## Implementation effort
Medium to High

## Applicability
Basically to every QtQuick application

## Caveats
- Implementation of a simulator should be considered at project start, since it implies a big overhead
- Stubbing or mocking some of the backend functionality can become too complex

## See also
\-

## Implementation hints
- Backend implemented as QML plugin, providing a unified interface to QML
- Depending on backend implementation either
  - Provide mock classes behind the interface, that can interact with the UI
  - Hook up to e.g. DBus interfaces with adapters, that can be controlled from the UI