# Mainframe Batch to AWS Scheme

A portfolio project that demonstrates how a traditional mainframe batch workload can be modernized on AWS using two distinct strategies:

1. **Re-host (lift-and-shift, conceptual)**  
   Preserve the legacy operating model by running COBOL workloads in a compatible runtime environment.

2. **Re-platform / Re-engineer (practical implementation)**  
   Rebuild the batch workload using modern cloud-native components such as Rust, containers, S3, Terraform, and AWS operational services.

---

## Project goal

This repository shows how a typical batch-oriented financial processing flow can evolve from a mainframe pattern:

- COBOL batch program
- JCL job orchestration
- fixed-width transaction file
- VSAM / DB2-like data flow

into a modern AWS-aligned architecture using:

- Rust batch application
- Docker container
- Amazon S3
- Amazon ECS or Lambda
- Amazon RDS / Aurora
- CloudWatch
- Terraform
- GitHub Actions
-

---

## Why Rust for the modern implementation?

Rust was chosen for the modernized batch path because it aligns well with the requirements of workloads that traditionally run on the mainframe:

- **Reliability and safety**: Rust provides strong memory safety guarantees without garbage collection, which is valuable for predictable batch execution.
- **Performance**: batch processing often deals with large input files and deterministic transformations, where Rust performs very well.
- **Operational efficiency**: Rust binaries are lightweight and deploy well in containers, which is useful for ECS-based execution.
- **Modern engineering value**: the project is not only about translating legacy logic, but also about demonstrating how stable, critical workloads can move to a modern and robust implementation model.
- **Portfolio differentiation**: using Rust highlights modern systems engineering capability in addition to legacy/mainframe knowledge.

In this project, Rust is not presented as the only valid modernization target. Instead, it is used as a practical example of a modern, safe, and cloud-friendly implementation choice.

---

## Why this project matters

This project is designed to demonstrate practical modernization thinking, not just code translation.

It highlights:

- legacy batch understanding
- modernization decision-making
- cloud architecture mapping
- infrastructure as code
- containerization
- operational readiness

---

## Modernization strategies

### 1) Re-host

Best when the goal is speed, low application change, and minimal disruption.

Typical mapping:

- COBOL remains largely unchanged
- JCL remains part of the operating model
- workloads run in a compatible runtime or managed modernization platform

Trade-offs:

- faster migration
- lower code change
- potentially higher long-term platform cost
- less cloud-native flexibility

### 2) Re-platform / Re-engineer

Best when the goal is long-term maintainability, observability, and cloud-native evolution.

Typical mapping:

- fixed-width input / VSAM-like file → S3
- batch job → container on ECS or small Lambda workload
- DB2-like persistence → RDS / Aurora
- SYSOUT / operational logs → CloudWatch
- infrastructure → Terraform
- pipeline → GitHub Actions

Trade-offs:

- more engineering effort
- stronger long-term architecture
- better operational visibility
- lower runtime lock-in

---

## Current implementation status

### Legacy path

Implemented:

- COBOL batch program
- representative JCL artifact
- local execution using GnuCOBOL
- fixed-width input file
- batch summary generation

### Modern path

Implemented:

- Rust application skeleton
- fixed-width input parsing
- structured logging
- Docker packaging

Planned:

- AWS Terraform foundation
- S3 integration
- CloudWatch integration
- ECS execution model
- RDS/Aurora integration
- CI/CD improvements

---

## Repository structure

```text
.
├── .github/
│   └── workflows/
├── docs/
│   ├── decision-matrix.md
│   ├── diagram.mmd
│   └── runbook.md
├── legacy/
│   ├── cobol/
│   ├── data/
│   └── jcl/
├── modern/
│   ├── app/
│   └── infra/
│       └── terraform/
├── scripts/
├── .gitignore
└── README.md
```
