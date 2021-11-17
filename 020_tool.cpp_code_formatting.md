# Apply appropriate code styles

## Goals

Keep code readable by applying consistent code styles.

## Description

To ensure readable code it's important to apply consistent coding style guidelines.

## Environment

C/C++

## Platform

All

## Implementation effort

Minimal

## Applicability

Applicable to code that has just been written by yourself. Don't blindly reformat code! This is a big no-no.

"Format-on-save" is problematic. It can work on green field projects where the developer is working alone (or all people involved use the some format-configuration and have "format-on-safe" enabled).

Generally "format-on-save" should not be turned on, if the IDE allows to enable it. Code style adaptions should be done on a commit-basis, with the exception of style-change-only-commits that can reformat whole files.

Consider putting the custom clang-format file under version control so developers are using the same configuration.

## Caveats

## See also

## Implementation hints

At project start decide which coding style to use. Ask the customer if there are in-house styles which should be implemented. If the customer doesn't care we will use the official Qt C++ code style.

Use IDE to apply coding styles while writing (in QtCreator: `Options > C++ > Code Style`).

Use IDE to 'convert' whole files

- QtCreator: enable 'Beautifier' plugin and configure appropriately, requires clang-format, astyle or uncrustify to be installed in the system
- Clang format
    - Linux: apt-get install clang-format
    - Windows: install from http://llvm.org/builds/
- Artistic Style
    - Linux: apt-get install astyle
    - Windows: install from https://sourceforge.net/projects/astyle/files/
- Uncrustify
    - Linux: apt-get install uncrustify
    - Windows: install from https://sourceforge.net/projects/uncrustify/files/

Qt C++ coding style rules: https://wiki.qt.io/Qt_Coding_Style

A clang-format file implementing the qt style can be either obtained from http://code.qt.io/cgit/qt/qt5.git/tree/_clang-format (looks outdated) or taken from an installed kit if the source code was installed as well. For example from Qt/5.15.2/Src/_clang-format. In addition, this can of course also be used as a template augmented with changes agreed in the project (e.g. the indentation depth).



