# OpenOva

**Enterprise-grade support provider for open-source Kubernetes ecosystems.**

OpenOva provides a converged blueprint ecosystem with operational guarantees, enabling cloud-native transformation for enterprises.

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

## Repository Structure

### Core Platform

| Repository | Purpose |
|------------|---------|
| [bootstrap](https://github.com/openova-io/bootstrap) | Platform bootstrap wizard |
| [terraform](https://github.com/openova-io/terraform) | Infrastructure as Code (bootstrap) |
| [flux](https://github.com/openova-io/flux) | GitOps configuration |

### Networking & Service Mesh

| Repository | Purpose |
|------------|---------|
| [cilium](https://github.com/openova-io/cilium) | CNI + Service Mesh (eBPF, mTLS) |
| [k8gb](https://github.com/openova-io/k8gb) | Global Server Load Balancing |
| [stunner](https://github.com/openova-io/stunner) | K8s-native TURN server |

### Security

| Repository | Purpose |
|------------|---------|
| [external-secrets](https://github.com/openova-io/external-secrets) | Secrets management (ESO + Vault) |
| [vault](https://github.com/openova-io/vault) | Secrets backend |
| [kyverno](https://github.com/openova-io/kyverno) | Policy engine |
| [trivy](https://github.com/openova-io/trivy) | Security scanning |
| [cert-manager](https://github.com/openova-io/cert-manager) | TLS certificate automation |

### Storage & Registry

| Repository | Purpose |
|------------|---------|
| [harbor](https://github.com/openova-io/harbor) | Container registry |
| [minio](https://github.com/openova-io/minio) | S3-compatible object storage |
| [velero](https://github.com/openova-io/velero) | Kubernetes backup |

### Observability

| Repository | Purpose |
|------------|---------|
| [grafana](https://github.com/openova-io/grafana) | LGTM stack (Loki, Tempo, Mimir) |

### GitOps & Developer Platform

| Repository | Purpose |
|------------|---------|
| [gitea](https://github.com/openova-io/gitea) | Self-hosted Git + CI/CD |
| [backstage](https://github.com/openova-io/backstage) | Internal Developer Platform |

### Scaling

| Repository | Purpose |
|------------|---------|
| [keda](https://github.com/openova-io/keda) | Event-driven autoscaling |
| [vpa](https://github.com/openova-io/vpa) | Vertical Pod Autoscaler |

---

## Data Services (A La Carte)

| Repository | Purpose |
|------------|---------|
| [cnpg](https://github.com/openova-io/cnpg) | PostgreSQL operator |
| [mongodb](https://github.com/openova-io/mongodb) | Document database |
| [valkey](https://github.com/openova-io/valkey) | Redis-compatible cache |
| [redpanda](https://github.com/openova-io/redpanda) | Kafka-compatible streaming |

---

## Communication (A La Carte)

| Repository | Purpose |
|------------|---------|
| [stalwart](https://github.com/openova-io/stalwart) | Self-hosted email server |

---

## Meta Blueprints

### AI Hub

Enterprise AI platform with LLM serving, RAG, and intelligent agents.

| Repository | Purpose |
|------------|---------|
| [ai-hub](https://github.com/openova-io/ai-hub) | Meta blueprint (stitches all AI components) |
| [llm-gateway](https://github.com/openova-io/llm-gateway) | Subscription proxy for Claude Code |
| [anthropic-adapter](https://github.com/openova-io/anthropic-adapter) | Claude API translation |
| [knative](https://github.com/openova-io/knative) | Serverless platform |
| [kserve](https://github.com/openova-io/kserve) | Model serving |
| [vllm](https://github.com/openova-io/vllm) | LLM inference engine |
| [langserve](https://github.com/openova-io/langserve) | LangChain RAG service |
| [milvus](https://github.com/openova-io/milvus) | Vector database |
| [neo4j](https://github.com/openova-io/neo4j) | Graph database |
| [librechat](https://github.com/openova-io/librechat) | Chat UI |
| [n8n](https://github.com/openova-io/n8n) | Workflow automation |
| [searxng](https://github.com/openova-io/searxng) | Privacy-respecting web search |
| [bge](https://github.com/openova-io/bge) | Embeddings + reranking |

### Open Banking

Fintech sandbox with PSD2/FAPI compliance.

| Repository | Purpose |
|------------|---------|
| [open-banking](https://github.com/openova-io/open-banking) | Meta blueprint |
| [keycloak](https://github.com/openova-io/keycloak) | FAPI Authorization Server |
| [openmeter](https://github.com/openova-io/openmeter) | Usage metering |
| [lago](https://github.com/openova-io/lago) | Billing and invoicing |

---

## Cloud Providers

| Provider | Status |
|----------|--------|
| Hetzner Cloud | Available |
| Huawei Cloud | Coming Soon |
| Oracle Cloud (OCI) | Coming Soon |

---

## Documentation

| Document | Description |
|----------|-------------|
| [Platform Tech Stack](PLATFORM-TECH-STACK.md) | Technology stack overview |
| [Repository Structure](REPOSITORY-STRUCTURE.md) | Repository organization |
| [SRE Handbook](SRE.md) | Site reliability practices |

---

## Hosted Products

- [TalentMesh](https://github.com/talentmesh-io) - AI-powered talent assessment platform

---

*Enterprise Kubernetes, delivered with GitOps*
