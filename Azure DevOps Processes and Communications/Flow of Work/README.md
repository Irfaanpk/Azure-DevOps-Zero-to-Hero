# Flow of Work

## 📖 Introduction

The **flow of work** describes how work moves through the software development and delivery lifecycle — from an initial requirement to development, testing, deployment, operations, and feedback.

In a DevOps environment, the objective is to create a continuous and efficient flow of value.

A typical DevOps flow is:

```text
Plan
  ↓
Develop
  ↓
Build
  ↓
Test
  ↓
Release
  ↓
Deploy
  ↓
Operate
  ↓
Monitor
  ↓
Feedback
  ↓
Plan
```

The flow is continuous because feedback from development, testing, production, monitoring, and users can create new work.

---

## 📚 Table of Contents

- [1. What is Flow of Work?](#1-what-is-flow-of-work)
- [2. Why Flow of Work is Important](#2-why-flow-of-work-is-important)
- [3. Traditional Software Delivery Flow](#3-traditional-software-delivery-flow)
- [4. DevOps Flow of Work](#4-devops-flow-of-work)
- [5. Azure DevOps and the Flow of Work](#5-azure-devops-and-the-flow-of-work)
- [6. Planning](#6-planning)
- [7. Development](#7-development)
- [8. Code Review](#8-code-review)
- [9. Build](#9-build)
- [10. Testing](#10-testing)
- [11. Release and Deployment](#11-release-and-deployment)
- [12. Operations and Monitoring](#12-operations-and-monitoring)
- [13. Feedback](#13-feedback)
- [14. Continuous Integration and Continuous Delivery](#14-continuous-integration-and-continuous-delivery)
- [15. Traceability](#15-traceability)
- [16. Bottlenecks](#16-bottlenecks)
- [17. DevOps Metrics](#17-devops-metrics)
- [18. Real-World Example](#18-real-world-example)
- [19. Best Practices](#19-best-practices)
- [20. Hands-On Lab](#20-hands-on-lab)
- [21. AZ-400 Exam Focus](#21-az-400-exam-focus)
- [22. Summary](#22-summary)

---

# 1. What is Flow of Work?

The **flow of work** represents how a requirement, feature, bug, or other piece of work moves through different stages of software delivery.

A simple representation is:

```text
Business Requirement
        ↓
Work Item
        ↓
Development
        ↓
Source Control
        ↓
Build
        ↓
Testing
        ↓
Artifact
        ↓
Deployment
        ↓
Production
        ↓
Monitoring
        ↓
Feedback
```

The objective is to move work through these stages with minimum unnecessary delay.

A good flow should be:

- Fast
- Predictable
- Automated where appropriate
- Traceable
- Secure
- Measurable
- Continuously improving

---

# 2. Why Flow of Work is Important

A poor flow can result in:

- Long development cycles
- Manual processes
- Delayed testing
- Deployment errors
- Poor communication
- Lack of traceability
- Long approval times
- Difficult troubleshooting
- Slow customer feedback

DevOps improves the flow through automation and collaboration.

| DevOps Practice | Purpose |
|---|---|
| Source Control | Track and manage changes |
| Continuous Integration | Frequently validate code changes |
| Automated Testing | Detect problems early |
| Continuous Delivery | Automate software delivery |
| Infrastructure as Code | Automate infrastructure changes |
| Monitoring | Observe applications and infrastructure |
| Feedback | Continuously improve the system |
| Traceability | Connect work to delivery |

---

# 3. Traditional Software Delivery Flow

Traditional software delivery often involves separate teams.

```text
Business
   ↓
Requirements
   ↓
Development
   ↓
Testing
   ↓
Operations
   ↓
Production
```

Each team may have separate processes and responsibilities.

This can create handoffs and waiting periods.

For example:

```text
Developer
   ↓
Code Complete
   ↓
Waiting for Testing
   ↓
Testing Complete
   ↓
Waiting for Operations
   ↓
Deployment
```

The more manual handoffs exist, the longer the overall delivery process can become.

---

# 4. DevOps Flow of Work

DevOps connects development and operations activities into a continuous lifecycle.

```text
Plan
 ↓
Code
 ↓
Build
 ↓
Test
 ↓
Release
 ↓
Deploy
 ↓
Operate
 ↓
Monitor
 ↓
Feedback
 ↓
Plan
```

Instead of completing one phase and handing everything to another team, teams collaborate throughout the lifecycle.

A modern workflow may look like:

```text
Requirement
     ↓
Work Tracking
     ↓
Source Control
     ↓
Pull Request
     ↓
Code Review
     ↓
Build
     ↓
Automated Tests
     ↓
Security Validation
     ↓
Artifact
     ↓
Deployment
     ↓
Production
     ↓
Monitoring
     ↓
Feedback
```

---

# 5. Azure DevOps and the Flow of Work

Azure DevOps provides services that support different parts of the software delivery lifecycle.

| Azure DevOps Service | Main Purpose |
|---|---|
| Azure Boards | Plan and track work |
| Azure Repos | Source control |
| Azure Pipelines | Build and deployment automation |
| Azure Test Plans | Test management |
| Azure Artifacts | Package and artifact management |
| Azure DevOps Wiki | Documentation |

A simplified Azure DevOps flow is:

```text
┌────────────────────┐
│    Azure Boards    │
│ Plan & Track Work  │
└─────────┬──────────┘
          ↓
┌────────────────────┐
│    Azure Repos     │
│   Source Control   │
└─────────┬──────────┘
          ↓
┌────────────────────┐
│   Azure Pipelines  │
│ Build & Automation │
└─────────┬──────────┘
          ↓
┌────────────────────┐
│      Testing       │
│  Quality Validation│
└─────────┬──────────┘
          ↓
┌────────────────────┐
│   Azure Artifacts  │
│ Packages/Artifacts │
└─────────┬──────────┘
          ↓
┌────────────────────┐
│     Deployment     │
│ Dev → Test → Prod  │
└─────────┬──────────┘
          ↓
┌────────────────────┐
│     Monitoring     │
│ Telemetry & Alerts │
└─────────┬──────────┘
          ↓
       Feedback
          ↓
    Azure Boards
```

These services can be combined according to the organization's requirements.

---

# 6. Planning

The flow starts with planning.

A requirement can come from:

- Business teams
- Customers
- Product owners
- Developers
- Operations teams
- Security teams
- Monitoring systems

Examples include:

```text
New Feature
Bug Fix
Security Improvement
Performance Improvement
Infrastructure Change
Technical Debt
```

The work can be represented using work items.

For example:

```text
Epic
  ↓
Feature
  ↓
User Story
  ↓
Task
```

### Example

```text
Epic:
Application Security

    ↓

Feature:
Multi-Factor Authentication

    ↓

User Story:
As a user, I want MFA so that my account is more secure.

    ↓

Tasks:
- Configure authentication
- Implement MFA
- Write tests
- Update documentation
```

The work item becomes the starting point for traceability.

---

# 7. Development

After work is planned, developers implement the requirement.

A typical development flow is:

```text
Work Item
    ↓
Create Branch
    ↓
Write Code
    ↓
Commit
    ↓
Push
```

Example:

```text
main
 │
 ├── feature/mfa
 │
 ├── feature/payment
 │
 └── bug/login-error
```

Developers can work independently on branches and later merge their changes through a Pull Request.

---

# 8. Code Review

A Pull Request allows changes to be reviewed before they are merged.

```text
Feature Branch
      ↓
Pull Request
      ↓
Code Review
      ↓
Build Validation
      ↓
Automated Tests
      ↓
Approval
      ↓
Merge
```

Branch policies can require:

- Reviewers
- Successful builds
- Passing tests
- Linked work items
- Resolved comments
- Merge restrictions

Example:

```text
Pull Request
      │
      ├── Code Review
      │
      ├── Build Validation
      │
      ├── Automated Tests
      │
      └── Security Checks
              ↓
          Validation
              ↓
        ┌─────┴─────┐
        ↓           ↓
      Pass         Fail
        ↓           ↓
      Merge        Fix
```

This helps maintain source-code quality.

---

# 9. Build

After code is pushed or merged, a CI pipeline can automatically build the application.

A typical build flow is:

```text
Source Code
     ↓
Checkout
     ↓
Restore Dependencies
     ↓
Compile
     ↓
Build
     ↓
Package
```

For example:

```text
Developer Push
      ↓
Pipeline Trigger
      ↓
Build Agent
      ↓
Compile Application
      ↓
Run Build Tasks
      ↓
Create Artifact
```

Automation makes the build process repeatable.

---

# 10. Testing

Testing validates the application before it moves further through the delivery flow.

Common testing activities include:

```text
Unit Testing
     ↓
Integration Testing
     ↓
Load Testing
     ↓
Security Testing
```

### Unit Testing

Unit tests validate individual components.

```text
Function
   ↓
Unit Test
   ↓
Pass / Fail
```

### Integration Testing

Integration tests validate interactions between components.

```text
Application
    ↓
API
    ↓
Database
    ↓
Integration Test
```

### Load Testing

Load testing evaluates application behavior under expected or high levels of traffic.

```text
Users
  ↓
Application
  ↓
Load Test
  ↓
Performance Results
```

A pipeline can stop when tests fail.

```text
Build
  ↓
Test
  ↓
Tests Passed?
 ├── Yes → Continue
 └── No  → Stop Pipeline
```

---

# 11. Release and Deployment

After the application passes required validation, it can be packaged and deployed.

A typical environment flow is:

```text
Development
     ↓
Testing
     ↓
Staging
     ↓
Production
```

The same validated artifact can be promoted through environments.

```text
Build
  ↓
Artifact
  ↓
Development
  ↓
Testing
  ↓
Staging
  ↓
Production
```

Approvals and checks can be used before sensitive environments.

Deployment targets can include:

- Azure App Service
- Azure Functions
- Azure Virtual Machines
- Azure Container Apps
- Azure Kubernetes Service
- Other supported environments

The deployment process should be automated wherever appropriate.

---

# 12. Operations and Monitoring

After deployment, the application enters the operations phase.

Operations may include:

- Availability management
- Performance monitoring
- Resource monitoring
- Incident management
- Troubleshooting
- Configuration management
- Security monitoring

Monitoring can collect information such as:

| Area | Example |
|---|---|
| CPU | CPU utilization |
| Memory | Memory usage |
| Disk | Disk utilization |
| Network | Network traffic |
| Application | Request failures |
| Performance | Response time |
| Availability | Service availability |
| Errors | Application exceptions |

A simplified monitoring flow is:

```text
Application
     ↓
Telemetry
     ↓
Azure Monitor
     ↓
Analysis
     ↓
Alert
     ↓
Investigation
```

---

# 13. Feedback

Feedback is an essential part of DevOps.

Feedback can come from:

- Developers
- Testers
- Operations
- Security systems
- Monitoring systems
- Customers
- Users

For example:

```text
Production
    ↓
Application Error
    ↓
Monitoring Alert
    ↓
Investigation
    ↓
Bug
    ↓
Work Item
    ↓
Developer
```

The new work enters the lifecycle again.

```text
PLAN
  ↓
DEVELOP
  ↓
BUILD
  ↓
TEST
  ↓
DEPLOY
  ↓
OPERATE
  ↓
MONITOR
  ↓
FEEDBACK
  │
  └────────────→ PLAN
```

This continuous feedback loop is a fundamental DevOps concept.

---

# 14. Continuous Integration and Continuous Delivery

## Continuous Integration

Continuous Integration (CI) focuses on frequently integrating and validating code changes.

```text
Developer
    ↓
Commit
    ↓
Push
    ↓
CI Trigger
    ↓
Build
    ↓
Test
    ↓
Artifact
```

CI helps detect problems early.

---

## Continuous Delivery

Continuous Delivery extends the process beyond building and testing.

```text
Code
 ↓
Build
 ↓
Test
 ↓
Artifact
 ↓
Development
 ↓
Testing
 ↓
Staging
 ↓
Production
```

The objective is to make software consistently ready for deployment.

---

# 15. Traceability

**Traceability** means connecting different parts of the delivery lifecycle.

A complete traceability chain can look like:

```text
Requirement
     ↓
Work Item
     ↓
Commit
     ↓
Pull Request
     ↓
Build
     ↓
Test
     ↓
Artifact
     ↓
Release
     ↓
Deployment
```

Traceability helps answer questions such as:

- Which requirement caused this change?
- Which developer implemented it?
- Which Pull Request introduced it?
- Which build contains the change?
- Which tests validated it?
- Which artifact was deployed?
- Which environment received it?

Traceability is especially important in enterprise environments.

---

# 16. Bottlenecks

A **bottleneck** is a stage that slows down the overall flow.

Example:

```text
Development
     ↓
Build
     ↓
Testing
     ↓
     ↓
     ↓
Manual Approval
     ↓
Deployment
```

If testing takes several days while development takes only a few hours, testing may become a bottleneck.

Common bottlenecks include:

| Bottleneck | Example |
|---|---|
| Manual Testing | Large amount of manual validation |
| Manual Deployment | Engineers deploy applications manually |
| Slow Builds | Pipelines take too long |
| Long Code Reviews | Pull Requests wait for approval |
| Environment Availability | Test environments are unavailable |
| Manual Approvals | Deployment waits for people |
| Poor Communication | Teams do not receive timely information |

DevOps practices attempt to identify and reduce these bottlenecks.

---

# 17. DevOps Metrics

Organizations can measure how efficiently work moves through the delivery lifecycle.

Important metrics include:

| Metric | Description |
|---|---|
| Lead Time | Time from work initiation to delivery |
| Cycle Time | Time taken for work to move through development |
| Deployment Frequency | How frequently deployments occur |
| Change Failure Rate | Percentage of deployments that result in failures |
| Time to Recovery | Time required to recover from failures |
| Build Duration | Time required to complete builds |
| Test Duration | Time required to execute tests |
| Pipeline Failure Rate | Frequency of pipeline failures |

Example:

```text
Planning       → 2 Days
Development    → 3 Days
Testing        → 1 Day
Approval       → 2 Days
Deployment     → 30 Minutes
```

In this example, the approval stage may be a bottleneck.

Metrics should help teams identify improvement opportunities.

---

# 18. Real-World Example

Consider an e-commerce company that wants to add a new payment method.

The complete flow could be:

```text
Business Requirement
        ↓
Azure Boards Work Item
        ↓
Developer Creates Branch
        ↓
Code Development
        ↓
Git Commit
        ↓
Pull Request
        ↓
Code Review
        ↓
CI Pipeline
        ↓
Build
        ↓
Automated Tests
        ↓
Security Checks
        ↓
Artifact
        ↓
Development Deployment
        ↓
Testing
        ↓
Staging
        ↓
Approval
        ↓
Production
        ↓
Monitoring
        ↓
Customer Feedback
        ↓
New Work Item
```

This demonstrates how a business requirement can move through the complete DevOps lifecycle.

---

# 19. Best Practices

## 1. Automate Repetitive Work

Automate builds, testing, deployments, infrastructure changes, and other repeatable activities where appropriate.

## 2. Keep Changes Small

Small changes are easier to:

- Review
- Test
- Deploy
- Troubleshoot
- Roll back

## 3. Integrate Frequently

Frequent integration helps detect conflicts and problems earlier.

## 4. Test Early

Testing should happen as early as practical.

```text
Code
 ↓
Build
 ↓
Test
```

## 5. Maintain Traceability

Connect work items, commits, Pull Requests, builds, tests, artifacts, and deployments.

## 6. Monitor Production

Monitoring provides visibility into application and infrastructure behavior.

## 7. Create Short Feedback Loops

Problems should return to the development process quickly.

## 8. Measure the Flow

Use metrics to identify bottlenecks and improve delivery.

## 9. Automate Infrastructure

Use Infrastructure as Code and pipelines to make infrastructure changes repeatable.

## 10. Continuously Improve

DevOps is an iterative process.

```text
Measure
   ↓
Identify Problem
   ↓
Improve
   ↓
Automate
   ↓
Measure Again
```

---

# 20. Hands-On Lab

## 🎯 Objective

Create a simple Azure DevOps workflow that demonstrates how work moves from planning to source control and CI.

### Lab Flow

```text
Azure Boards
     ↓
Azure Repos
     ↓
Pull Request
     ↓
Azure Pipelines
     ↓
Build
     ↓
Test
     ↓
Artifact
```

---

## Step 1 — Create an Azure DevOps Project

Create a new Azure DevOps project.

Example:

```text
Project Name:
DevOps-Flow-Demo
```

---

## Step 2 — Create a Work Item

Create a User Story.

Example:

```text
Title:
Create a simple web application
```

---

## Step 3 — Create an Azure Repos Repository

Create a Git repository.

Example:

```text
Repository:
devops-flow-demo
```

---

## Step 4 — Clone the Repository

```bash
git clone <repository-url>

cd devops-flow-demo
```

---

## Step 5 — Create a Feature Branch

```bash
git checkout -b feature/initial-application
```

---

## Step 6 — Add Application Files

Example structure:

```text
devops-flow-demo/
│
├── README.md
├── src/
│   └── app
│
└── tests/
```

---

## Step 7 — Commit the Changes

```bash
git add .

git commit -m "Add initial application"

git push -u origin feature/initial-application
```

---

## Step 8 — Create a Pull Request

Create a Pull Request from:

```text
feature/initial-application
            ↓
           main
```

Review the changes before merging.

---

## Step 9 — Create a Pipeline

Create an Azure Pipeline connected to the repository.

The pipeline should perform:

```text
Checkout
   ↓
Build
   ↓
Test
   ↓
Publish Artifact
```

---

## Step 10 — Observe the Flow

Verify the relationship:

```text
Work Item
    ↓
Git Branch
    ↓
Commit
    ↓
Pull Request
    ↓
Pipeline
    ↓
Build
    ↓
Test
    ↓
Artifact
```

The objective is to understand the movement of work through the lifecycle.

---

# 21. AZ-400 Exam Focus

For AZ-400, understand the flow of work from both a conceptual and practical perspective.

Important areas include:

- Flow of work
- Planning
- Work tracking
- GitHub Flow
- Feedback cycles
- Notifications
- Source control
- Continuous Integration
- Continuous Delivery
- Testing
- Deployment
- Monitoring
- Traceability
- DevOps metrics
- Collaboration

You should be able to understand a scenario and determine:

```text
Where does the work start?
        ↓
How is it tracked?
        ↓
Where is the source code stored?
        ↓
How is the change reviewed?
        ↓
How is it built?
        ↓
How is it tested?
        ↓
How is it packaged?
        ↓
How is it deployed?
        ↓
How is it monitored?
        ↓
How does feedback return to planning?
```

---

# 22. Summary

The **flow of work** represents the continuous movement of work from an initial requirement through development, testing, delivery, deployment, operations, monitoring, and feedback.

The overall lifecycle is:

```text
PLAN
  ↓
DEVELOP
  ↓
BUILD
  ↓
TEST
  ↓
RELEASE
  ↓
DEPLOY
  ↓
OPERATE
  ↓
MONITOR
  ↓
FEEDBACK
  ↓
PLAN
```

The key concepts introduced in this section are:

- **Flow of Work** connects the different stages of software delivery.
- **Planning** converts requirements into trackable work.
- **Source Control** manages application and infrastructure changes.
- **Code Review** validates changes before they are merged.
- **Build and Testing** validate software quality.
- **Artifacts** provide deployable outputs.
- **Deployment** moves validated changes into environments.
- **Monitoring** provides visibility into applications and infrastructure.
- **Feedback** creates a continuous improvement loop.
- **Traceability** connects work, code, builds, tests, artifacts, and deployments.
- **DevOps Metrics** help identify bottlenecks and improve the flow.
- **Automation and Collaboration** help create a faster, more reliable delivery process.

The most important concept to remember is:

> **DevOps is a continuous flow of value from planning to production, supported by automation, collaboration, traceability, measurement, and continuous feedback.**

---
