# Intelligent Repository Health Analyzer using Kestra

## Overview

The Repository Health Analyzer is an advanced DevOps automation project built using Kestra
 that continuously analyzes GitHub repositories and generates intelligent DevOps health reports.

This project demonstrates how modern workflow orchestration can automate:

Repository analysis
DevOps maturity checks
Security scanning
Docker validation
Infrastructure analysis
CI/CD inspection
Markdown & HTML dashboard generation

What is Kestra?

[Kestra official docs](https://academy.kestra.io/view/courses/kestra-fundamentals/3492611-introduction/11404080-what-is-kestra) 

Kestra is an open-source orchestration platform built to handle workflows of any scale — from simple three-step automations to complex pipelines with hundreds of tasks running across distributed systems.

Unlike tools that are built for a single use case and fall short outside that area, Kestra gives you flexibility. You can build workflows with code (YAML), visually with a no-code editor, or even with the AI Copilot that writes your flows for you. Use whichever approach fits your style and the complexity of what you're building.

Kestra is API-first and event-driven, which makes it a natural fit for modern systems. It is also built to scale, with the observability and control you need for everything from simple automations to mission-critical enterprise workflows.

## Install Kestra
Before you begin, make sure you have Docker installed. Once installed.

1. Linux/macOS:
```
curl -o docker-compose.yml \
https://raw.githubusercontent.com/kestra-io/kestra/develop/docker-compose.yml
```

3. Windows:
```
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/kestra-io/kestra/develop/docker-compose.yml" -OutFile "docker-compose.yml"
```
