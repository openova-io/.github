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

## Monorepo Structure

```
openova/
├── core/                    # Bootstrap + Lifecycle Manager
├── platform/                # All 41 component blueprints (flat)
├── meta-platforms/          # Bundled vertical solutions
│   ├── ai-hub/              # Enterprise AI platform
│   └── open-banking/        # PSD2/FAPI fintech sandbox (+ 6 services)
└── docs/                    # Platform documentation
```

---

## Platform Components (41)

All components under `platform/` (flat structure):

### Mandatory (Core Platform)

| Category | Components |
|----------|------------|
| **Infrastructure** | terraform, crossplane |
| **GitOps & IDP** | flux, gitea, backstage |
| **Networking** | cilium, external-dns, k8gb, stunner |
| **Security** | cert-manager, external-secrets, vault, trivy |
| **Policy** | kyverno |
| **Observability** | grafana |
| **Scaling** | vpa, keda |
| **Storage** | minio, velero |
| **Registry** | harbor |
| **Failover** | failover-controller |

### A La Carte (Optional)

| Category | Components |
|----------|------------|
| **Data** | cnpg, mongodb, valkey, redpanda |
| **Identity** | keycloak |
| **Communication** | stalwart |
| **Monetization** | openmeter, lago |
| **AI/ML** | knative, kserve, vllm, milvus, neo4j, langserve, librechat, n8n, searxng, bge, llm-gateway, anthropic-adapter |

---

## Meta-Platforms

### AI Hub

Enterprise AI platform with LLM serving, RAG, and intelligent agents.

**Uses:** kserve, knative, vllm, milvus, neo4j, langserve, librechat, n8n, searxng, bge, llm-gateway, anthropic-adapter

### Open Banking

Fintech sandbox with PSD2/FAPI compliance.

**Uses:** keycloak, openmeter, lago + 6 custom services

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
