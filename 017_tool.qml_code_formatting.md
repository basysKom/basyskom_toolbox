# QML code formatting

## Goals

Keep code readable/consistent.

## Description

Apply an (semi)automated mechanism to keep your QML code readable/consistent. This tool is about formatting, not structure of your code.

## Environment

Qt/QML

## Platform

All

## Implementation effort

Minimal

## Applicability

Applicable to code that has just been written by yourself. Don't blindly reformat code! This is a big no-no.

## Caveats

TODO: Maybe we will change the content to use the `qmlformat`-tool

`Tools > QML/JS > Reformat` file doesn't allow to reformat only selected text

## See also

[QML coding conventions](https://toolbox.basyskom.com/16)

## Implementation hints

TODO: Maybe we will change the content to use the `qmlformat`-tool

At project start decide which code formatting to use. Ask the customer if there are in-house styles which should be implemented. If the customer doesn't care we will use the official Qt QML code style.

Use IDE to apply code formatting while writing (in QtCreator: Options > Qt Quick > Code Style).

To reformat whole QML files hit Tools > QML/JS > Reformat file, which isn't recommended because it can potentially lead to commits containing changes that are unrelated to the actual change.
