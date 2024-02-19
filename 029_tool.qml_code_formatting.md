# Tool QML code formatting

## Goals
Keep code readable/consistent

## Description
Apply an (semi)automated mechanism to keep your QML code readable/consistent. This tool is about formatting, not structure of your code. Qt provides the [`qmlfomat`](https://doc.qt.io/qt-6/qtquick-tools-and-utilities.html#qmlformat) tool as a cli-utility or directly integrated in QtCreator to streamline QML development.

## Environment
QML

## Platform
All

## Implementation effort
Minimal

## Applicability
Applicable to code that has just been written by yourself. Don't blindly reformat code! Reformatting code without careful consideration makes tracking changes more difficult, and disrupt the work of others who may be using the same code.

## Caveats
\-

## Limitations
 - QtCreators `Tools > QML/JS > Reformat file` doesn't allow to reformat only selected text

## See also

- [C/C++ code formatting](https://toobox.basyskom.com/26)

## Implementation hints
At project start decide which code formatting to use. We ask the customer if there are in-house styles which should be implemented. If the customer doesn't care, we will use the official Qt QML code style.

Use IDE to apply code formatting while writing (in QtCreator: `Options > Qt Quick > Code Style`).

If a custom format shall be used, put a custom .qmlformat.ini in your repository, so every developer has the same settings applied. The default settings can be exported using `qmlformat --write-defaults` to start from there.

To reformat whole QML files hit `Tools > QML/JS > Reformat file`, which isn't recommended because it can potentially lead to commits containing changes that are unrelated to the actual change.