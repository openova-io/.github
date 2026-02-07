# Repository Structure

OpenOva platform repository organization and namespace conventions.

**Status:** Accepted | **Updated:** 2026-02-07

---

## Overview

OpenOva adopts a product-centric repository structure with one repository per component.

---

## Repository Organization

```
openova-io/
├── .github/            # Org documentation
│
├── # Core Platform
├── bootstrap/          # Bootstrap wizard
├── terraform/          # Infrastructure as Code (bootstrap)
├── flux/               # GitOps configuration
│
├── # Networking & Service Mesh
├── cilium/             # CNI + Service Mesh
├── k8gb/               # Global Server Load Balancing
├── stunner/            # WebRTC gateway
│
├── # Security
├── external-secrets/   # Secrets management (ESO)
├── vault/              # Secrets backend
├── kyverno/            # Policy engine
├── trivy/              # Security scanning
├── cert-manager/       # TLS automation
│
├── # Storage & Registry
├── harbor/             # Container registry
├── minio/              # Object storage
├── velero/             # Backup
│
├── # Observability
├── grafana/            # LGTM stack
│
├── # GitOps & IDP
├── gitea/              # Self-hosted Git + CI/CD
├── backstage/          # Developer portal
│
├── # Scaling
├── keda/               # Event-driven autoscaling
├── vpa/                # Vertical Pod Autoscaler
│
├── # Data Services (A La Carte)
├── cnpg/               # PostgreSQL
├── mongodb/            # MongoDB
├── valkey/             # Redis-compatible cache
├── redpanda/           # Kafka-compatible streaming
│
├── # Communication (A La Carte)
├── stalwart/           # Email server
│
├── # AI Hub Meta Blueprint
├── ai-hub/             # AI Hub meta blueprint
├── llm-gateway/        # Subscription proxy for Claude Code
├── anthropic-adapter/  # Claude API translation
├── knative/            # Serverless platform
├── kserve/             # Model serving
├── vllm/               # LLM inference
├── langserve/          # LangChain RAG service
├── milvus/             # Vector database
├── neo4j/              # Graph database
├── librechat/          # Chat UI
├── n8n/                # Workflow automation
├── searxng/            # Web search
├── bge/                # Embeddings + reranking
│
├── # Open Banking Meta Blueprint
├── open-banking/       # Open Banking meta blueprint
├── keycloak/           # FAPI Authorization Server
├── openmeter/          # Usage metering
└── lago/               # Billing
```

---

## Rationale

| Principle | Benefit |
|-----------|---------|
| Independent versioning | Each component versions separately |
| Flux integration | Each repo is a GitRepository source |
| Clear ownership | CODEOWNERS per repository |
| Co-located docs | README.md lives with code |

---

## Repository Standard

Each repository contains:

```
<component>/
├── README.md           # Single merged documentation
├── deploy/             # Kustomize manifests
│   ├── base/
│   └── overlays/
├── charts/             # Helm charts (if applicable)
└── tests/              # Integration tests
```

---

## Namespace Categories

| Namespace | Purpose | Owner |
|-----------|---------|-------|
| `kube-system` | Kubernetes system | Platform |
| `flux-system` | GitOps controllers | Platform |
| `cilium-gateway` | Cilium Gateway and Service Mesh | Platform |
| `monitoring` | Observability stack | Platform |
| `platform-services` | Shared platform services | Platform |
| `databases` | Database operators | Platform |
| `<tenant>-*` | Tenant workloads | Tenant |

---

## Platform Namespaces

```yaml
---
apiVersion: v1
kind: Namespace
metadata:
  name: flux-system
  labels:
    app.kubernetes.io/part-of: openova
    openova.io/component: gitops
---
apiVersion: v1
kind: Namespace
metadata:
  name: cilium-gateway
  labels:
    app.kubernetes.io/part-of: openova
    openova.io/component: mesh
---
apiVersion: v1
kind: Namespace
metadata:
  name: monitoring
  labels:
    app.kubernetes.io/part-of: openova
    openova.io/component: observability
---
apiVersion: v1
kind: Namespace
metadata:
  name: platform-services
  labels:
    app.kubernetes.io/part-of: openova
    openova.io/component: platform
---
apiVersion: v1
kind: Namespace
metadata:
  name: databases
  labels:
    app.kubernetes.io/part-of: openova
    openova.io/component: data
```

---

## Tenant Namespace Template

```yaml
---
apiVersion: v1
kind: Namespace
metadata:
  name: <tenant>-prod
  labels:
    app.kubernetes.io/part-of: <tenant>
    openova.io/tenant: <tenant>
    openova.io/environment: production
---
apiVersion: v1
kind: Namespace
metadata:
  name: <tenant>-staging
  labels:
    app.kubernetes.io/part-of: <tenant>
    openova.io/tenant: <tenant>
    openova.io/environment: staging
```

---

## Resource Quotas

```yaml
apiVersion: v1
kind: ResourceQuota
metadata:
  name: <tenant>-quota
  namespace: <tenant>-prod
spec:
  hard:
    requests.cpu: "4"
    requests.memory: 8Gi
    limits.cpu: "8"
    limits.memory: 16Gi
    persistentvolumeclaims: "10"
    pods: "50"
```

---

## Network Policy (Default Deny)

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: default-deny-all
  namespace: <tenant>-prod
spec:
  podSelector: {}
  policyTypes:
    - Ingress
    - Egress
```

---

## Consequences

**Positive:**
- Clean separation of concerns
- Independent releases per component
- GitOps-native structure
- Clear namespace ownership

**Negative:**
- Many repositories to manage
- Cross-repo coordination needed for platform updates

---

*Part of [OpenOva](https://openova.io)*
