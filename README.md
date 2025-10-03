
use the yaml files under preparation directory for bootstrap

# Use with ArgoCD
https://gexperts.com/wp/bootstrapping-openshift-gitops-with-rhacm/
# Content

#Sample configmap to use at templates in order differentiate configs as per the cluster

apiVersion: v1
data:
  ingressdefaultcount: "1"
  monitoring-sc: ocs-external-storagecluster-ceph-rbd
immutable: false
kind: ConfigMap
metadata:
  name: local-cluster
  namespace: acm-policies



TESTED WITH OCP 4.12

## Cluster Configs

- Tolerates any taints for DNS daemon pods

- Encyrypts etcd

- Creates a etcd backup

- Configures chronyd for master and workers

- Sets the timezone 

- Configured route sharding if required

- Increases the interface card buffers (for Baremetal deployments)

- Ingress

Configures the replica number

Other options:

Tolerates the taints for router nodes

Node Placement

- Internal Registry Options:

Use noobaa backend

Use Cephfs backend

- Kubelet config; Garbage collection

Other options:

Configure max pods per node

- Use Ldap Group Operator for LDAP group sync

- Configure LDAP (non-TLS only for now)

- Configure monitoring/Alert Manager (includes tolerations for infra nodes)

- User workload monitoring

- Configures proxy for additional CAs

- Tuned operator configuration to increase the kernel TCP buffers (for Baremetal Deployments)
  
## Operator Catalog

- ACS central installation to the hub cluster

- ACS secured cluster installtion to the managed clusters

- ACM observability installation

- CNV installation (For Baremetal Clusters)

- ODF installation

Options:

with LSO backend

with thin backend

Noobaa only deployment

- Migration Toolkit For Container installation 

- Node Healthcheck and Self Node Remediation installation (For Cloud Agnostic Installations)

- NMState installation and bridge configurtion 

- OCP Compliance installation with ocp-cis and ocp-cis-node profiles

- Logging/Log Forwarder installation and Configuration

- QUAY installation/configuration to the Hub cluster


