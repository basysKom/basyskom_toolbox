# Tool i18n: Make your software international

## Goals
Have translations delivered that are easy to integrate into the system to make your system speak the language of your customers. Build software that adapts to the country, language and timezone of the customers, without changing the code.

## Description
Since translations are often provided by a third party, it's important to consider the requirements of the project and have appropriate translation files delivered that are easy to integrate with Qt's translation system.

## Environment
Qt/QML

## Platform
All

## Implementation effort
Minimal/Medium (depending on how complex translations are handled)

## Applicability
Applicable whenever Qt is used as the UI framework

## Caveats
Clients might not want to use Qt's translation system and use a third party provider whose format is not compatible with Qt.

Some projects require splitting translations over multiple files due to branding or other requirements. Those cases require a more complex handling of translation files being loaded by QTranslator.

## See also
\-

## Implementation hints
Qt provides a workflow using its .ts file format and Qt Linguist as a tool to specify, adapt and deploy translations.

Decide which translation function to use, depending on the use case and project size:

- by simple text → `qsTr()` (QML) / `QObject::tr()` (C++)
- by text id → `qsTrId()` (QML)
- by text and context → `qsTranslate()` (QML) / `QCoreApplication::translate()` (C++)

Update translation files using `lupdate`, either via command line or directly from QtCreator: `Tools > External > Linguist > Update Translations` to update translation files (.ts) in your repository. These should be tracked by the version control system.

Use [Qt Linguist](https://doc.qt.io/qt-5/qtlinguist-index.html) to provide translations for the user strings of your application.

Build your translations using `lrelease`, either via command line or directly from QtCreator:
`Tools > External > Linguist > Release Translations`. This will generate .qm files and should not be checked into the version control system but need to be deployed with your application.