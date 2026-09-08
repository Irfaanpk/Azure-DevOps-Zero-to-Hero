# Work Tracking

## Introduction

**Work tracking** is the process of capturing, organizing, assigning, prioritizing, and monitoring the work required to deliver software.

In a DevOps environment, work can include:

- Features
- User stories
- Bugs
- Tasks
- Improvements
- Technical work
- Security work
- Testing activities
- Operational work

The goal of work tracking is to make it clear:

```text
What needs to be done?
        ↓
Who is responsible?
        ↓
What is the priority?
        ↓
What is the current status?
        ↓
What is blocking the work?
        ↓
When will it be completed?
```

For the current **AZ-400** exam, Microsoft specifically includes designing and implementing integration for tracking work using **GitHub Projects, Azure Boards, and repositories**. :contentReference[oaicite:0]{index=0}

This section focuses specifically on **work tracking**, while feedback cycles, traceability, and DevOps metrics are covered separately.

---

## 📚 Table of Contents

- [1. What is Work Tracking?](#1-what-is-work-tracking)
- [2. Why Work Tracking Matters](#2-why-work-tracking-matters)
- [3. Work Tracking Lifecycle](#3-work-tracking-lifecycle)
- [4. Work Items](#4-work-items)
- [5. Common Types of Work](#5-common-types-of-work)
- [6. Work Item States](#6-work-item-states)
- [7. Prioritization](#7-prioritization)
- [8. Ownership and Assignment](#8-ownership-and-assignment)
- [9. Backlogs](#9-backlogs)
- [10. Sprints and Iterations](#10-sprints-and-iterations)
- [11. Azure Boards](#11-azure-boards)
- [12. Azure Boards Components](#12-azure-boards-components)
- [13. GitHub Projects](#13-github-projects)
- [14. GitHub Project Views](#14-github-project-views)
- [15. Azure Boards vs GitHub Projects](#15-azure-boards-vs-github-projects)
- [16. Work Tracking with Repositories](#16-work-tracking-with-repositories)
- [17. Linking Work to Code](#17-linking-work-to-code)
- [18. Azure Boards and GitHub Integration](#18-azure-boards-and-github-integration)
- [19. Work Tracking Across Teams](#19-work-tracking-across-teams)
- [20. Work Tracking Example](#20-work-tracking-example)
- [21. Work Tracking Best Practices](#21-work-tracking-best-practices)
- [22. Hands-On Lab](#22-hands-on-lab)
- [23. AZ-400 Exam Focus](#23-az-400-exam-focus)
- [24. Summary](#24-summary)

---

# 1. What is Work Tracking?

Work tracking is the practice of recording and managing work throughout its lifecycle.

Instead of keeping work in:

```text
Email
Excel
Chat Messages
Personal Notes
```

teams can use a centralized work-tracking system.

For example:

```text
Feature Request
      ↓
Work Item
      ↓
Assigned
      ↓
In Progress
      ↓
Development
      ↓
Testing
      ↓
Completed
```

A work-tracking system provides visibility into the current state of work.

---

# 2. Why Work Tracking Matters

Without centralized work tracking, teams may lose visibility.

```text
Developer A
   ↓
Personal Notes

Developer B
   ↓
Spreadsheet

Tester
   ↓
Email

Manager
   ↓
Chat
```

It becomes difficult to determine:

- What work is pending?
- Who owns it?
- What is completed?
- What is blocked?
- What should be done next?

With centralized tracking:

```text
                 Work Tracking
                      │
       ┌──────────────┼──────────────┐
       ↓              ↓              ↓
    Planning      Development      Testing
       │              │              │
       └──────────────┼──────────────┘
                      ↓
                   Delivery
```

Benefits include:

- Centralized visibility
- Clear ownership
- Prioritization
- Better planning
- Easier collaboration
- Better status visibility
- Reduced duplicate work
- Better connection between requirements and implementation

---

# 3. Work Tracking Lifecycle

A typical work-tracking lifecycle is:

```text
Requirement
    ↓
Create Work Item
    ↓
Prioritize
    ↓
Assign
    ↓
Plan
    ↓
Develop
    ↓
Test
    ↓
Complete
```

For example:

```text
Feature Request
      ↓
User Story
      ↓
Task
      ↓
Development
      ↓
Pull Request
      ↓
Testing
      ↓
Done
```

Work tracking therefore provides the planning layer around the actual engineering work.

---

# 4. Work Items

A **work item** is a trackable representation of a piece of work.

A work item normally contains information such as:

```text
Title
Description
Owner
Priority
Status
Tags
Iteration
Attachments
Comments
Links
```

Example:

```text
Title:
Add MFA login support

Description:
Implement multi-factor authentication
for application users.

Assigned To:
Developer A

Priority:
High

State:
In Progress
```

The exact fields depend on the work-tracking platform and process configuration.

---

# 5. Common Types of Work

Different types of work should be represented appropriately.

| Work Type | Example |
|---|---|
| Epic | E-commerce platform modernization |
| Feature | Payment processing |
| User Story | User can pay using a credit card |
| Task | Implement payment API |
| Bug | Payment fails for expired cards |
| Issue | Production checkout problem |
| Improvement | Improve API performance |
| Security Work | Fix dependency vulnerability |
| Technical Work | Upgrade application framework |

The hierarchy can be represented as:

```text
Epic
 │
 ├── Feature
 │      │
 │      ├── User Story
 │      │       │
 │      │       ├── Task
 │      │       └── Task
 │      │
 │      └── User Story
 │
 └── Feature
```

The exact hierarchy differs between tools and configured processes.

---

# 6. Work Item States

A work item moves through different states during its lifecycle.

A simple workflow is:

```text
New
 ↓
Active
 ↓
In Progress
 ↓
Testing
 ↓
Done
```

For example:

```text
New
 ↓
Assigned
 ↓
Development
 ↓
Code Review
 ↓
Testing
 ↓
Completed
```

A blocked work item may follow another path:

```text
In Progress
     ↓
   Blocked
     ↓
Dependency Resolved
     ↓
In Progress
```

The objective is to make the current state visible to the team.

---

# 7. Prioritization

Not all work has the same importance.

Teams should prioritize work based on factors such as:

- Business value
- Customer impact
- Security risk
- Production impact
- Dependencies
- Urgency
- Technical risk

Example:

| Priority | Example |
|---|---|
| Critical | Production outage |
| High | Security vulnerability |
| Medium | Important feature |
| Low | Documentation improvement |

A simple prioritization flow:

```text
All Work
   ↓
Evaluate
   ↓
Prioritize
   ↓
Order Backlog
   ↓
Select Work
```

Prioritization helps teams focus their limited capacity on the most valuable work.

---

# 8. Ownership and Assignment

Every important work item should have clear ownership.

Example:

```text
Work Item
    ↓
Assigned To
    ↓
Responsible Person
    ↓
Progress
    ↓
Completion
```

Without ownership:

```text
Bug
 ↓
Nobody Assigned
 ↓
Delayed
```

With ownership:

```text
Bug
 ↓
Developer Assigned
 ↓
Investigate
 ↓
Fix
 ↓
Test
 ↓
Complete
```

Ownership does not necessarily mean one person performs every activity. It means the responsibility for progressing the work is clear.

---

# 9. Backlogs

A **backlog** is an ordered collection of work that may need to be completed.

For example:

```text
Product Backlog
│
├── Feature A
├── Feature B
├── Bug C
├── User Story D
└── Technical Task E
```

The backlog can be prioritized:

```text
1. Production Security Fix
2. Payment Feature
3. Login Improvement
4. Dashboard Enhancement
5. Documentation
```

Teams can continuously refine the backlog as requirements and priorities change.

---

# 10. Sprints and Iterations

Teams using iterative development can organize work into **sprints** or **iterations**.

Example:

```text
Product Backlog
      ↓
Sprint Planning
      ↓
Sprint 1
      ↓
Development
      ↓
Testing
      ↓
Sprint Review
      ↓
Completed Work
```

For example:

```text
Sprint 1
│
├── Login Feature
├── Payment API
├── Unit Tests
└── Bug Fix #25
```

A future sprint might contain:

```text
Sprint 2
│
├── Reporting
├── Notifications
└── Performance Improvements
```

Iterations help teams organize work into manageable time periods.

---

# 11. Azure Boards

**Azure Boards** is the work-tracking service within Azure DevOps.

It provides capabilities for:

- Work items
- Backlogs
- Boards
- Sprints
- Queries
- Dashboards
- Planning
- Team collaboration
- Work-item relationships

Microsoft's current AZ-400 learning content specifically covers **Azure Boards**, GitHub Projects, project/team configuration, and integration between Azure Boards and GitHub. :contentReference[oaicite:1]{index=1}

A simplified Azure Boards workflow is:

```text
Requirement
    ↓
Azure Boards
    ↓
Backlog
    ↓
Sprint
    ↓
Work Item
    ↓
Development
    ↓
Completion
```

---

# 12. Azure Boards Components

Azure Boards provides several important work-management capabilities.

## 12.1 Boards

Boards provide a visual representation of work.

Example:

```text
┌────────────┐
│   To Do    │
├────────────┤
│ Payment    │
│ Login      │
└────────────┘

┌────────────┐
│ In Progress│
├────────────┤
│ API Update │
└────────────┘

┌────────────┐
│    Done    │
├────────────┤
│ Bug #25    │
└────────────┘
```

---

## 12.2 Backlogs

Backlogs provide an ordered list of planned work.

```text
Backlog
│
├── Feature 1
├── User Story 2
├── Bug 3
└── Task 4
```

---

## 12.3 Sprints

Sprints organize selected backlog items into an iteration.

```text
Backlog
   ↓
Sprint Planning
   ↓
Sprint
   ↓
Work
```

---

## 12.4 Queries

Queries allow teams to find work items that match specific conditions.

For example:

```text
Find:
All active bugs
```

Or:

```text
Find:
High-priority work
assigned to Developer A
```

Queries become useful when repositories contain a large number of work items.

---

# 13. GitHub Projects

**GitHub Projects** provides project and work-management capabilities directly within the GitHub ecosystem.

It can be used to organize:

- Issues
- Pull Requests
- Planning items
- Development work
- Team tasks

A simplified workflow is:

```text
GitHub Issue
      ↓
GitHub Project
      ↓
Planning
      ↓
Development
      ↓
Pull Request
      ↓
Completed
```

GitHub Projects can therefore connect planning with the repository and development workflow.

---

# 14. GitHub Project Views

GitHub Projects can present work in different views depending on how a team wants to manage it.

Common approaches include:

### Table View

```text
| Title | Status | Priority | Owner |
|-------|--------|----------|-------|
| Login | Todo   | High     | Alex  |
| API   | Doing  | Medium   | Sam   |
| Docs  | Done   | Low      | John  |
```

### Board View

```text
┌──────────┐  ┌────────────┐  ┌──────────┐
│   Todo   │  │ In Progress│  │   Done   │
├──────────┤  ├────────────┤  ├──────────┤
│ Login    │  │ Payment API│  │ Docs     │
│ Reports  │  │ MFA        │  │ Bug #25  │
└──────────┘  └────────────┘  └──────────┘
```

Different views allow teams to look at the same work from different perspectives.

---

# 15. Azure Boards vs GitHub Projects

Both can be used for work tracking, but they fit different environments.

| Capability | Azure Boards | GitHub Projects |
|---|---|---|
| Platform | Azure DevOps | GitHub |
| Work Tracking | Yes | Yes |
| Backlogs | Yes | Project-based planning |
| Boards | Yes | Yes |
| Sprints | Strong support | Can organize project work |
| GitHub Integration | Yes | Native |
| Azure DevOps Integration | Native | Integration available |
| Repository Integration | Azure Repos / GitHub | GitHub repositories |
| Best Fit | Azure DevOps-centric teams | GitHub-centric teams |

The choice depends on the team's existing platform, workflow, governance requirements, and integration needs.

---

# 16. Work Tracking with Repositories

Work tracking becomes more valuable when it is connected to source control.

Instead of having:

```text
Work Tracking
      ↓
Separate System

Source Code
      ↓
Separate System
```

teams can connect them:

```text
Work Item
    ↓
Branch
    ↓
Commit
    ↓
Pull Request
    ↓
Code
```

This allows teams to understand how planned work becomes actual implementation.

---

# 17. Linking Work to Code

A common workflow is:

```text
Work Item
    ↓
Developer Creates Branch
    ↓
Commit
    ↓
Pull Request
    ↓
Review
    ↓
Merge
```

For example:

```text
Work Item #245
"Add MFA support"

        ↓

Branch:
feature/mfa

        ↓

Commit:
Add MFA authentication

        ↓

Pull Request:
Add MFA authentication

        ↓

Merge
```

The connection between work and source code makes the development process easier to understand.

---

# 18. Azure Boards and GitHub Integration

Azure Boards can be connected to GitHub repositories.

Microsoft documents that Azure Boards can connect to GitHub repositories so that commits and Pull Requests can automatically link to Azure Boards work items. :contentReference[oaicite:2]{index=2}

A simplified architecture is:

```text
                 Azure Boards
                     │
                     │
                Work Item
                     │
                     ↓
                 GitHub Repo
                     │
          ┌──────────┼──────────┐
          ↓          ↓          ↓
       Branch      Commit       PR
          │          │          │
          └──────────┼──────────┘
                     ↓
                Completed Work
```

This allows a team to use:

```text
Azure Boards
     +
GitHub
```

instead of treating planning and development as completely separate systems.

---

# 19. Work Tracking Across Teams

Large organizations may have multiple teams working on the same product.

For example:

```text
                    Product
                       │
        ┌──────────────┼──────────────┐
        ↓              ↓              ↓
    Frontend        Backend        Platform
        │              │              │
      Work           Work           Work
        │              │              │
        └──────────────┼──────────────┘
                       ↓
                    Release
```

Each team can manage its own work while maintaining visibility into the larger product.

Example:

```text
Product
│
├── Authentication
│
├── Payments
│
├── Platform
│
└── Monitoring
```

Cross-team dependencies should be visible so that one team's blocked work does not remain hidden.

---

# 20. Work Tracking Example

Consider an online shopping application.

The product team wants to add a new payment method.

### Step 1 — Requirement

```text
Customer should be able to
pay using a new payment provider.
```

### Step 2 — Create Work

```text
Feature:
New Payment Provider
```

### Step 3 — Break Down Work

```text
Feature
│
├── Payment API
├── Frontend Integration
├── Unit Tests
├── Integration Tests
└── Documentation
```

### Step 4 — Prioritize

```text
Payment API        → High
Frontend           → High
Integration Tests  → High
Documentation      → Medium
```

### Step 5 — Assign

```text
Payment API       → Backend Team
Frontend          → Frontend Team
Testing           → QA Team
Documentation     → Technical Writer
```

### Step 6 — Track Progress

```text
To Do
 ↓
In Progress
 ↓
Code Review
 ↓
Testing
 ↓
Done
```

### Step 7 — Connect Development

```text
Work Item
   ↓
GitHub Branch
   ↓
Commit
   ↓
Pull Request
   ↓
Validation
   ↓
Merge
```

The complete work item can therefore represent the journey from requirement to implementation.

---

# 21. Work Tracking Best Practices

## 1. Keep Work Centralized

Use an agreed work-tracking system instead of scattered personal notes.

---

## 2. Use Clear Work Items

A work item should describe what needs to be accomplished.

Poor:

```text
Fix stuff
```

Better:

```text
Fix payment timeout when processing
international transactions
```

---

## 3. Define Ownership

Every active item should have a clear owner or responsible team.

---

## 4. Prioritize the Backlog

Keep the most important work visible at the top.

---

## 5. Keep Status Accurate

If work is completed, update the work item.

Do not leave:

```text
Status: In Progress
```

when the work has already been completed.

---

## 6. Break Large Work into Smaller Items

Instead of:

```text
Build Entire Application
```

use:

```text
Application
│
├── Authentication
├── Database
├── API
├── Frontend
├── Testing
└── Deployment
```

Smaller work items are easier to plan and track.

---

## 7. Track Dependencies

Example:

```text
Frontend
   ↓
Blocked by
   ↓
Backend API
```

Dependencies should be visible to the team.

---

## 8. Connect Work to Development

Where appropriate, connect:

```text
Work Item
   ↓
Branch
   ↓
Commit
   ↓
Pull Request
   ↓
Deployment
```

This improves visibility across the delivery process.

---

## 9. Avoid Duplicate Tracking Systems

If teams maintain the same task in:

```text
Excel
+
Teams
+
GitHub
+
Azure Boards
```

the information can become inconsistent.

Choose a primary system and integrate other tools where necessary.

---

## 10. Keep the Process Simple

Work tracking should help the team rather than create unnecessary administrative work.

---

# 22. Hands-On Lab

## 🎯 Objective

Create and manage a basic work-tracking workflow using **Azure Boards** and connect it to a GitHub repository.

### Lab Architecture

```text
Azure Boards
     │
     ↓
Work Item
     │
     ↓
GitHub Repository
     │
     ↓
Branch
     │
     ↓
Commit
     │
     ↓
Pull Request
     │
     ↓
Completed Work
```

---

## Step 1 — Create an Azure DevOps Project

Open your Azure DevOps organization and create a project.

Example:

```text
Project Name:
Work-Tracking-Demo
```

---

## Step 2 — Open Azure Boards

Navigate to:

```text
Azure DevOps
    ↓
Project
    ↓
Boards
```

Explore:

- Boards
- Backlogs
- Sprints
- Queries

---

## Step 3 — Create a Work Item

Create a work item such as:

```text
Title:
Add login validation

Description:
Improve validation for invalid login attempts.
```

Set:

```text
Priority:
High

State:
New
```

---

## Step 4 — Assign the Work

Assign the work item to yourself.

Example:

```text
Assigned To:
Your Account
```

Change the state when development starts:

```text
New
 ↓
Active
```

---

## Step 5 — Create a GitHub Repository

Create or use a repository:

```text
work-tracking-demo
```

Clone it:

```bash
git clone <github-repository-url>

cd work-tracking-demo
```

---

## Step 6 — Connect Azure Boards and GitHub

Configure the connection between your Azure DevOps project and GitHub repository.

The integration allows development activity in GitHub to be associated with Azure Boards work items. :contentReference[oaicite:3]{index=3}

---

## Step 7 — Create a Branch

```bash
git switch main

git pull origin main

git switch -c feature/login-validation
```

---

## Step 8 — Make a Change

Modify the application or documentation.

Check the changes:

```bash
git status
```

---

## Step 9 — Commit the Change

Use a commit message that references the relevant work item according to the configured Azure Boards/GitHub integration.

Example:

```bash
git add .

git commit -m "Improve login validation"
```

---

## Step 10 — Push the Branch

```bash
git push -u origin feature/login-validation
```

---

## Step 11 — Create a Pull Request

Create:

```text
feature/login-validation
          ↓
         main
```

Review the Pull Request and verify that the development activity is associated with the relevant work.

---

## Step 12 — Complete the Work

After review and validation:

```text
Pull Request
      ↓
Merge
      ↓
Work Item
      ↓
Done
```

Update the Azure Boards work item to the appropriate completed state.

---

## Step 13 — Verify the Complete Flow

Your final workflow should look like:

```text
Requirement
     ↓
Azure Boards Work Item
     ↓
Prioritize
     ↓
Assign
     ↓
GitHub Branch
     ↓
Commit
     ↓
Pull Request
     ↓
Review
     ↓
Merge
     ↓
Work Item Completed
```

---

# 23. AZ-400 Exam Focus

For the current AZ-400 exam, work tracking is part of:

> **Design and implement traceability and flow of work**

Microsoft specifically lists:

- GitHub Projects
- Azure Boards
- Repositories
- Integration for tracking work :contentReference[oaicite:4]{index=4}

You should understand how these components fit together.

### Important Concepts

```text
Work Item
    ↓
Planning
    ↓
Backlog
    ↓
Sprint / Iteration
    ↓
Development
    ↓
Repository
    ↓
Pull Request
    ↓
Completed Work
```

### Know Azure Boards

Understand:

- Boards
- Backlogs
- Work items
- Queries
- Sprints
- Iterations
- Teams
- Work-item ownership
- Priorities
- Dependencies

### Know GitHub Projects

Understand:

- Projects
- Project items
- Issues
- Pull Requests
- Views
- Planning
- Status tracking

### Know Integration

Understand the purpose of connecting:

```text
Azure Boards
     ↕
GitHub Repository
```

The goal is to avoid separating planning from implementation.

### Scenario Thinking

If a question says:

> A company uses GitHub for source code but Azure DevOps for planning and wants developers to associate GitHub development activity with planned work.

Think:

```text
Azure Boards
     ↓
Work Item
     ↓
GitHub Repository
     ↓
Branch / Commit / Pull Request
     ↓
Tracked Work
```

If a question says:

> A team needs a lightweight work-management solution directly within its GitHub workflow.

Think:

```text
GitHub
  ↓
GitHub Projects
  ↓
Issues / Pull Requests
  ↓
Project Views
```

The important principle is:

> **Work tracking should connect planning with the actual engineering work rather than keeping them as isolated activities.**

---

# 24. Summary

**Work tracking** provides a structured way to plan, organize, assign, prioritize, and monitor work throughout the DevOps lifecycle.

The basic flow is:

```text
Requirement
     ↓
Work Item
     ↓
Prioritize
     ↓
Assign
     ↓
Plan
     ↓
Develop
     ↓
Test
     ↓
Complete
```

The key concepts introduced in this section are:

- **Work Items** represent individual pieces of work.
- **Backlogs** provide an ordered collection of planned work.
- **Boards** provide visual status tracking.
- **Sprints / Iterations** organize work into development periods.
- **Ownership** makes responsibility clear.
- **Prioritization** helps teams focus on valuable work.
- **Azure Boards** provides work tracking within Azure DevOps.
- **GitHub Projects** provides project and work-management capabilities within GitHub.
- **Repositories** contain the actual source code used to implement tracked work.
- **Integration** connects planning with branches, commits, and Pull Requests.
- **Dependencies** should be visible so teams can identify blocked work.
- **Work tracking** provides visibility from requirements through implementation.

The most important sequence to remember is:

> **Plan → Track → Assign → Develop → Link → Complete**

---

