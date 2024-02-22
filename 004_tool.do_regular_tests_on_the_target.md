# Regular testing on the target device

## Goals

Make sure the program developed works well on the intended target - while still benefitting from fast iterations on the desktop.

## Description

Qt as well as web-technologies makes it easy to develop embedded HMIs on the desktop. This enables quick iterations, high turnarounds and easy debugging. Do not fall into the trap of developing something that only works on the desktop, either because of performance reasons or because of features not available on the target. Make sure to regular test on the target device.

## Environment

All

## Platform

All

## Implementation effort

Minimal. You need to be able to do proper one-stop builds anyways.

## Applicability

All projects that are developed in a desktop environment while targeting a mobile or embedded device.

## Caveats

\-

## See also

- [Definition of done](https://toolbox.basyskom.com/21)
- [Continuous Integration](https://toolbox.basyskom.com/3)

## Implementation hints

- Make sure developers and testers have access to actual target hardware (or comparable evaluation boards)
- Make sure your CI system is creating regular target builds to guard against host dependencies creeping in.
- Consider to make "tested on the target" part of your definition of done.
