# DevOps Metrics, Dashboards and Queries

## Introduction

**DevOps metrics** provide measurable information about how effectively a team plans, develops, tests, secures, delivers, and operates software.

Metrics help teams answer questions such as:

```text
How quickly are we delivering changes?
        ↓
How long does work take?
        ↓
How frequently are changes delivered?
        ↓
How often do changes fail?
        ↓
How quickly can we recover?
        ↓
Where are the bottlenecks?
```

Metrics should not exist only for reporting.

Their main purpose is to help teams:

- Understand delivery performance
- Identify bottlenecks
- Detect quality problems
- Improve planning
- Improve development
- Improve testing
- Improve security
- Improve delivery
- Improve operations
- Make data-driven decisions

The current **AZ-400** objectives specifically include implementing **metrics and queries** for project planning, development, testing, security, delivery, and operations, as well as dashboards containing metrics such as **cycle time, lead time, and time to recovery**.

A simple DevOps measurement cycle is:

```text
Collect Data
     ↓
Create Queries
     ↓
Build Metrics
     ↓
Visualize on Dashboard
     ↓
Analyze
     ↓
Identify Problem
     ↓
Improve Process
     ↓
Measure Again
```

---

## 📚 Table of Contents

- [1. What are DevOps Metrics?](#1-what-are-devops-metrics)
- [2. Why DevOps Metrics Matter](#2-why-devops-metrics-matter)
- [3. Metrics Across the DevOps Lifecycle](#3-metrics-across-the-devops-lifecycle)
- [4. Project Planning Metrics](#4-project-planning-metrics)
- [5. Development Metrics](#5-development-metrics)
- [6. Testing Metrics](#6-testing-metrics)
- [7. Security Metrics](#7-security-metrics)
- [8. Delivery Metrics](#8-delivery-metrics)
- [9. Operations Metrics](#9-operations-metrics)
- [10. Lead Time](#10-lead-time)
- [11. Cycle Time](#11-cycle-time)
- [12. Time to Recovery](#12-time-to-recovery)
- [13. Deployment Frequency](#13-deployment-frequency)
- [14. Change Failure Rate](#14-change-failure-rate)
- [15. Work Item Metrics](#15-work-item-metrics)
- [16. Build Metrics](#16-build-metrics)
- [17. Test Metrics](#17-test-metrics)
- [18. Security Metrics](#18-security-metrics)
- [19. Deployment Metrics](#19-deployment-metrics)
- [20. Operational Metrics](#20-operational-metrics)
- [21. Queries](#21-queries)
- [22. Dashboards](#22-dashboards)
- [23. DevOps Dashboard Design](#23-devops-dashboard-design)
- [24. Metrics and Bottleneck Identification](#24-metrics-and-bottleneck-identification)
- [25. Metrics Example](#25-metrics-example)
- [26. Metrics Best Practices](#26-metrics-best-practices)
- [27. Hands-On Lab](#27-hands-on-lab)
- [28. AZ-400 Exam Focus](#28-az-400-exam-focus)
- [29. Summary](#29-summary)

---

# 1. What are DevOps Metrics?

A **metric** is a measurable value that provides information about a process, system, or outcome.

Examples:

```text
Build Duration
Deployment Frequency
Cycle Time
Lead Time
Test Pass Rate
Code Coverage
Failure Rate
Recovery Time
```

For example:

```text
Average Build Duration = 8 minutes
```

This tells the team how long builds typically take.

Another example:

```text
Deployment Frequency = 12 deployments/week
```

This indicates how frequently changes are being delivered.

---

# 2. Why DevOps Metrics Matter

Without metrics, teams may rely on assumptions.

```text
"We are delivering quickly."
"We have very few failures."
"Testing is working well."
"Deployments are reliable."
```

Metrics provide evidence.

```text
Assumption
    ↓
Collect Data
    ↓
Metric
    ↓
Analysis
    ↓
Decision
```

For example:

```text
Team believes deployments are slow
             ↓
Measure deployment duration
             ↓
Average = 42 minutes
             ↓
Identify bottleneck
             ↓
Optimize pipeline
             ↓
Average = 18 minutes
```

Metrics therefore support continuous improvement.

---

# 3. Metrics Across the DevOps Lifecycle

Metrics should cover the complete DevOps lifecycle.

```text
Planning
   ↓
Development
   ↓
Testing
   ↓
Security
   ↓
Delivery
   ↓
Operations
```

Each stage can have different measurements.

| Area | Example Metrics |
|---|---|
| Planning | Backlog size, work-item age, completion rate |
| Development | PR duration, commit activity, review time |
| Testing | Test pass rate, failed tests, coverage |
| Security | Vulnerabilities, remediation time, scan results |
| Delivery | Deployment frequency, deployment duration |
| Operations | Availability, incidents, recovery time |

A mature DevOps dashboard should provide a balanced view instead of focusing on only one stage.

---

# 4. Project Planning Metrics

Planning metrics help teams understand how effectively planned work is being managed.

Examples include:

- Backlog size
- Work-item count
- Work-item age
- Work completion rate
- Planned vs completed work
- Blocked work
- Priority distribution
- Sprint progress
- Remaining work

Example:

```text
Sprint
│
├── Completed     20
├── In Progress    5
├── Blocked        2
└── Not Started    3
```

This allows teams to identify whether work is progressing as expected.

---

## Work Aging

Work-item age measures how long work has remained in a particular state.

Example:

```text
Bug #101
Age: 2 days

Bug #102
Age: 14 days

Bug #103
Age: 45 days
```

A large number of old work items may indicate:

- Prioritization problems
- Ownership problems
- Dependencies
- Technical complexity
- Insufficient capacity

---

# 5. Development Metrics

Development metrics help teams understand the efficiency and quality of software development.

Examples include:

- Pull Request count
- Pull Request review time
- Pull Request completion time
- Commit frequency
- Review turnaround time
- Failed builds
- Rework
- Defect introduction

For example:

```text
PR Created
    ↓
Review Requested
    ↓
Review Started
    ↓
Changes Requested
    ↓
Approved
    ↓
Merged
```

The time spent between these stages can reveal development bottlenecks.

---

# 6. Testing Metrics

Testing metrics help determine whether the application is being validated effectively.

Examples include:

- Test pass rate
- Test failure rate
- Test execution duration
- Code coverage
- Number of automated tests
- Flaky test rate
- Defect detection rate
- Regression test results

Example:

```text
Test Run

Total Tests: 500
Passed:      480
Failed:       15
Skipped:       5
```

Test pass rate:

```text
Passed Tests
──────────── × 100
Total Tests
```

In this example:

```text
480 / 500 × 100 = 96%
```

The metric alone does not explain why tests failed, so teams should combine metrics with test results and investigation.

---

# 7. Security Metrics

Security metrics help teams understand the security posture of the development and delivery process.

Examples include:

- Vulnerability count
- Critical vulnerability count
- Dependency vulnerabilities
- Secret detection findings
- Code scanning findings
- Time to remediate vulnerabilities
- Security scan success/failure
- Open security findings

Example:

```text
Security Findings

Critical    1
High        4
Medium     12
Low         8
```

A useful security measurement can track how quickly findings are resolved.

```text
Vulnerability Detected
        ↓
Assigned
        ↓
Fixed
        ↓
Validated
```

This can be used to measure remediation time.

---

# 8. Delivery Metrics

Delivery metrics measure how efficiently software moves toward users and production.

Examples include:

- Deployment frequency
- Deployment duration
- Lead time
- Release success rate
- Change failure rate
- Deployment rollback rate
- Release duration

A delivery pipeline may look like:

```text
Commit
  ↓
Build
  ↓
Test
  ↓
Artifact
  ↓
Deploy
```

Metrics can be collected at each stage.

---

# 9. Operations Metrics

Operations metrics describe the behavior and reliability of applications and infrastructure after deployment.

Examples include:

- Availability
- Error rate
- Request rate
- Response time
- CPU utilization
- Memory utilization
- Disk utilization
- Network utilization
- Incident count
- Recovery time

For example:

```text
Application
    ↓
Telemetry
    ↓
Monitoring
    ↓
Metric
    ↓
Alert
```

Operations metrics are especially important because they show what is happening in the real environment.

---

# 10. Lead Time

**Lead time** measures the time from the beginning of a work request or change until the desired delivery point.

A simplified software delivery example is:

```text
Work Requested
      ↓
Development
      ↓
Testing
      ↓
Deployment
```

The elapsed time across this process can be used as a lead-time measurement.

For example:

```text
Requirement Created:
Monday 9:00 AM

Production Deployment:
Wednesday 3:00 PM

Lead Time:
54 hours
```

Lead time helps teams understand how long it takes for requested work to become delivered value.

---

# 11. Cycle Time

**Cycle time** measures how long work takes once active work begins.

For example:

```text
Work Starts
     ↓
Development
     ↓
Testing
     ↓
Completed
```

Example:

```text
Work Started:
Monday 10:00 AM

Work Completed:
Tuesday 4:00 PM

Cycle Time:
30 hours
```

The distinction can be represented as:

```text
              Lead Time
<-------------------------------------->

Requested                              Delivered
     │                                      │
     ├──────── Waiting ────────┐            │
     │                         ↓            │
     │                     Work Starts      │
     │                         │            │
     │<------ Cycle Time ------>│            │
     │                         │            │
     └─────────────────────────┴────────────┘
```

The exact definitions used by a team should remain consistent when reporting metrics.

---

# 12. Time to Recovery

**Time to recovery** measures how long it takes to restore service after a failure or incident.

A simplified flow is:

```text
Incident
   ↓
Detection
   ↓
Investigation
   ↓
Fix / Rollback
   ↓
Service Restored
```

Example:

```text
Incident Detected:
10:00 AM

Service Restored:
10:45 AM

Time to Recovery:
45 minutes
```

A lower recovery time generally indicates that teams can restore service more quickly.

---

# 13. Deployment Frequency

**Deployment frequency** measures how frequently software changes are deployed.

Example:

```text
Monday       → 3 deployments
Tuesday      → 2 deployments
Wednesday    → 4 deployments
Thursday     → 1 deployment
Friday       → 3 deployments
```

Total:

```text
13 deployments/week
```

Deployment frequency helps teams understand delivery cadence.

However, frequency should not be optimized by itself.

For example:

```text
More Deployments
       ≠
Automatically Better
```

Teams should consider deployment frequency together with reliability and quality.

---

# 14. Change Failure Rate

**Change failure rate** measures the proportion of changes that result in failures requiring remediation, rollback, or other corrective action.

Example:

```text
Total Deployments: 100
Failed Deployments: 5
```

Conceptually:

```text
Change Failure Rate
=
Failed Changes
──────────────── × 100
Total Changes
```

Example:

```text
5 / 100 × 100
=
5%
```

A high failure rate may indicate problems with:

- Testing
- Deployment automation
- Configuration
- Infrastructure
- Release processes
- Application quality

This metric should be interpreted in the context of how the organization defines a failed change.

---

# 15. Work Item Metrics

Work-item data can provide useful information about planning and delivery.

Examples:

```text
Total Work Items
Completed Work Items
Open Work Items
Blocked Work Items
Average Work-Item Age
```

Example dashboard:

```text
Work Items

Open:       42
In Progress: 15
Blocked:      4
Completed:   87
```

Teams can create queries to retrieve specific subsets of work.

For example:

```text
All open bugs
```

or:

```text
All high-priority work assigned to Team A
```

These queries can then support dashboards and reports.

---

# 16. Build Metrics

Build metrics help teams understand pipeline performance.

Examples include:

- Build success rate
- Build failure rate
- Build duration
- Queue time
- Build frequency
- Failed builds by branch
- Failed builds by pipeline
- Flaky build patterns

Example:

```text
Build #101 → PASS → 8 min
Build #102 → PASS → 7 min
Build #103 → FAIL → 11 min
Build #104 → PASS → 8 min
```

If build duration continuously increases:

```text
8 min
 ↓
10 min
 ↓
14 min
 ↓
21 min
```

the team should investigate the cause.

---

# 17. Test Metrics

Testing metrics provide insight into validation quality.

Important examples include:

```text
Test Pass Rate
Test Failure Rate
Test Duration
Code Coverage
Flaky Tests
Regression Failures
```

A test dashboard could show:

```text
Test Execution

Tests:       1,000
Passed:        950
Failed:         35
Skipped:        15

Coverage:
82%
```

Teams should avoid treating code coverage as the only measure of test quality.

High coverage does not automatically mean that the application is well tested.

---

# 18. Security Metrics

Security dashboards can provide visibility into the state of security validation.

Example:

```text
Security Dashboard

Critical Findings:     0
High Findings:          3
Medium Findings:       10
Secrets Detected:       0
Dependency Alerts:      4
```

Teams can also track:

```text
Finding Detected
      ↓
Assigned
      ↓
Remediated
      ↓
Validated
```

The time between detection and remediation can be measured.

---

# 19. Deployment Metrics

Deployment metrics help teams understand release performance.

Examples:

- Deployment frequency
- Deployment duration
- Deployment success rate
- Deployment failure rate
- Rollback count
- Environment deployment time
- Approval waiting time

Example:

```text
Deployment #500

Build:       PASS
Tests:       PASS
Approval:    PASS
Deployment:  PASS
Duration:    12 min
```

If deployments repeatedly fail in the same stage:

```text
Deployment
    ↓
Stage 1 → PASS
    ↓
Stage 2 → PASS
    ↓
Stage 3 → FAIL
    ↓
Stage 3 → FAIL
    ↓
Stage 3 → FAIL
```

the team has identified a potential bottleneck.

---

# 20. Operational Metrics

Operational metrics provide visibility into the behavior of deployed systems.

Common examples:

| Metric | What It Shows |
|---|---|
| Availability | Whether the service is available |
| CPU | Processor utilization |
| Memory | Memory utilization |
| Disk | Storage utilization |
| Network | Network activity |
| Error Rate | Frequency of errors |
| Response Time | Application responsiveness |
| Request Rate | Traffic volume |
| Incident Count | Operational failures |
| Recovery Time | Time required to restore service |

Example:

```text
Application Performance

Requests/minute:  4,500
Error Rate:          0.8%
Average Response:   180 ms
Availability:      99.95%
```

These metrics help teams understand real-world application behavior.

---

# 21. Queries

A **query** retrieves specific information from a data source based on defined conditions.

For example, a work-item query could identify:

```text
All active bugs
```

A more specific query could identify:

```text
Active bugs
AND
Priority = High
AND
Assigned To = Team A
```

Conceptually:

```text
Data
 ↓
Query Conditions
 ↓
Filtered Results
 ↓
Metric / Dashboard
```

Queries are useful because raw data can be difficult to interpret.

---

## Query Example

Suppose a team has:

```text
100 Work Items
```

A query can return:

```text
State = Active
```

Result:

```text
32 Work Items
```

Another query:

```text
State = Active
AND
Priority = High
```

Result:

```text
8 Work Items
```

The query provides a focused view of the data.

---

# 22. Dashboards

A **dashboard** presents important information visually.

Instead of checking multiple systems individually:

```text
Work Items
Builds
Tests
Security
Deployments
Operations
```

a dashboard can provide a consolidated view.

Example:

```text
┌──────────────────────────────────────────┐
│          DEVOPS DASHBOARD                │
├──────────────────────────────────────────┤
│ Work Items       │ Build Success         │
│ Open: 42         │ 96%                   │
├──────────────────┼───────────────────────┤
│ Test Pass Rate   │ Deployment Frequency   │
│ 97%              │ 14 / week             │
├──────────────────┼───────────────────────┤
│ Cycle Time       │ Time to Recovery      │
│ 2.4 days         │ 38 min                │
├──────────────────┼───────────────────────┤
│ Security         │ Availability           │
│ High: 3          │ 99.95%                │
└──────────────────────────────────────────┘
```

A dashboard should help people understand the state of delivery quickly.

---

# 23. DevOps Dashboard Design

A useful dashboard should answer important questions rather than display every available metric.

A good structure can be:

```text
                 DevOps Dashboard
                        │
        ┌───────────────┼───────────────┐
        ↓               ↓               ↓
      Work            Delivery        Quality
        │               │               │
        ↓               ↓               ↓
    Planning         Pipelines         Tests
    Backlog          Deployments       Security
        │               │               │
        └───────────────┼───────────────┘
                        ↓
                    Operations
                        │
                        ↓
                  Reliability
```

---

## Dashboard Audience

Different users may need different views.

| Audience | Useful Information |
|---|---|
| Developer | Builds, tests, PRs |
| QA Team | Test results, failures, coverage |
| Security Team | Vulnerabilities, security findings |
| DevOps Team | Pipelines, deployments, incidents |
| Engineering Manager | Delivery trends, bottlenecks |
| Product Team | Work progress, lead time |
| Leadership | Delivery, quality, reliability |

A dashboard should be designed around the decisions the audience needs to make.

---

# 24. Metrics and Bottleneck Identification

One of the most useful purposes of metrics is finding bottlenecks.

Consider:

```text
Planning
  ↓
Development
  ↓
Code Review
  ↓
Testing
  ↓
Deployment
```

Suppose measurements show:

```text
Planning       → 1 day
Development    → 2 days
Code Review    → 4 days
Testing        → 1 day
Deployment     → 30 min
```

The obvious bottleneck is:

```text
Code Review
     ↓
4 days
```

The team can then investigate:

- Too few reviewers
- Large Pull Requests
- Unclear ownership
- Review process problems
- Complex changes

After improvement:

```text
Code Review
4 days
  ↓
1 day
```

Metrics have therefore helped identify and improve the bottleneck.

---

# 25. Metrics Example

Consider a team delivering an online shopping application.

During one month, the team measures:

```text
Average Lead Time:       5 days
Average Cycle Time:      3 days
Deployment Frequency:    12/week
Change Failure Rate:     8%
Average Recovery Time:   60 minutes
```

The team notices:

```text
Lead Time
   ↓
5 days
```

but:

```text
Cycle Time
   ↓
3 days
```

This indicates that some time exists outside active implementation.

The team investigates and discovers:

```text
Waiting for Review
        ↓
Waiting for Security Approval
        ↓
Waiting for Deployment Window
```

They improve the process:

```text
Automated Security Checks
          ↓
Faster Reviews
          ↓
Automated Deployment
```

After improvement:

```text
Lead Time:          5 days → 2.5 days
Cycle Time:         3 days → 1.8 days
Recovery Time:     60 min → 25 min
```

Metrics have provided evidence that the process improved.

---

# 26. Metrics Best Practices

## 1. Measure What Matters

Do not collect metrics simply because they are available.

Measure metrics that help answer meaningful questions.

---

## 2. Use Multiple Metrics

Avoid relying on a single number.

For example:

```text
Deployment Frequency
        +
Change Failure Rate
        +
Recovery Time
```

provides more information than deployment frequency alone.

---

## 3. Measure Trends

A single measurement may not tell the complete story.

Compare:

```text
This Week
Last Week
This Month
Previous Month
```

---

## 4. Establish a Baseline

Before improving a process, understand its current state.

```text
Current:
Build = 20 min

Target:
Build = 10 min
```

---

## 5. Avoid Vanity Metrics

A metric should help with a decision.

Poor example:

```text
Number of commits
```

when used without context.

Better:

```text
Build failure rate
```

when the team wants to understand pipeline reliability.

---

## 6. Combine Speed and Quality

Fast delivery is not useful if reliability is poor.

```text
Speed
 +
Quality
 +
Reliability
```

should be considered together.

---

## 7. Make Metrics Visible

Use dashboards so teams can easily understand important trends.

---

## 8. Investigate Significant Changes

If a metric suddenly changes:

```text
Cycle Time
2 days
 ↓
7 days
```

investigate why.

---

## 9. Use Metrics for Improvement

Metrics should support learning and improvement rather than blame.

---

## 10. Keep Definitions Consistent

If a team changes how it calculates a metric, historical comparisons may become misleading.

Document the definitions used by the organization.

---

# 27. Hands-On Lab

## 🎯 Objective

Create a basic Azure DevOps metrics and dashboard workflow using work items, queries, pipeline results, and delivery information.

### Lab Flow

```text
Create Work
     ↓
Collect Data
     ↓
Create Queries
     ↓
Analyze Metrics
     ↓
Create Dashboard
     ↓
Identify Bottleneck
     ↓
Improve
     ↓
Measure Again
```

---

## Step 1 — Create Work Items

Create several work items in Azure Boards.

Example:

```text
Feature: Payment Integration
Bug: Payment Timeout
Task: Add Payment Tests
Task: Update Documentation
Bug: Invalid Payment Response
```

Use different priorities and states.

---

## Step 2 — Create a Query

Create a query for active work.

Example:

```text
State = Active
```

Then create another query:

```text
Work Item Type = Bug
AND
State = Active
```

Finally:

```text
Work Item Type = Bug
AND
State = Active
AND
Priority = High
```

Compare the results.

---

## Step 3 — Create a Pipeline

Use an existing CI pipeline or create a basic pipeline.

The pipeline should perform:

```text
Checkout
   ↓
Build
   ↓
Test
   ↓
Publish Result
```

Record:

- Build duration
- Build result
- Test result

---

## Step 4 — Collect Test Metrics

Record the test results.

Example:

```text
Total Tests: 100
Passed:       96
Failed:        4
```

Calculate:

```text
Pass Rate = 96%
```

---

## Step 5 — Track Deployment

Run a deployment to a test environment.

Record:

```text
Deployment Number
Duration
Result
Environment
```

Example:

```text
Deployment #25
Duration: 14 minutes
Result: SUCCESS
Environment: Test
```

---

## Step 6 — Create a Dashboard

Create a dashboard containing useful information such as:

```text
Open Work Items
Active Bugs
Build Results
Test Results
Deployment Results
```

Where available, add delivery-oriented metrics such as:

```text
Cycle Time
Lead Time
Recovery Time
```

---

## Step 7 — Identify a Bottleneck

Analyze your collected information.

For example:

```text
Build:
10 minutes

Testing:
15 minutes

Deployment:
12 minutes

Approval:
45 minutes
```

The likely bottleneck is:

```text
Approval
   ↓
45 minutes
```

Investigate whether the process can be improved.

---

## Step 8 — Measure Again

After making an improvement, compare the new result.

Example:

```text
Before:
Approval = 45 minutes

After:
Approval = 15 minutes
```

Record the improvement.

---

# 28. AZ-400 Exam Focus

For the current AZ-400 exam, understand how to implement **metrics and queries** across:

- Project planning
- Development
- Testing
- Security
- Delivery
- Operations

You should also understand dashboard-oriented measurements such as:

- Cycle time
- Lead time
- Time to recovery

### Important Concepts

```text
Data
 ↓
Query
 ↓
Metric
 ↓
Dashboard
 ↓
Analysis
 ↓
Improvement
```

### Know the Difference

| Metric | Focus |
|---|---|
| Lead Time | Overall elapsed time from request/change initiation to delivery |
| Cycle Time | Time spent actively processing work |
| Time to Recovery | Time required to restore service after failure |
| Deployment Frequency | How often deployments occur |
| Change Failure Rate | How frequently changes result in failures |
| Test Pass Rate | Proportion of tests passing |
| Build Duration | Time required to complete a build |

---

## Scenario Thinking

If a question asks:

> A team wants to determine where work is spending the most time.

Think:

```text
Planning
   ↓
Development
   ↓
Review
   ↓
Testing
   ↓
Deployment
```

Measure the duration of each stage and identify the bottleneck.

---

If a question asks:

> A team wants to know how long it takes to restore an application after a production incident.

Think:

```text
Incident
   ↓
Detection
   ↓
Recovery
   ↓
Service Restored
```

Measure:

```text
Time to Recovery
```

---

If a question asks:

> A team wants to identify all high-priority active bugs.

Think:

```text
Work Item Query
     ↓
Type = Bug
     ↓
State = Active
     ↓
Priority = High
```

---

If a question asks:

> Management needs a single view of important DevOps information.

Think:

```text
Queries
   ↓
Metrics
   ↓
Dashboard
```

---

## Key Exam Principle

Remember:

> **Metrics tell you what is happening, queries help you retrieve the relevant data, and dashboards help you visualize and analyze it.**

The complete cycle is:

```text
Collect
  ↓
Query
  ↓
Measure
  ↓
Visualize
  ↓
Analyze
  ↓
Improve
```

---

# 29. Summary

**DevOps metrics** provide measurable information about planning, development, testing, security, delivery, and operations.

The overall measurement cycle is:

```text
Collect Data
     ↓
Create Queries
     ↓
Build Metrics
     ↓
Create Dashboard
     ↓
Analyze
     ↓
Identify Bottleneck
     ↓
Improve
     ↓
Measure Again
```

The key concepts introduced in this section are:

- **Project Planning Metrics** measure backlog and work-management performance.
- **Development Metrics** measure development and review activity.
- **Testing Metrics** measure test execution and quality.
- **Security Metrics** measure vulnerabilities and remediation.
- **Delivery Metrics** measure software delivery performance.
- **Operations Metrics** measure production reliability and behavior.
- **Lead Time** measures elapsed time from the beginning of a request/change through delivery.
- **Cycle Time** measures the time spent actively processing work.
- **Time to Recovery** measures how quickly service is restored after failure.
- **Deployment Frequency** measures how frequently changes are deployed.
- **Change Failure Rate** measures how frequently changes result in failures.
- **Queries** retrieve focused information from work and delivery data.
- **Dashboards** provide a visual representation of important DevOps information.
- **Bottleneck Analysis** uses metrics to identify where work is slowing down.
- **Continuous Measurement** allows teams to verify whether improvements actually work.

The most important sequence to remember is:

> **Collect → Query → Measure → Visualize → Analyze → Improve**

---

