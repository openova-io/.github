# openova

**Cloud-native kubernetes platform for hosting enterprise applications.**

openova provides a production-ready kubernetes infrastructure with:

- **K3s Cluster** on Contabo VPS (3-node HA with etcd quorum)
- **Cilium Service Mesh** with eBPF networking, WireGuard mTLS, and Hubble observability
- **Gitea** for self-hosted Git with bidirectional mirroring
- **Flux GitOps** for declarative continuous delivery
- **Grafana LGTM Stack** for unified observability (Loki, Grafana, Tempo, Mimir)

## Repository Structure

| Repository | Purpose |
|------------|---------|
| [handbook](https://github.com/openova-io/handbook) | Central documentation, ADRs, guides |
| [terraform](https://github.com/openova-io/terraform) | Infrastructure as Code for VPS/K3s |
| [flux](https://github.com/openova-io/flux) | GitOps cluster configuration |

### Infrastructure Components

| Repository | Category | Purpose |
|------------|----------|---------|
| [cilium](https://github.com/openova-io/cilium) | network | CNI + Service Mesh with eBPF |
| [gitea](https://github.com/openova-io/gitea) | platform | Self-hosted Git server |
| [k8gb](https://github.com/openova-io/k8gb) | network | Global Server Load Balancing |
| [stunner](https://github.com/openova-io/stunner) | network | K8s-native TURN server |
| [cnpg](https://github.com/openova-io/cnpg) | database | PostgreSQL operator |
| [mongodb](https://github.com/openova-io/mongodb) | database | MongoDB operator |
| [dragonfly](https://github.com/openova-io/dragonfly) | database | Redis-compatible cache |
| [redpanda](https://github.com/openova-io/redpanda) | middleware | Kafka-compatible streaming |
| [minio](https://github.com/openova-io/minio) | storage | S3-compatible object storage |
| [velero](https://github.com/openova-io/velero) | storage | Kubernetes backup |
| [grafana](https://github.com/openova-io/grafana) | observability | LGTM stack (Loki, Tempo, Mimir) |
| [keda](https://github.com/openova-io/keda) | autoscaling | Event-driven autoscaling |
| [kyverno](https://github.com/openova-io/kyverno) | security | Policy engine |
| [external-secrets](https://github.com/openova-io/external-secrets) | security | Secrets management (ESO + Vault) |
| [cert-manager](https://github.com/openova-io/cert-manager) | security | TLS certificate automation |
| [stalwart](https://github.com/openova-io/stalwart) | workplace | Self-hosted email server |

## Hosted Products

- [talentmesh](https://github.com/talentmesh-io) - AI-powered talent assessment platform

## Infrastructure Cost

| Component | Cost |
|-----------|------|
| 3x Contabo VPS 10 | ~€13.50/month (~$15) |
| 12 vCPU, 24GB RAM, 600GB SSD | |

---

*Powered by kubernetes, delivered with GitOps*
