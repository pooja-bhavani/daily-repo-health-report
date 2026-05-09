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

## Project Strucutre

```text
                    +----------------------+
                    |   GitHub Repository  |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    |   Kestra Workflow    |
                    +----------+-----------+
                               |
          +--------------------+--------------------+
          |                    |                    |
          v                    v                    v
+----------------+   +----------------+   +----------------+
| Security Scan  |   | Docker Checks |   | Repo Analysis  |
+----------------+   +----------------+   +----------------+
          |                    |                    |
          +--------------------+--------------------+
                               |
                               v
                    +----------------------+
                    | Dashboard Generator  |
                    +----------------------+
                               |
                               v
                    +----------------------+
                    | Markdown + HTML UI   |
                    +----------------------+
```
## What is Kestra?

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

4. Once the file is downloaded, you can start Kestra with the following command:
```
docker compose up -d
```

<img width="1469" height="802" alt="image" src="https://github.com/user-attachments/assets/faaf7335-94e5-4e77-b77f-cfafe253ba63" />

## Configure Kestra
Inside of your docker-compose.yml file, there is an environment variable called KESTRA_CONFIGURATION . This is where we can configure our Kestra environment.
```
environment:
  KESTRA_CONFIGURATION: |
    datasources:
      postgres:
        url: jdbc:postgresql://postgres:5432/kestra
        driverClassName: org.postgresql.Driver
        username: kestra
        password: k3str4
    kestra:
      # server:
      #   basic-auth:
      #     username: admin@kestra.io # it must be a valid email address
      #     password: Admin1234! # it must be at least 8 characters long with uppercase letter and a number
      repository:
        type: postgres
      storage:
        type: local
        local:
          base-path: "/app/storage"
      queue:
        type: postgres
      tasks:
        tmp-dir:
          path: /tmp/kestra-wd/tmp
      url: http://localhost:8080/
```
---

## Flows

Every journey begins with a Flow. A flow is your workflow's container — it holds all the tasks you want to execute and defines how they work together. Think of it as a recipe: it lists the ingredients (tasks) and the steps to follow (orchestration logic).

Flows can be created through the Flow Editor using YAML, No-code Editor as well as with the AI Copilot.
<img width="1470" height="800" alt="image" src="https://github.com/user-attachments/assets/d5dc3e51-8e81-486f-b102-53dd0bd071c1" />

<img width="1470" height="805" alt="image" src="https://github.com/user-attachments/assets/aa1ec993-8e58-428a-9d4c-79bb026c00b2" />
