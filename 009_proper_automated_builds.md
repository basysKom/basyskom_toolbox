# Proper automated builds

## Goals

Be able to reliably create a new build of your project.

## Description

Builds that take a lot of manual work are highly error-prone. Make sure to have a good foundation for your project by implementing automated project builds. Having automatic - one-stop - builds is a baseline effort to enable other, high-value tools such as continuous integration, unit tests or just easy on-boarding of new project members.

It should be possible to check out a project from VCS and create a build with just 2-3 commands.

A strongly related topic is how to handle external dependencies and build environments.

## Environment

All

## Platform

All

## Implementation effort

Minimal for new projects. Potentially substantial for large existing projects.

## Applicability

All

## Caveats

- Do not rely on the project files of IDEs for your builds. These are hard to automate, bad for version control and force all team members into the same IDE. Also there is a tendency of projects to outlive their initial IDE, creating a porting effort down the line.

## See also

\-

## Implementation hints

- Consider to use a package manager like conan.io or vpkg to manage dependencies.
