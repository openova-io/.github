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

All components flat under `platform/`:

anthropic-adapter, backstage, bge, cert-manager, cilium, cnpg, crossplane, external-dns, external-secrets, failover-controller, flux, gitea, grafana, harbor, k8gb, keda, keycloak, knative, kserve, kyverno, lago, langserve, librechat, llm-gateway, milvus, minio, mongodb, n8n, neo4j, openmeter, redpanda, searxng, stalwart, stunner, terraform, trivy, valkey, vault, velero, vllm, vpa

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
