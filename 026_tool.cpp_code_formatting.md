# Apply C/C++ code formatting

## Goals
Keep code readable by applying consistent code styles

## Description
To ensure readable code it's important to apply consistent coding style guidelines. Use tools to help your team to stay consistent and not waste time while coding and during reviews to fix tedious formatting mistakes.

## Environment
C/C++

## Platform
All

## Implementation effort
Minimal

## Applicability
Applicable to code that has just been written by yourself. Reformatting code without careful consideration makes tracking changes more difficult, and disrupt the work of others who may be using the same code.

Generally, "format-on-save" should only be turned on if all members of project adhere to coding style. Code style adaptions (e.g. in an existing code base) should ONLY be done on a commit-basis, "format-on-save" should not be used in these cases. If you want to adapt the code base or single files to a new or changed format use style-change-only-commits without changing any logic. This will make tracking changes in your version control system easier.

Additional considerations: 
- Put a (custom) clang-format file into your repository, so developers are using the same configuration. 
- Adapt your CI-checks to involve a formatting check in order to catch formatting errors automatically.

## Caveats
Formatting tools are do not always format code as you would like. Especially line breaks are common issues. You might use `// clang-format off` and `// clang-format on` comments around a line or section to disable clang-format sporadically to manually format the code.

## See also

- [QML code formatting](https://toolbox.basyskom.com/29)
- [Continuous Integration keeps your project healthy](https://toolbox.basyskom.com/3)

## Implementation hints
At project start decide which coding style to use. Ask the customer if there are in-house styles which should be implemented. If the customer doesn't care we will use the official [Qt C++ code style](https://wiki.qt.io/Qt_Coding_Style).

Use IDE to apply coding styles while writing (in QtCreator: `Options > C++ > Code Style`).

Use IDE to 'convert' whole files

- QtCreator: enable 'Beautifier' plugin and configure it appropriately. Requires `clang-format`, `astyle` or `uncrustify` to be installed in the system
- Clang format
  - Linux: `apt install clang-format`
  - Windows: install from http://llvm.org/builds/
- Artistic Style
  - Linux: `apt install astyle`
  - Windows: install from https://sourceforge.net/projects/astyle/files/
- Uncrustify
  - Linux: `apt install uncrustify`
  - Windows: install from https://sourceforge.net/projects/uncrustify/files/
