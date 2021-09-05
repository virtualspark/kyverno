### Advanced Cloud Architecture - YCIT 020 at McGill University

## Kyverno

### What is Kyverno?
Kyverno is a policy engine designed for Kubernetes. It runs as an admission controller and can validate, mutate, and generate any configuration data based on customizable policies. It is designed to work nicely with tools you already use like kubectl, kustomize, and Git.

### How to get it started?

Step 1: Install Kyverno using Helm

a) Add the Kyverno Helm repository:

  helm repo add kyverno https://kyverno.github.io/kyverno/

