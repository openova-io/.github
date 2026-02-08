# OpenOva

**Enterprise-grade support provider for open-source Kubernetes ecosystems.**

OpenOva provides a converged blueprint ecosystem with operational guarantees, enabling cloud-native transformation for enterprises.

---

## Repository

All OpenOva platform components are in a single monorepo:

**[openova-io/openova](https://github.com/openova-io/openova)** - OpenOva Platform Monorepo

---

## Documentation

| Document | Description |
|----------|-------------|
| [Platform Tech Stack](https://github.com/openova-io/openova/blob/main/docs/PLATFORM-TECH-STACK.md) | Technology stack overview |
| [SRE Handbook](https://github.com/openova-io/openova/blob/main/docs/SRE.md) | Site reliability practices |
| [Core Application](https://github.com/openova-io/openova/blob/main/core/README.md) | Bootstrap + Lifecycle Manager |

---

## What We Provide

| Offering | Description |
|----------|-------------|
| **Converged Blueprints** | Production-ready K8s component bundles |
| **Day-2 Operations** | Upgrades, security, SLA guarantees |
| **Transformation Journey** | Cloud-native adoption partnership |

---

## Platform Architecture

```
Bootstrap Wizard → Customer's K8s + Backstage + Flux + Gitea
                 → OpenOva Blueprints (stays in picture)
```

---

## Monorepo Structure

```
openova/
├── core/                    # Bootstrap + Lifecycle Manager
├── platform/                # Component blueprints
│   ├── networking/          # Cilium, k8gb, ExternalDNS, STUNner
│   ├── security/            # cert-manager, ESO, Vault, Trivy
│   ├── policy/              # Kyverno
│   ├── observability/       # Grafana Stack
│   ├── registry/            # Harbor
│   ├── storage/             # MinIO, Velero
│   ├── scaling/             # KEDA, VPA
│   ├── failover/            # Failover Controller
│   ├── gitops/              # Flux, Gitea
│   ├── idp/                 # Backstage
│   ├── data/                # CNPG, MongoDB, Valkey, Redpanda
│   ├── communication/       # Stalwart
│   ├── iac/                 # Terraform, Crossplane
│   └── identity/            # Keycloak
├── meta-platforms/          # Bundled vertical solutions
│   ├── ai-hub/              # Enterprise AI platform
│   └── open-banking/        # PSD2/FAPI fintech sandbox
└── docs/                    # Platform documentation
```

---

## Platform Components

### Mandatory

| Category | Components |
|----------|------------|
| **Networking** | Cilium, k8gb, ExternalDNS, STUNner |
| **Security** | cert-manager, External Secrets, Vault, Trivy |
| **Policy** | Kyverno |
| **Observability** | Grafana Stack (Alloy, Loki, Mimir, Tempo) |
| **Registry** | Harbor |
| **Storage** | MinIO, Velero |
| **Scaling** | KEDA, VPA |
| **Failover** | Failover Controller |
| **GitOps** | Flux, Gitea |
| **IDP** | Backstage |
| **IaC** | Terraform (bootstrap), Crossplane (day-2) |

### A La Carte

| Category | Components |
|----------|------------|
| **Data** | CNPG (PostgreSQL), MongoDB, Valkey, Redpanda |
| **Communication** | Stalwart (email), STUNner (WebRTC) |
| **Identity** | Keycloak |

---

## Meta-Platforms

### AI Hub

Enterprise AI platform with LLM serving, RAG, and intelligent agents.

Components: KServe, Knative, vLLM, Milvus, Neo4j, LangServe, LibreChat, n8n, SearXNG, BGE

### Open Banking

Fintech sandbox with PSD2/FAPI compliance.

Components: Keycloak (FAPI), OpenMeter, Lago

---

## Cloud Providers

| Provider | Status |
|----------|--------|
| Hetzner Cloud | Available |
| Huawei Cloud | Coming Soon |
| Oracle Cloud (OCI) | Coming Soon |

---

## Getting Started

```bash
# Managed Bootstrap (recommended)
# Visit https://bootstrap.openova.io

# Self-Hosted Bootstrap
docker run -p 8080:8080 ghcr.io/openova-io/bootstrap:latest
```

---

## Hosted Products

- [TalentMesh](https://github.com/talentmesh-io) - AI-powered talent assessment platform

---

*Enterprise Kubernetes, delivered with GitOps*
