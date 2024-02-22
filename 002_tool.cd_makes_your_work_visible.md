# Continuous Delivery makes your work visible early

## Goals

Regular delivery into production systems. Reduce the cost, time, and risk of delivering changes.

## Description

[Continuous Delivery](https://en.wikipedia.org/wiki/Continuous_delivery) and Continuous Integration are related disciplines. Continuous Delivery is the ability to get changes to the users, safely and quickly in a sustainable way. A Continuous Delivery process achieves this by ensuring that code is always in a deployable state even when making changes on a daily basis. Continuous Delivery completely eliminates traditional integration, testing and hardening phases as well as code freezes. 

Continuous Delivery is an approach, in which you deliver software in short cycles. It is about ensuring that the software can be reliably released at any time. It aims at building, testing, and releasing software with greater speed and frequency. Continuous Delivery helps to reduce the cost, time, and risk of delivering changes by allowing for more incremental updates to applications in production. A straightforward and repeatable deployment process is important for continuous delivery.

In contrast to Continuous Integration / Continuous Deployment, a Continuous Delivery process is a manually triggered process.

## Environment

Projects with web capabilities

## Platform

Web, Embedded, Desktop

## Implementation effort

Depends on the size of the project. On web projects, it is usually easily integrated with your pipelines. On embedded or desktop projects, the primary effort will be the update capabilities on your client software.

## Applicability

New projects, web projects. 

## Caveats

\- 

## See also

* [Continuous Integration](https://toolbox.basyskom.com/3)
* [Proper automated builds](https://toolbox.basyskom.com/9)

## Implementation hints

* If "on-premise" is a must have a look into Jenkins or gitlab-ci. If the cloud is an option look into Travis or AppVeyor (for Windows) or Circle CI.
* Traditionally the CI configuration of a project was kept separated from the project itself (often even outside of version control). Placing the CI configuration alongside the actual project is nowadays supported by a lot of systems and it adds a lot of control and flexibility. Examples are Jenkins pipelines or Travis yaml files.
