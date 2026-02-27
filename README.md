# CI/CD Pipeline Comparison: Jenkins vs AWS CodePipeline

## Overview
This project demonstrates and compares two CI/CD approaches for a Java Spring Boot application (Spring PetClinic).

## Architecture

### Jenkins Pipeline
- **Jenkins** + **SonarQube** running via Docker Compose
- Stages: Checkout → Build → Test → SonarQube Analysis → Docker Build → Push to ECR

### AWS CodePipeline
- **CodePipeline** + **CodeBuild** (fully managed)
- Stages: Source (GitHub) → Build (CodeBuild) → Push to ECR

## Comparison

| Criteria | Jenkins | AWS CodePipeline |
|----------|---------|-----------------|
| Setup time | ~2h (manual config) | ~20min (console) |
| Maintenance | High (self-hosted) | None (managed) |
| Cost | Free (self-hosted) | Pay per use |
| Scalability | Manual | Automatic |
| AWS Integration | Plugin needed | Native |
| Flexibility | Very high | Medium |

## Tech Stack
- Java 21 / Spring Boot 4
- Maven
- Docker
- SonarQube
- AWS ECR, CodeBuild, CodePipeline
- Jenkins

## Results
- 57 unit tests passing
- SonarQube: 0 bugs, 0 vulnerabilities
- Docker image pushed to ECR on every build