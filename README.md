# OpenTelemetry in the Cloud

This repository contains all of the instructions and files needed to have a first introduction to instrumenting an application with OpenTelemetry. In this lab you will identify and resolve various bugs using New Relic as your observability platform.

## Requirements

* Laptop with Mac OS X. Windows is not supported for this workshop
* [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running
* A free account with [New Relic](https://newrelic.com)
* [Homebrew](https://brew.sh/)
* Minikube / Kubectl / Skaffold / Git: `brew install minikube kubectl skaffold git`

> If you prefer to download these requirements manually (instead of using homebrew) you may choose to do so using the following links: [Minikube](https://minikube.sigs.k8s.io/docs/start/) || [Kubectl](https://kubernetes.io/docs/tasks/tools/) || [Skaffold](https://skaffold.dev/) || [Git](https://github.com/git-guides/install-git)


## Getting Started

1. From a new terminal window, clone this repository to your local machine using Git `git clone https://github.com/Bijesse/otel-workshop.git`
2. Navigate into your new workspace using `cd otel-workshop`
3. Move onto the first lab of this workshop

* Lab 1: [Setting up your environment](lab_1-Setting_up_environment.md)
* Lab 2: [Debugging a slow trace](lab_2-Debugging-a-slow-trace.md)
* Lab 3: [Building spans](lab_3-Building-Spans.md)
* Lab 4: [Adding span attributes](lab_4-Span-Attributes.md) 