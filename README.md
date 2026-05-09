# Intelligent Repository Health Analyzer using Kestra

![Kestra](https://img.shields.io/badge/Kestra-Orchestration-blue)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED)
![GitHub Actions](https://img.shields.io/badge/CI%2FCD-Automated-success)
![Terraform](https://img.shields.io/badge/IaC-Terraform-7B42BC)
![License](https://img.shields.io/badge/License-MIT-green)

## Overview

The Repository Health Analyzer is an advanced DevOps automation project built using Kestra+Grof
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

</div>

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
---

## Tasks

This is where the real work happens. Tasks are the individual steps within your flow — each one performs a discrete action. Tasks are incredibly versatile: they can send HTTP requests, run code in various languages, query databases, transform data, send notifications, and much more.

<img width="1469" height="804" alt="image" src="https://github.com/user-attachments/assets/497091d2-bc99-422f-8a6a-0b239ecd8226" />

<img width="1465" height="803" alt="image" src="https://github.com/user-attachments/assets/9d49f1d6-49c3-432d-b112-f8fa0a62b91d" />

## Inputs
Inputs make your flows dynamic. Instead of hard-coding values, you can parameterize your flow to accept different inputs each time it runs. This means you can execute the same flow multiple times with different values — no code changes needed.

## Execution
Throughout this course, we've been executing flows to see our concepts in action. But now that you understand how to build flows with tasks, inputs, outputs, triggers, expressions, and flowable tasks, it's worth taking a moment to understand what's actually happening behind the scenes when your flows run.

An Execution is a single run of your flow — your workflow in action, performing the steps you've defined. Every time you click Execute or a trigger fires, Kestra creates a new execution. Think of it like pressing play on your workflow: the execution is the recording of everything that happened during that run.

<img width="1467" height="801" alt="image" src="https://github.com/user-attachments/assets/33ae0ee4-7ab2-421c-bfd4-3af9630970f7" />

---
# 🌟 Final Thoughts

This project demonstrates how modern workflow orchestration can transform traditional DevOps operations into intelligent, automated, and scalable platforms.

By combining:

- Workflow orchestration with Kestra
- Security automation
- Infrastructure analysis
- CI/CD intelligence
- Repository health scoring
- Dashboard generation

this project showcases a real-world approach to building next-generation DevOps automation systems.

Instead of relying on scattered scripts and manual checks, the entire repository analysis lifecycle is centralized into a single orchestrated workflow — making operations more reliable, observable, and scalable.

As repositories continue to grow in complexity, automation platforms like Kestra become essential for:

- Platform Engineering
- DevOps Automation
- Infrastructure Governance
- Security Compliance
- CI/CD Standardization
- Operational Intelligence

This project is designed not only as a learning experience, but also as a foundation for building enterprise-grade DevOps intelligence platforms.

---

## 🚀 Future Vision

Potential future enhancements include:

- AI-powered repository recommendations
- Multi-repository analytics
- Historical trend analysis
- GitHub Pages dashboard hosting
- Real-time alerts & notifications
- Kubernetes manifest validation
- Helm chart analysis
- Infrastructure security scoring
- Cloud cost optimization insights

---

## 🤝 Contributing

Contributions, improvements, and ideas are always welcome.

Feel free to:

- Fork the repository
- Open issues
- Submit pull requests
- Suggest new workflow ideas
- Improve dashboard visualizations

---

# What I Learned Using Kestra

Working on this project helped me gain practical experience in workflow orchestration and modern DevOps automation using Kestra.

Kestra made it easier to transform multiple independent automation tasks into a centralized and intelligent workflow system.

Instead of relying on separate scripts and manual execution, I learned how to orchestrate complete DevOps processes using a clean, scalable, and production-ready orchestration platform.


---
📄 License
MIT — free to use, modify, and distribute.

