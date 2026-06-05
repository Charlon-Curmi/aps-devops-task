# APS Bank DevOps Assignment

## Overview

This project demonstrates the implementation of a CI/CD pipeline for a .NET application using GitHub Actions.

The solution includes source control management, automated builds, automated testing, deployment stages, environment separation, and deployment approvals.

---

## Technology Stack

* ASP.NET Core MVC (.NET 8)
* Git
* GitHub
* GitHub Actions
* xUnit
* Visual Studio Code
* macOS

---

## Application

A simple ASP.NET Core MVC application was selected to demonstrate the CI/CD process.

The application supports multiple environments through environment-specific configuration files:

* appsettings.Development.json
* appsettings.Test.json
* appsettings.Production.json

The active environment is displayed within the application to verify correct configuration loading.

---

## Branching Strategy

The repository follows a simplified feature-branch workflow.

### Branches

* main
* feature/*

### Workflow

1. Create a feature branch from main.
2. Implement changes.
3. Create a Pull Request.
4. Execute CI validation.
5. Merge into main.
6. Trigger deployment pipeline.

---

## Continuous Integration

The CI pipeline is implemented using GitHub Actions.

### Trigger Conditions

* Push to main
* Pull Requests targeting main

### Pipeline Stages

1. Checkout source code
2. Setup .NET SDK
3. Restore dependencies
4. Build application
5. Execute automated tests

The pipeline automatically validates code changes before deployment.

---

## Automated Testing

An xUnit test project is included in the solution.

Tests are executed automatically as part of the CI pipeline.

Pipeline execution fails if any test fails.

---

## Continuous Deployment

A separate GitHub Actions workflow is used for deployment activities.

### Deployment Flow

1. Build application
2. Publish application artifacts
3. Deploy to Test environment
4. Await approval
5. Deploy to Production environment

---

## Environment Management

The solution supports:

* Development
* Test
* Production

Each environment can maintain its own configuration while sharing the same codebase.

---

## Benefits

* Automated validation
* Consistent build process
* Reduced deployment risk
* Environment separation
* Deployment approvals
* Improved maintainability

---

## Future Improvements

Possible enhancements include:

* Docker containerization
* Cloud deployment targets
* Infrastructure as Code
* Automated security scanning
* Integration testing
* Monitoring and alerting
