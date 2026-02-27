# Why Kubernetes Exists

Kubernetes is a container orchestration platform designed to manage containerized applications at scale across a cluster of machines.

Containers alone solve packaging and isolation, but they do not solve large-scale operational challenges.

---

## Problem Containers Alone Could Not Solve

- Running containers across multiple nodes.
- Automatic scheduling based on resources.
- Self-healing when containers crash.
- Scaling applications based on demand.
- Service discovery between dynamic workloads.
- Maintaining application state consistently.

---

## What Orchestration Means

Orchestration means automating the deployment, scaling, networking, and lifecycle management of containerized applications across a cluster.

Instead of manually starting containers, Kubernetes manages them based on defined policies.

---

## Declarative Model and Desired State

Kubernetes follows a declarative model.

This means:
- The user defines the desired state (for example: 3 replicas of a Pod).
- Kubernetes continuously ensures the actual state matches the desired state.

If a Pod crashes, Kubernetes recreates it automatically to maintain the declared state.

---

# Kubernetes Architecture

## Control Plane Components

- API Server: The entry point for all cluster communication. All requests go through the API server.
- etcd: A distributed key-value store that stores the cluster’s desired state and configuration data.
- Scheduler: Assigns Pods to suitable nodes based on resource requirements and constraints.
- Controller Manager: Runs controllers that continuously reconcile actual state with desired state.

---

## Node Components

- kubelet: An agent running on each node that ensures containers are running as defined.
- container runtime: Software such as containerd that runs containers.
- kube-proxy: Maintains networking rules so Services can route traffic to the correct Pods.

---

# AKS Context

## What Microsoft Manages
- Control plane infrastructure
- API server availability
- etcd and control plane components
- Control plane upgrades

## What I Manage
- Node pools
- Workloads and deployments
- Networking configurations
- RBAC and security policies
