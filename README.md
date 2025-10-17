# HRGFSA Helm Deployments

This repository contains Helm charts to deploy the HRGFSA application components on a GKE Kubernetes cluster.

## Overview

- Helm charts manage Deployments, ClusterIP Services, and Ingress resources.
- The application currently runs a Hello World NGINX image hosted on Docker Hub.
- The Ingress controller exposes services to the outside world using hostname `hello.danklofan.com`.
- Deployment and upgrades are automated with **GitHub Actions**.

## GitHub Actions Integration

- The same **Google Cloud service account credentials** used in `hrgfsa-infra-gcp` repo are used here.
- Stored securely as GitHub Secrets and used by the workflow to authenticate and deploy Helm releases to GKE.
- On pushing code or chart changes, the workflow runs Helm upgrade/install commands automatically.

## Deployment Instructions

1. Ensure your GCP service account JSON is stored as a GitHub Secret.
2. Confirm cluster access and context setup in workflows.
3. Push changes to the repo to trigger automated Helm releases.

## Repository Structure

- `charts/hello-world`: Helm chart with templates and default values.
- `values.yaml`: Configuration for Docker image, service (ClusterIP), and ingress.
- `.github/workflows/lint.yml`: Helm deployment CI/CD pipeline.

## Support & Contribution

Issues and pull requests for Helm chart improvements and bug fixes are welcome.

---
