# GitHub Flow

## Introduction

**GitHub Flow** is a lightweight, branch-based workflow designed to support continuous integration and continuous delivery.

It provides a simple process for making changes to a repository:

```text
Create Branch
      ↓
Make Changes
      ↓
Commit Changes
      ↓
Push Branch
      ↓
Create Pull Request
      ↓
Review & Validate
      ↓
Merge
      ↓
Delete Branch
```

GitHub Flow is commonly used when teams want to make small, frequent changes while keeping the main branch in a deployable state.

The workflow is centered around the **main branch** and **Pull Requests**.

---

## 📚 Table of Contents

- [1. What is GitHub Flow?](#1-what-is-github-flow)
- [2. Core Principles of GitHub Flow](#2-core-principles-of-github-flow)
- [3. GitHub Flow Lifecycle](#3-github-flow-lifecycle)
- [4. Step 1 — Start from the Main Branch](#4-step-1--start-from-the-main-branch)
- [5. Step 2 — Create a Branch](#5-step-2--create-a-branch)
- [6. Step 3 — Make Changes](#6-step-3--make-changes)
- [7. Step 4 — Commit Changes](#7-step-4--commit-changes)
- [8. Step 5 — Push the Branch](#8-step-5--push-the-branch)
- [9. Step 6 — Create a Pull Request](#9-step-6--create-a-pull-request)
- [10. Step 7 — Review and Discuss](#10-step-7--review-and-discuss)
- [11. Step 8 — Validate the Pull Request](#11-step-8--validate-the-pull-request)
- [12. Step 9 — Merge the Pull Request](#12-step-9--merge-the-pull-request)
- [13. Step 10 — Delete the Branch](#13-step-10--delete-the-branch)
- [14. GitHub Flow Example](#14-github-flow-example)
- [15. Pull Requests in GitHub Flow](#15-pull-requests-in-github-flow)
- [16. Branch Protection](#16-branch-protection)
- [17. GitHub Flow and Continuous Integration](#17-github-flow-and-continuous-integration)
- [18. GitHub Flow with Azure DevOps](#18-github-flow-with-azure-devops)
- [19. Handling Changes During Review](#19-handling-changes-during-review)
- [20. Handling Failed Validation](#20-handling-failed-validation)
- [21. GitHub Flow Best Practices](#21-github-flow-best-practices)
- [22. Hands-On Lab](#22-hands-on-lab)
- [23. AZ-400 Exam Focus](#23-az-400-exam-focus)
- [24. Summary](#24-summary)

---

# 1. What is GitHub Flow?

GitHub Flow is a simple Git-based workflow that uses short-lived branches and Pull Requests.

The main idea is:

```text
main
  │
  ├── feature/change
  │
  └── Pull Request
          ↓
       Review
          ↓
        Merge
          ↓
         main
```

The `main` branch represents the primary branch of the repository.

Developers normally do not make significant changes directly to `main`.

Instead, they:

1. Create a branch from `main`
2. Make changes
3. Commit the changes
4. Push the branch
5. Open a Pull Request
6. Review and validate the changes
7. Merge the Pull Request
8. Delete the temporary branch

---

# 2. Core Principles of GitHub Flow

GitHub Flow is based on several important principles.

## 2.1 Keep the Main Branch Stable

The `main` branch should remain in a usable state.

```text
main
 │
 ├── stable
 ├── tested
 └── deployable
```

Changes should normally reach `main` through Pull Requests.

---

## 2.2 Use Short-Lived Branches

Branches should normally represent a specific change.

Examples:

```text
feature/payment
feature/user-profile
fix/login-error
docs/api-documentation
```

Avoid keeping branches open for unnecessarily long periods.

---

## 2.3 Use Pull Requests

Pull Requests provide a controlled point for:

- Code review
- Discussion
- Automated validation
- Security checks
- Testing
- Approval

---

## 2.4 Make Small Changes

Small Pull Requests are generally easier to:

- Review
- Test
- Understand
- Merge
- Troubleshoot

---

## 2.5 Keep Feedback Close to the Change

Developers should be able to receive feedback while the change is still being worked on.

```text
Change
  ↓
Pull Request
  ↓
Review
  ↓
Feedback
  ↓
Update
  ↓
Validation
  ↓
Merge
```

---

# 3. GitHub Flow Lifecycle

The complete GitHub Flow lifecycle is:

```text
                 ┌──────────────┐
                 │     main     │
                 └──────┬───────┘
                        ↓
                Create Branch
                        ↓
                Make Changes
                        ↓
                     Commit
                        ↓
                   Push Branch
                        ↓
                Create Pull Request
                        ↓
              Review & Discussion
                        ↓
               Automated Checks
                        ↓
                 ┌──────┴──────┐
                 ↓             ↓
               Pass           Fail
                 ↓             ↓
               Merge         Fix
                 ↓             │
                main ←─────────┘
                 ↓
          Delete Feature Branch
```

The key workflow is:

```text
Branch → Change → Commit → Push → Pull Request → Review → Validate → Merge
```

---

# 4. Step 1 — Start from the Main Branch

Before creating a new branch, make sure the local repository is synchronized with the remote repository.

```bash
git checkout main
git pull origin main
```

With newer Git versions, the equivalent command can be:

```bash
git switch main
git pull origin main
```

This reduces the chance of starting development from an outdated version of the repository.

---

# 5. Step 2 — Create a Branch

Create a branch for the specific change.

Example:

```bash
git switch -c feature/payment
```

Or:

```bash
git checkout -b feature/payment
```

The repository now looks like:

```text
main
  │
  └── feature/payment
```

The developer can work on the feature without directly modifying `main`.

---

## Branch Naming Examples

Good branch names should clearly describe the purpose.

```text
feature/payment
feature/user-profile
feature/mfa
fix/login-error
fix/database-timeout
docs/api-guide
```

A consistent naming convention makes repositories easier to manage.

---

# 6. Step 3 — Make Changes

The developer implements the required change.

For example:

```text
feature/payment
       ↓
Add payment API
       ↓
Update application
       ↓
Add tests
       ↓
Update documentation
```

The developer can inspect changes using:

```bash
git status
```

To view the actual differences:

```bash
git diff
```

---

# 7. Step 4 — Commit Changes

Once a logical change is ready, create a Git commit.

```bash
git add .
```

Then:

```bash
git commit -m "Add payment integration"
```

A good commit message should explain what changed.

Examples:

```text
Add payment integration
Fix login validation
Update API documentation
Add unit tests for payment service
```

Avoid unclear messages such as:

```text
update
changes
fix
test
stuff
```

---

# 8. Step 5 — Push the Branch

Push the branch to GitHub.

```bash
git push -u origin feature/payment
```

The branch now exists remotely.

```text
Local Repository
       │
       │ git push
       ↓
GitHub Repository
       │
       └── feature/payment
```

The remote branch can now be used to create a Pull Request.

---

# 9. Step 6 — Create a Pull Request

A Pull Request is created to propose merging the branch into `main`.

```text
feature/payment
       ↓
Pull Request
       ↓
main
```

A Pull Request normally contains:

- Source branch
- Target branch
- Title
- Description
- Changed files
- Reviewers
- Checks
- Comments
- Linked work items

Example:

```text
Title:
Add payment integration

Source:
feature/payment

Target:
main
```

The Pull Request becomes the central collaboration point for the change.

---

# 10. Step 7 — Review and Discuss

Reviewers examine the proposed changes.

They may review:

- Application logic
- Code quality
- Security
- Tests
- Configuration
- Documentation
- Architecture
- Potential defects

A reviewer can leave comments on specific lines.

Example:

```text
Developer
    ↓
Pull Request
    ↓
Reviewer
    ↓
Comment
    ↓
Developer Updates Code
    ↓
New Commit
    ↓
Pull Request Updated
```

The Pull Request remains open until the required review and validation conditions are satisfied.

---

# 11. Step 8 — Validate the Pull Request

Automated checks can run against the Pull Request.

Typical checks include:

```text
Pull Request
      ↓
Build
      ↓
Unit Tests
      ↓
Integration Tests
      ↓
Security Scan
      ↓
Code Quality
      ↓
Validation Result
```

For example:

```text
Build                 ✓
Unit Tests            ✓
Integration Tests     ✓
Security Scan         ✓
Code Quality          ✓
```

If a check fails:

```text
Pull Request
      ↓
Automated Check
      ↓
Failure
      ↓
Developer Fix
      ↓
Commit
      ↓
Check Runs Again
```

This provides fast feedback before the change is merged.

---

# 12. Step 9 — Merge the Pull Request

After the required reviews and checks pass, the Pull Request can be merged.

```text
feature/payment
       ↓
Pull Request
       ↓
Review
       ↓
Validation
       ↓
Merge
       ↓
main
```

GitHub provides different merge options depending on repository configuration.

Common options include:

- Merge commit
- Squash and merge
- Rebase and merge

The choice depends on the team's repository and commit-history strategy.

---

# 13. Step 10 — Delete the Branch

After the Pull Request is merged, the temporary branch can usually be deleted.

```text
feature/payment
       ↓
Pull Request
       ↓
Merged
       ↓
Delete Branch
```

For example:

```bash
git push origin --delete feature/payment
```

The local branch can also be removed:

```bash
git branch -d feature/payment
```

This keeps the repository clean.

---

# 14. GitHub Flow Example

Consider a developer working on a payment feature.

### Step 1

Start from `main`.

```text
main
```

### Step 2

Create a branch.

```text
main
  │
  └── feature/payment
```

### Step 3

Implement the feature.

```text
feature/payment
       ↓
Payment API
Payment UI
Payment Tests
```

### Step 4

Commit and push.

```text
feature/payment
       ↓
GitHub
```

### Step 5

Create Pull Request.

```text
feature/payment
       ↓
Pull Request
       ↓
main
```

### Step 6

Review and validate.

```text
Code Review
     +
Automated Tests
     +
Security Checks
```

### Step 7

Merge.

```text
feature/payment
       ↓
      main
```

### Step 8

Delete the branch.

```text
main
```

The completed feature is now part of the main branch.

---

# 15. Pull Requests in GitHub Flow

Pull Requests are a central component of GitHub Flow.

A Pull Request provides a place where teams can:

- Review code
- Discuss implementation
- Run automated checks
- Validate quality
- Review security
- Track changes
- Approve or reject changes

A Pull Request lifecycle can be represented as:

```text
Create PR
   ↓
Review
   ↓
Comments
   ↓
Developer Changes
   ↓
Automated Checks
   ↓
Approval
   ↓
Merge
```

A Pull Request can remain open while changes are being discussed.

---

# 16. Branch Protection

GitHub Flow becomes more reliable when the `main` branch is protected.

Branch protection can enforce rules such as:

- Require Pull Requests
- Require approvals
- Require successful status checks
- Require branches to be up to date
- Restrict direct pushes
- Restrict force pushes
- Require conversation resolution

Example:

```text
Developer
    ↓
feature branch
    ↓
Pull Request
    ↓
Required Review
    ↓
Required Checks
    ↓
Approval
    ↓
main
```

Without protection, a developer could potentially bypass the Pull Request process.

---

# 17. GitHub Flow and Continuous Integration

GitHub Flow works well with Continuous Integration.

A Pull Request can automatically trigger a CI workflow.

```text
Developer
    ↓
Push Branch
    ↓
Pull Request
    ↓
CI Pipeline
    ↓
Build
    ↓
Test
    ↓
Security Validation
    ↓
Result
```

For example:

```text
Pull Request
     │
     ├── Build ✓
     ├── Unit Tests ✓
     ├── Integration Tests ✓
     ├── Code Analysis ✓
     └── Security Scan ✓
              ↓
           Approved
              ↓
            Merge
```

This prevents changes from being merged without passing required validation.

---

# 18. GitHub Flow with Azure DevOps

GitHub Flow can be used even when Azure DevOps provides the CI/CD platform.

For example:

```text
GitHub Repository
       ↓
GitHub Flow
       ↓
Pull Request
       ↓
Azure Pipelines
       ↓
Build
       ↓
Test
       ↓
Security Validation
       ↓
Artifact
       ↓
Deployment
```

A team may therefore use:

| Platform | Responsibility |
|---|---|
| GitHub | Repository and Pull Requests |
| Azure Pipelines | CI/CD |
| Azure Artifacts | Package management |
| Azure Environments | Deployment environments |
| Azure Monitor | Monitoring |
| Microsoft Entra ID | Identity and authentication |

This is important for AZ-400 because modern DevOps environments can combine GitHub and Azure DevOps services.

---

# 19. Handling Changes During Review

A Pull Request is not necessarily completed after the first submission.

Reviewers may request changes.

Example:

```text
Pull Request
      ↓
Code Review
      ↓
Changes Requested
      ↓
Developer Updates Code
      ↓
Commit
      ↓
Push
      ↓
Pull Request Updated
      ↓
Review Again
```

The developer can continue committing to the same branch.

The Pull Request automatically reflects the new commits.

Example:

```bash
git add .
git commit -m "Address review comments"
git push
```

The existing Pull Request is updated.

---

# 20. Handling Failed Validation

If an automated check fails, the Pull Request should not be merged until the problem is addressed.

Example:

```text
Pull Request
      ↓
Build
      ↓
Failed
      ↓
Investigate
      ↓
Fix
      ↓
Commit
      ↓
Push
      ↓
Build Again
```

For example:

```text
Unit Tests
    ↓
Failure
    ↓
Developer Investigates
    ↓
Fix Code
    ↓
Push
    ↓
Unit Tests
    ↓
Pass
```

This creates a feedback loop directly inside the Pull Request.

---

# 21. GitHub Flow Best Practices

## 1. Keep Branches Short-Lived

Avoid keeping feature branches open for long periods when possible.

## 2. Keep Pull Requests Small

Smaller Pull Requests are easier to review and validate.

## 3. Protect Main

Require Pull Requests and appropriate validation before merging.

## 4. Automate Validation

Run builds, tests, and security checks automatically.

## 5. Write Meaningful Commit Messages

Commits should clearly describe the change.

## 6. Use Clear Branch Names

Examples:

```text
feature/payment
fix/login-error
docs/api-guide
```

## 7. Review Before Merging

Use Pull Requests as the collaboration and quality-control point.

## 8. Resolve Review Comments

Do not leave unresolved review discussions before merging when repository policies require resolution.

## 9. Keep Main Deployable

Changes merged into `main` should meet the repository's required quality standards.

## 10. Delete Completed Branches

Remove branches that are no longer needed.

---

# 22. Hands-On Lab

## 🎯 Objective

Implement a complete GitHub Flow workflow using a GitHub repository.

### Lab Flow

```text
main
 ↓
Create Feature Branch
 ↓
Make Changes
 ↓
Commit
 ↓
Push
 ↓
Pull Request
 ↓
Review
 ↓
Automated Validation
 ↓
Merge
 ↓
Delete Branch
```

---

## Step 1 — Clone a Repository

```bash
git clone <github-repository-url>

cd <repository-name>
```

---

## Step 2 — Switch to Main

```bash
git switch main
```

Pull the latest changes:

```bash
git pull origin main
```

---

## Step 3 — Create a Feature Branch

```bash
git switch -c feature/github-flow-demo
```

---

## Step 4 — Make a Change

Create or modify a file.

Example:

```text
github-flow-demo/
│
├── README.md
└── index.html
```

---

## Step 5 — Commit the Change

```bash
git add .

git commit -m "Add GitHub Flow demo"
```

---

## Step 6 — Push the Branch

```bash
git push -u origin feature/github-flow-demo
```

---

## Step 7 — Create a Pull Request

Create:

```text
feature/github-flow-demo
          ↓
         main
```

Add:

- Pull Request title
- Description
- Reviewers
- Related work item if applicable

---

## Step 8 — Review the Pull Request

Review:

- Changed files
- Commit history
- Comments
- Automated checks

---

## Step 9 — Merge

After all required checks and approvals pass, merge the Pull Request.

```text
feature/github-flow-demo
          ↓
         main
```

---

## Step 10 — Delete the Branch

Delete the completed feature branch.

```bash
git branch -d feature/github-flow-demo
```

If deleting the remote branch manually:

```bash
git push origin --delete feature/github-flow-demo
```

---

## Step 11 — Synchronize Local Main

```bash
git switch main

git pull origin main
```

The GitHub Flow lifecycle is now complete.

---

# 23. AZ-400 Exam Focus

For AZ-400, understand **GitHub Flow as a development workflow** and how it supports continuous delivery.

Important concepts include:

- GitHub Flow
- Main branch
- Short-lived branches
- Pull Requests
- Code review
- Automated validation
- Branch protection
- Required checks
- Approvals
- Merge
- Branch cleanup
- Continuous Integration
- GitHub and Azure DevOps integration

A scenario may ask you to determine how developers should safely introduce changes into a repository.

Think:

```text
Main
 ↓
Feature Branch
 ↓
Changes
 ↓
Pull Request
 ↓
Review
 ↓
Automated Checks
 ↓
Approval
 ↓
Merge
 ↓
Main
```

The important point is that **GitHub Flow provides a lightweight process for moving changes from development into the main branch while using Pull Requests and automated validation as control points.**

---

# 24. Summary

**GitHub Flow** is a lightweight Git workflow centered around the `main` branch and Pull Requests.

The complete process is:

```text
Create Branch
      ↓
Make Changes
      ↓
Commit
      ↓
Push
      ↓
Pull Request
      ↓
Review
      ↓
Automated Validation
      ↓
Approval
      ↓
Merge
      ↓
Delete Branch
```

The key concepts introduced in this section are:

- **GitHub Flow** provides a simple workflow for collaborative development.
- **Main Branch** represents the primary repository branch.
- **Feature Branches** isolate individual changes.
- **Pull Requests** provide a controlled collaboration and review point.
- **Code Review** allows developers to inspect proposed changes.
- **Automated Checks** validate builds, tests, security, and quality.
- **Branch Protection** prevents unsafe changes from reaching important branches.
- **Merge** integrates an approved change into the main branch.
- **Branch Cleanup** removes temporary branches after successful completion.
- **Azure Pipelines** can be integrated with GitHub Flow for CI/CD.
- **Continuous Validation** helps keep the main branch reliable.

The most important GitHub Flow sequence to remember is:

> **Branch → Change → Commit → Push → Pull Request → Review → Validate → Merge → Delete Branch**

---

