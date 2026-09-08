# Traceability

## Introduction

**Traceability** is the ability to follow a piece of work from its original requirement through development, testing, security validation, deployment, and delivery.

In a DevOps environment, traceability helps answer:

```text
Why was this change made?
        ↓
Which requirement requested it?
        ↓
Which code implemented it?
        ↓
Which Pull Request reviewed it?
        ↓
Which tests validated it?
        ↓
Which build produced it?
        ↓
Which deployment released it?
        ↓
Where was it deployed?
```

Without traceability, teams may have difficulty understanding the relationship between business requirements, source code, tests, builds, releases, and production deployments.

The current **AZ-400** objectives specifically include implementing a strategy for **source, bug, and quality traceability**.

A simplified traceability chain is:

```text
Requirement
     ↓
Work Item
     ↓
Branch
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
     ↓
Production
```

Traceability therefore connects the different parts of the DevOps lifecycle.

---

## 📚 Table of Contents

- [1. What is Traceability?](#1-what-is-traceability)
- [2. Why Traceability Matters](#2-why-traceability-matters)
- [3. End-to-End Traceability](#3-end-to-end-traceability)
- [4. Requirement Traceability](#4-requirement-traceability)
- [5. Source Code Traceability](#5-source-code-traceability)
- [6. Commit Traceability](#6-commit-traceability)
- [7. Pull Request Traceability](#7-pull-request-traceability)
- [8. Build Traceability](#8-build-traceability)
- [9. Test Traceability](#9-test-traceability)
- [10. Bug Traceability](#10-bug-traceability)
- [11. Quality Traceability](#11-quality-traceability)
- [12. Artifact Traceability](#12-artifact-traceability)
- [13. Release and Deployment Traceability](#13-release-and-deployment-traceability)
- [14. Security Traceability](#14-security-traceability)
- [15. Traceability Across Azure DevOps](#15-traceability-across-azure-devops)
- [16. Traceability Across GitHub and Azure DevOps](#16-traceability-across-github-and-azure-devops)
- [17. Traceability Example](#17-traceability-example)
- [18. Traceability During Production Incidents](#18-traceability-during-production-incidents)
- [19. Traceability for Auditing and Compliance](#19-traceability-for-auditing-and-compliance)
- [20. Traceability Best Practices](#20-traceability-best-practices)
- [21. Hands-On Lab](#21-hands-on-lab)
- [22. AZ-400 Exam Focus](#22-az-400-exam-focus)
- [23. Summary](#23-summary)

---

# 1. What is Traceability?

Traceability means maintaining relationships between different development and delivery artifacts.

For example:

```text
User Requirement
       ↓
Work Item #245
       ↓
Branch feature/payment
       ↓
Commit abc123
       ↓
Pull Request #82
       ↓
Build #450
       ↓
Test Results
       ↓
Artifact v2.4.0
       ↓
Production Deployment
```

If a production problem occurs, the team can work backward through this chain.

```text
Production Problem
       ↓
Deployment
       ↓
Artifact
       ↓
Build
       ↓
Commit
       ↓
Pull Request
       ↓
Work Item
       ↓
Requirement
```

This is the fundamental purpose of traceability.

---

# 2. Why Traceability Matters

Without traceability, development information can become disconnected.

```text
Requirement       → Unknown
Source Code       → Unknown
Tests             → Unknown
Build             → Unknown
Deployment        → Unknown
```

A team may know that a production deployment failed but not know exactly:

- What changed?
- Who made the change?
- Why was it made?
- Which requirement caused it?
- Which tests were executed?
- Which artifact was deployed?
- Which environment received it?

With traceability:

```text
Production Deployment
        ↓
Artifact
        ↓
Build
        ↓
Commit
        ↓
Pull Request
        ↓
Work Item
        ↓
Requirement
```

Traceability provides:

- Better visibility
- Faster investigation
- Easier auditing
- Better release confidence
- Easier troubleshooting
- Improved accountability
- Stronger quality control
- Better compliance evidence

---

# 3. End-to-End Traceability

The ideal DevOps environment connects work across the entire delivery chain.

```text
                    END-TO-END TRACEABILITY

Requirement
     │
     ↓
Work Item
     │
     ↓
Source Branch
     │
     ↓
Commit
     │
     ↓
Pull Request
     │
     ↓
Build
     │
     ↓
Tests
     │
     ↓
Artifact
     │
     ↓
Release
     │
     ↓
Deployment
     │
     ↓
Production
```

Each stage should provide enough information to identify the previous and next stage.

For example:

```text
Work Item #245
      ↓
PR #82
      ↓
Build #450
      ↓
Artifact v2.4.0
      ↓
Production Deployment #120
```

This creates a connected chain instead of isolated records.

---

# 4. Requirement Traceability

Requirement traceability connects a business or technical requirement to the implementation that delivers it.

Example:

```text
Requirement:

"Customers must be able to
reset their password."

        ↓

Work Item #125

        ↓

Development

        ↓

Pull Request

        ↓

Build

        ↓

Testing

        ↓

Release
```

The team can determine whether the requirement has actually been implemented and validated.

---

## Requirement → Implementation

A useful relationship is:

```text
Requirement
     ↓
Feature
     ↓
User Story
     ↓
Task
     ↓
Code
```

For example:

```text
Feature:
User Authentication

        ↓

User Story:
User can reset password

        ↓

Task:
Implement reset-password API

        ↓

Code:
password-reset-service
```

This provides traceability from the business requirement to the technical implementation.

---

# 5. Source Code Traceability

Source code traceability connects a change in the repository with the work that caused the change.

Example:

```text
Work Item #245
       ↓
feature/password-reset
       ↓
Commit abc123
       ↓
Pull Request #82
```

This allows the team to understand why a particular code change exists.

A developer should be able to answer:

```text
Why does this code exist?
        ↓
Which requirement requested it?
        ↓
Which work item tracks it?
```

Source-code traceability becomes especially valuable when investigating older changes.

---

# 6. Commit Traceability

A Git commit represents a specific change to source code.

Example:

```text
Commit:
abc123

Message:
Implement password reset API
```

A traceable commit should provide enough information to connect it to the relevant work.

Conceptually:

```text
Work Item
   ↓
Commit
```

For example:

```text
Work Item #245
"Implement password reset"

        ↓

Commit abc123
"Implement password reset API"
```

A good commit message should describe the change clearly.

Poor:

```text
update
```

Better:

```text
Implement password reset API
```

Best practice is to use the team's configured conventions for linking commits to work items.

---

# 7. Pull Request Traceability

A Pull Request provides another important traceability point.

Example:

```text
Work Item #245
      ↓
Branch feature/password-reset
      ↓
Pull Request #82
      ↓
Code Review
      ↓
Automated Validation
      ↓
Merge
```

The Pull Request can provide information about:

- Source branch
- Target branch
- Commits
- Changed files
- Reviewers
- Comments
- Automated checks
- Linked work

This makes it possible to determine how a change was reviewed before it entered an important branch.

---

# 8. Build Traceability

A build converts source code into a validated output or artifact.

Traceability should connect the build to the source that produced it.

```text
Commit
   ↓
Build #450
   ↓
Artifact
```

For example:

```text
Commit abc123
       ↓
Build #450
       ↓
Application Package
       ↓
Version 2.4.0
```

If the application deployed to production has a problem, the team can identify which build produced it.

---

## Build Information

A build should ideally provide information such as:

```text
Build Number
Source Commit
Branch
Pipeline
Build Status
Test Results
Artifact
Timestamp
```

This makes the build reproducible and easier to investigate.

---

# 9. Test Traceability

Testing should also be connected to the change being validated.

A simplified relationship is:

```text
Requirement
     ↓
Code Change
     ↓
Build
     ↓
Test
     ↓
Test Result
```

For example:

```text
Requirement:
Password reset must reject invalid tokens.

        ↓

Implementation

        ↓

Automated Test

        ↓

Test Result:
PASS
```

This allows teams to determine whether a requirement has been tested.

---

## Test Traceability

A test record can provide information such as:

```text
Test Name
Test Type
Build
Test Run
Result
Duration
Environment
Failure Details
```

For example:

```text
Build #450
     ↓
Integration Test
     ↓
Test Case #85
     ↓
PASS
```

If the test fails:

```text
Build #450
     ↓
Integration Test
     ↓
Test Case #85
     ↓
FAIL
```

The failure can then be connected back to the source change.

---

# 10. Bug Traceability

Bug traceability connects a defect to the code, work, test, and release associated with it.

Example:

```text
Production Bug
      ↓
Bug Work Item
      ↓
Fix Branch
      ↓
Commit
      ↓
Pull Request
      ↓
Build
      ↓
Test
      ↓
Release
```

For example:

```text
Bug #501

Problem:
Payment fails for expired cards.

        ↓

Fix:
Validate card expiration date.

        ↓

Pull Request #95

        ↓

Build #475

        ↓

Regression Tests

        ↓

Production
```

This makes it easier to understand how a defect was discovered and resolved.

---

# 11. Quality Traceability

**Quality traceability** connects development changes with the quality checks performed against them.

Example:

```text
Code Change
    ↓
Build
    ↓
Unit Tests
    ↓
Integration Tests
    ↓
Code Coverage
    ↓
Security Scan
    ↓
Quality Result
```

A quality record can answer:

```text
Was the code tested?
       ↓
Did the tests pass?
       ↓
What was the code coverage?
       ↓
Were security checks successful?
       ↓
Was the change allowed to proceed?
```

---

## Quality Gate Example

```text
Build
 ↓
Unit Tests
 ↓
Integration Tests
 ↓
Code Coverage
 ↓
Security Scan
 ↓
Quality Gate
 ↓
Pass / Fail
```

If the quality requirements are not satisfied:

```text
Quality Gate
     ↓
   Failed
     ↓
Deployment Blocked
```

If they pass:

```text
Quality Gate
     ↓
   Passed
     ↓
Continue Delivery
```

Traceability therefore helps connect quality decisions to the exact change being evaluated.

---

# 12. Artifact Traceability

An **artifact** is an output produced by a build or development process.

Examples include:

- Application packages
- Container images
- Libraries
- Deployment packages
- Configuration bundles

Artifact traceability connects the artifact to the source and build that produced it.

```text
Source Code
    ↓
Commit
    ↓
Build
    ↓
Artifact
```

For example:

```text
Commit abc123
      ↓
Build #450
      ↓
payment-api:v2.4.0
```

If version `v2.4.0` is running in production, the team should be able to identify its source and build.

---

# 13. Release and Deployment Traceability

Deployment traceability connects an artifact to the environment where it was deployed.

Example:

```text
Artifact v2.4.0
       ↓
Development
       ↓
Testing
       ↓
Staging
       ↓
Production
```

A deployment record should allow the team to determine:

```text
What was deployed?
       ↓
Which version?
       ↓
Which artifact?
       ↓
Which environment?
       ↓
When?
       ↓
Which deployment?
```

For example:

```text
Artifact:
payment-api:v2.4.0

        ↓

Deployment #120

        ↓

Environment:
Production

        ↓

Time:
10:30 AM
```

This is particularly important when multiple application versions are deployed across different environments.

---

# 14. Security Traceability

Security activities should also be connected to the software delivery process.

For example:

```text
Source Code
     ↓
Security Scan
     ↓
Finding
     ↓
Work Item
     ↓
Fix
     ↓
Pull Request
     ↓
Validation
     ↓
Deployment
```

Suppose a dependency vulnerability is detected.

```text
Security Scan
      ↓
Vulnerability
      ↓
Security Work Item
      ↓
Dependency Update
      ↓
Pull Request
      ↓
Security Scan
      ↓
Pass
```

This provides evidence that the security finding was not simply detected but also addressed.

---

# 15. Traceability Across Azure DevOps

Azure DevOps provides multiple services that can participate in traceability.

A simplified model is:

```text
Azure Boards
     ↓
Azure Repos
     ↓
Azure Pipelines
     ↓
Azure Test Plans
     ↓
Azure Artifacts
     ↓
Azure Environments
```

For example:

```text
Work Item
    ↓
Repository Change
    ↓
Pipeline Build
    ↓
Test Results
    ↓
Artifact
    ↓
Deployment
```

This creates a connected delivery history.

---

## Example Azure DevOps Traceability

```text
Azure Boards
Work Item #245
       ↓
Azure Repos
Branch / Commit / PR
       ↓
Azure Pipelines
Build #450
       ↓
Test Results
       ↓
Azure Artifacts
Package v2.4.0
       ↓
Deployment
Production
```

The exact integration depends on the team's Azure DevOps configuration.

---

# 16. Traceability Across GitHub and Azure DevOps

Modern organizations may use GitHub for source control while using Azure DevOps for pipelines or work tracking.

For example:

```text
                 Azure Boards
                     │
                     ↓
                 Work Item
                     │
                     ↓
                 GitHub Repo
                     │
             ┌───────┼────────┐
             ↓       ↓        ↓
          Branch   Commit      PR
             │       │        │
             └───────┼────────┘
                     ↓
              Azure Pipelines
                     ↓
                   Build
                     ↓
                   Tests
                     ↓
                 Artifact
                     ↓
                 Deployment
```

This allows teams to maintain traceability even when different DevOps platforms are used for different responsibilities.

The important principle is to maintain the relationships between:

```text
Planning
   ↕
Source Control
   ↕
CI/CD
   ↕
Testing
   ↕
Deployment
```

---

# 17. Traceability Example

Consider an online shopping application.

The business requirement is:

```text
Customers must be able to
receive an email after a successful payment.
```

---

## Step 1 — Requirement

```text
Requirement #100
Payment confirmation email
```

---

## Step 2 — Work Item

```text
User Story #245
Send confirmation email
```

---

## Step 3 — Development

Developer creates:

```text
feature/payment-confirmation
```

---

## Step 4 — Commit

```text
Commit abc123

Add payment confirmation email
```

---

## Step 5 — Pull Request

```text
Pull Request #82
        ↓
Code Review
        ↓
Automated Validation
```

---

## Step 6 — Build

```text
Build #450
        ↓
Source:
abc123
        ↓
Build:
PASS
```

---

## Step 7 — Testing

```text
Build #450
      ↓
Unit Tests
      ↓
Integration Tests
      ↓
Email Notification Test
      ↓
PASS
```

---

## Step 8 — Artifact

```text
Build #450
      ↓
payment-service:v2.4.0
```

---

## Step 9 — Deployment

```text
payment-service:v2.4.0
          ↓
       Staging
          ↓
      Production
```

---

## Complete Traceability Chain

```text
Requirement #100
       ↓
Work Item #245
       ↓
Branch feature/payment-confirmation
       ↓
Commit abc123
       ↓
Pull Request #82
       ↓
Build #450
       ↓
Test Results
       ↓
Artifact v2.4.0
       ↓
Production Deployment
```

If a production problem occurs, the team can follow this chain backward.

---

# 18. Traceability During Production Incidents

Traceability becomes especially valuable during incidents.

Suppose users report:

```text
Payment service is failing.
```

The operations team can start from production and work backward.

```text
Production Failure
       ↓
Current Deployment
       ↓
Artifact Version
       ↓
Build
       ↓
Commit
       ↓
Pull Request
       ↓
Work Item
       ↓
Recent Requirement
```

For example:

```text
Production
   ↓
payment-api:v2.4.0
   ↓
Build #450
   ↓
Commit abc123
   ↓
PR #82
   ↓
Work Item #245
```

The team can then determine:

```text
What changed?
Who changed it?
Why was it changed?
Was it reviewed?
Were tests executed?
Which build produced it?
When was it deployed?
```

This can significantly reduce investigation time.

---

# 19. Traceability for Auditing and Compliance

Traceability can also provide evidence for organizational and regulatory requirements.

For example, an organization may need to demonstrate:

```text
Requirement
    ↓
Implementation
    ↓
Review
    ↓
Testing
    ↓
Approval
    ↓
Deployment
```

A traceable delivery process can provide evidence such as:

- Work item history
- Commit history
- Pull Request reviews
- Build records
- Test results
- Security scan results
- Artifact versions
- Deployment records

For example:

```text
Requirement #245
       ↓
PR #82
       ↓
Reviewer Approval
       ↓
Build #450
       ↓
Security Scan
       ↓
Test Results
       ↓
Deployment #120
```

This provides a historical record of how the change moved through the delivery process.

---

# 20. Traceability Best Practices

## 1. Connect Requirements to Development

Use work items and appropriate repository references.

```text
Requirement
     ↓
Work Item
     ↓
Code
```

---

## 2. Use Meaningful Commit Messages

Avoid:

```text
update
fix
changes
```

Prefer:

```text
Fix payment timeout handling
```

---

## 3. Link Pull Requests to Work

Where supported, connect Pull Requests to the corresponding work items.

---

## 4. Preserve Build Information

Know which source version produced each build.

```text
Commit
  ↓
Build
```

---

## 5. Track Test Results

Maintain a relationship between the build and its test results.

```text
Build
  ↓
Tests
  ↓
Results
```

---

## 6. Version Artifacts

Use clear and consistent artifact versions.

Example:

```text
payment-api:v2.4.0
```

---

## 7. Track Deployments

Know which artifact was deployed to which environment.

```text
Artifact
   ↓
Environment
```

---

## 8. Include Security Results

Security findings should be connected to the affected change and remediation.

---

## 9. Avoid Broken Links

Traceability is useful only when the relationships remain accurate.

For example:

```text
Work Item
    ↓
Invalid Reference
    ↓
Unknown Code Change
```

should be avoided.

---

## 10. Automate Traceability Where Possible

Manual tracking becomes difficult as the organization grows.

Prefer automated relationships:

```text
Work Item
    ↓
Commit
    ↓
PR
    ↓
Build
    ↓
Test
    ↓
Artifact
    ↓
Deployment
```

---

# 21. Hands-On Lab

## 🎯 Objective

Create a simple end-to-end traceability chain connecting a work item, Git repository, Pull Request, build, test, and deployment.

### Lab Flow

```text
Work Item
    ↓
Git Branch
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
Deployment
```

---

## Step 1 — Create a Work Item

In Azure Boards, create a work item.

Example:

```text
Title:
Add health check endpoint

Description:
Add a health check endpoint that can
be used to verify application availability.
```

Record the work item ID.

Example:

```text
Work Item:
#300
```

---

## Step 2 — Create a Git Branch

Clone your repository:

```bash
git clone <repository-url>

cd <repository-name>
```

Update `main`:

```bash
git switch main

git pull origin main
```

Create a feature branch:

```bash
git switch -c feature/health-check
```

---

## Step 3 — Implement the Change

Add the health-check functionality.

For example:

```text
GET /health
```

should return a successful response when the application is healthy.

---

## Step 4 — Commit the Change

```bash
git add .

git commit -m "Add application health check"
```

Where supported, use your configured work-item linking convention.

---

## Step 5 — Push the Branch

```bash
git push -u origin feature/health-check
```

---

## Step 6 — Create a Pull Request

Create:

```text
feature/health-check
        ↓
       main
```

Review:

- Changed files
- Commits
- Work-item relationship
- Review comments
- Validation results

---

## Step 7 — Run a Build

Configure or use an existing CI pipeline.

The pipeline should:

```text
Checkout Code
      ↓
Build
      ↓
Run Tests
      ↓
Publish Artifact
```

Record the build number.

Example:

```text
Build #520
```

---

## Step 8 — Review Test Results

Verify that the build contains test results.

Example:

```text
Build #520

Unit Tests:
Passed: 25
Failed: 0

Result:
PASS
```

---

## Step 9 — Publish an Artifact

Publish the application output.

Example:

```text
health-api:v1.0.0
```

The relationship should now be:

```text
Commit
  ↓
Build #520
  ↓
Artifact v1.0.0
```

---

## Step 10 — Deploy

Deploy the artifact to a test environment.

```text
Artifact v1.0.0
      ↓
Test Environment
```

If the deployment succeeds, promote it to the next environment according to your pipeline design.

---

## Step 11 — Verify Traceability

Verify that you can follow:

```text
Work Item #300
      ↓
Branch feature/health-check
      ↓
Commit
      ↓
Pull Request
      ↓
Build #520
      ↓
Test Results
      ↓
Artifact v1.0.0
      ↓
Deployment
```

---

## Step 12 — Perform a Reverse Trace

Start from the deployed application and work backward.

```text
Deployment
    ↓
Artifact
    ↓
Build
    ↓
Commit
    ↓
Pull Request
    ↓
Work Item
```

If you can successfully navigate the entire chain, your traceability implementation is working.

---

# 22. AZ-400 Exam Focus

For the current AZ-400 exam, **traceability** is part of the objective covering the flow of work.

You should understand how to implement traceability for:

- Source
- Bugs
- Quality
- Work
- Builds
- Tests
- Artifacts
- Releases
- Deployments

The core concept is:

```text
Requirement
     ↓
Work Item
     ↓
Source Change
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

### Scenario Thinking

If a question asks:

> A team needs to determine which source change introduced a production problem.

Think:

```text
Production
    ↓
Deployment
    ↓
Artifact
    ↓
Build
    ↓
Commit
    ↓
Pull Request
    ↓
Source Change
```

---

If a question asks:

> A company needs to prove that a requirement was implemented, reviewed, and tested before release.

Think:

```text
Requirement
     ↓
Work Item
     ↓
Code
     ↓
Pull Request
     ↓
Review
     ↓
Build
     ↓
Test Results
     ↓
Release
```

---

If a question asks:

> A security or quality finding needs to be connected to the change that caused it and the work required to resolve it.

Think:

```text
Finding
   ↓
Work Item
   ↓
Code Change
   ↓
Pull Request
   ↓
Validation
   ↓
Resolution
```

---

## Key Exam Principle

Remember:

> **Traceability means being able to follow a change forward from requirement to production and backward from production to the original source.**

The two directions are:

```text
FORWARD TRACE

Requirement
    ↓
Code
    ↓
Build
    ↓
Test
    ↓
Artifact
    ↓
Deployment
```

and:

```text
BACKWARD TRACE

Production
    ↓
Deployment
    ↓
Artifact
    ↓
Build
    ↓
Commit
    ↓
Pull Request
    ↓
Requirement
```

---

# 23. Summary

**Traceability** connects requirements, work items, source code, Pull Requests, builds, tests, artifacts, releases, and deployments.

The complete traceability chain is:

```text
Requirement
     ↓
Work Item
     ↓
Branch
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
     ↓
Production
```

The key concepts introduced in this section are:

- **Requirement Traceability** connects business requirements to implementation.
- **Source Traceability** connects code changes to the work that caused them.
- **Commit Traceability** provides a history of individual changes.
- **Pull Request Traceability** connects code review and validation to a change.
- **Build Traceability** identifies which source produced a build.
- **Test Traceability** connects validation results to the code and build being tested.
- **Bug Traceability** connects defects to their fixes and releases.
- **Quality Traceability** connects quality checks and gates to a specific change.
- **Artifact Traceability** identifies the source and build behind a deployable package.
- **Deployment Traceability** identifies which artifact was deployed to each environment.
- **Security Traceability** connects security findings to remediation work.
- **End-to-End Traceability** allows teams to follow changes from requirements to production and back again.

The most important sequence to remember is:

> **Requirement → Work → Source → Build → Test → Artifact → Release → Deployment**

And for troubleshooting:

> **Production → Deployment → Artifact → Build → Commit → Pull Request → Work Item → Requirement**

---

