# basysKom Toolbox

## Goals

- Improve the quality of the software we create through technical/organisational measures
- Good defaults for our projects
- Conscious decisions to make use of certain techniques at the start of the project (when there is still time)
- Knowledge transfer within the basysKom team and with our customers
- Provide a tools teams, developers and project managers can pick from

## Non-goals
- The goal is **NOT** to construct a heavy-weight process to be applied to all projects in a one-size-fits-all manner.

## What is a tool?
In this context, a tool is a small guide for achieving a particular **goal**. It gives hints on how to **implement** a tool and on the potential **effort** to do so. In which situation can a tool be **usefully applied**? It outlines **caveats** and **limitations**. The idea is loosely inspired by the classic book "Design Patterns". 

A tool is not set in stone. We expect feedback from users of a tool about it's usefulness, effort, caveats and limitations. Please post issues about a specific tool directly on github.

An important piece of information for a given tool is the **applicability**. A particular tool might be very easy to implement in a greenfield project, but not in a legacy code base. Another tool might make perfect sense for developing a large application, but not for a three-week prototype.


## Usage on Github
You can create badges in the readme of your projects to list tools or principles you used during develepment like this:

[![Story](https://img.shields.io/badge/Story-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F20)](https://toolbox.basyskom.com/20)
[![Benefit From Peer Reviews](https://img.shields.io/badge/Benefit%20From%20Peer%20Reviews-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F14)](https://toolbox.basyskom.com/14) 


### List of Badges

| Title                                          | Badge |
|------------------------------------------------|-------|
| Tool: Avoid Deprecated Qt                      | [![Avoid Deprecated Qt](https://img.shields.io/badge/Avoid%20Deprecated%20Qt-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F1)](https://toolbox.basyskom.com/1) |
| Tool: CD Makes Your Work Visible               | [![CD Makes Your Work Visible](https://img.shields.io/badge/CD%20Makes%20Your%20Work%20Visible-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F2)](https://toolbox.basyskom.com/2) |
| Tool: CI Keeps Your Project Healthy            | [![CI Keeps Your Project Healthy](https://img.shields.io/badge/CI%20Keeps%20Your%20Project%20Healthy-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F3)](https://toolbox.basyskom.com/3) |
| Tool: Do Regular Tests on the Target           | [![Do Regular Tests on the Target](https://img.shields.io/badge/Do%20Regular%20Tests%20on%20the%20Target-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F4)](https://toolbox.basyskom.com/4) |
| Tool: QML Build Time Checks                    | [![QML Build Time Checks](https://img.shields.io/badge/QML%20Build%20Time%20Checks-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F5)](https://toolbox.basyskom.com/5) |
| Tool: Enable Security Hardening Flags          | [![Enable Security Hardening Flags](https://img.shields.io/badge/Enable%20Security%20Hardening%20Flags-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F6)](https://toolbox.basyskom.com/6) |
| Tool: Make Good Use of Compiler Warnings       | [![Make Good Use of Compiler Warnings](https://img.shields.io/badge/Make%20Good%20Use%20of%20Compiler%20Warnings-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F7)](https://toolbox.basyskom.com/7) |
| Tool: QML Best Practices                       | [![QML Best Practices](https://img.shields.io/badge/QML%20Best%20Practices-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F8)](https://toolbox.basyskom.com/8) |
| Proper Automated Builds                        | [![Proper Automated Builds](https://img.shields.io/badge/Proper%20Automated%20Builds-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F9)](https://toolbox.basyskom.com/9) |
| Tool: Use the AddressSanitizer                 | [![Use the AddressSanitizer](https://img.shields.io/badge/Use%20the%20AddressSanitizer-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F10)](https://toolbox.basyskom.com/10) |
| Tool: Compiler Warnings as Error               | [![Compiler Warnings as Error](https://img.shields.io/badge/Compiler%20Warnings%20as%20Error-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F11)](https://toolbox.basyskom.com/11) |
| Tool: Unit Tests                               | [![Unit Tests](https://img.shields.io/badge/Unit%20Tests-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F12)](https://toolbox.basyskom.com/12) |
| Tool: Clazy                                    | [![Clazy](https://img.shields.io/badge/Clazy-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F13)](https://toolbox.basyskom.com/13) |
| Tool: Benefit From Peer Reviews                | [![Benefit From Peer Reviews](https://img.shields.io/badge/Benefit%20From%20Peer%20Reviews-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F14)](https://toolbox.basyskom.com/14) |
| Tool: Use Valgrind or MemorySanitizer          | [![Use Valgrind or MemorySanitizer](https://img.shields.io/badge/Use%20Valgrind%20or%20MemorySanitizer-orange?link=https%3A%2F%2Ftoolbox.basykom.com%2F15)](https://toolbox.basyskom.com/15) |
| Agile Essential: Definition of Ready           | [![Definition of Ready](https://img.shields.io/badge/Definition%20of%20Ready-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F16)](https://toolbox.basyskom.com/16) |
| Agile Essential: Interdisciplinary Teams       | [![Interdisciplinary Teams](https://img.shields.io/badge/Interdisciplinary%20Teams-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F17)](https://toolbox.basyskom.com/17) |
| Agile Essential: Implement a Retrospective     | [![Implement a Retrospective](https://img.shields.io/badge/Implement%20a%20Retrospective-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F18)](https://toolbox.basyskom.com/18) |
| Agile Essential: Daily Call                    | [![Daily Call](https://img.shields.io/badge/Daily%20Call-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F19)](https://toolbox.basyskom.com/19) |
| Agile Essential: Story                         | [![Story](https://img.shields.io/badge/Story-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F20)](https://toolbox.basyskom.com/20) |
| Agile Essential: DoD                           | [![DoD](https://img.shields.io/badge/DoD-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F21)](https://toolbox.basyskom.com/21) |
| Agile Essential: Scrum                         | [![Scrum](https://img.shields.io/badge/Scrum-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F22)](https://toolbox.basyskom.com/22) |
| Agile Essential: Storypoints                   | [![Storypoints](https://img.shields.io/badge/Storypoints-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F23)](https://toolbox.basyskom.com/23) |
| Agile Essential: Backlogs                      | [![Backlogs](https://img.shields.io/badge/Backlogs-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F24)](https://toolbox.basyskom.com/24) |
| Agile Essential: Sprint                        | [![Sprint](https://img.shields.io/badge/Sprint-gray?link=https%3A%2F%2Ftoolbox.basykom.com%2F25)](https://toolbox.basyskom.com/25) |
