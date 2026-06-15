# Frontend-Artifact-Registry-Deployment

Project Description – Frontend Artifact Registry Deployment

This project demonstrates a hybrid DevOps CI/CD pipeline that combines Ansible for artifact packaging and Terraform for infrastructure provisioning and deployment. The goal is to package a frontend application's build output into a deployable artifact and publish it to a cloud-based artifact registry (simulated using an AWS S3-compatible local cloud emulator).

Project Objectives
Package frontend application build files into a compressed release artifact.
Store deployment artifacts in a centralized artifact registry.
Provision cloud infrastructure using Infrastructure as Code (IaC).
Automate the deployment process using Ansible and Terraform.
Follow enterprise DevOps best practices by separating build, packaging, and deployment responsibilities.
Workflow Overview
1. Package the Frontend Application (Ansible)

Ansible acts as the local packaging engine:

Targets localhost instead of remote servers.
Compresses the frontend build directory.
Creates a deployable artifact named:
release.tar.gz

Source directory:

./artifact-publisher/build

Generated artifact:

./release.tar.gz
2. Provision the Artifact Registry (Terraform)

Terraform creates the infrastructure required to store deployment artifacts:

Creates an S3 bucket named:
company-artifact-registry
Manages infrastructure declaratively through code.
Tracks infrastructure state automatically.
3. Upload the Artifact

Terraform uploads the generated archive:

release.tar.gz

to the artifact registry bucket as:

release.tar.gz

This simulates a production artifact publishing workflow where application releases are stored centrally before deployment to downstream environments.

Technologies Used
Ansible
Artifact packaging
Automation workflows
Local task execution
Terraform
Infrastructure as Code (IaC)
Resource provisioning
State management
AWS S3 (Moto Emulator)
Artifact storage
Cloud resource simulation
Safe local testing environment
DevOps Concepts Demonstrated
Continuous Integration (CI)
Artifact Management
Infrastructure as Code (IaC)
Automation and Orchestration
Separation of Concerns
Release Packaging
Cloud Storage Deployment
Reproducible Infrastructure
Expected Outcome

After executing the pipeline:

The frontend build directory is compressed into release.tar.gz.
Terraform provisions the S3 artifact registry bucket.
The release artifact is uploaded successfully.
Infrastructure and deployment actions are tracked in Terraform state.
The complete process is automated and repeatable.
Business Value

This project mirrors real-world enterprise CI/CD pipelines where developers build applications, automation tools package release artifacts, and infrastructure platforms securely store versioned releases. By separating packaging (Ansible) from infrastructure management (Terraform), the deployment process becomes more scalable, maintainable, and production-ready.
