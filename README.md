

# Use with ACM Subscription

-   Add the user who will create the suscription to the open-cluster-management:subscription-admin rolebinding

Example:

```
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: open-cluster-management:subscription-admin
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: open-cluster-management:subscription-admin
subjects:
- apiGroup: rbac.authorization.k8s.io
  kind: User
  name: kube:admin
- apiGroup: rbac.authorization.k8s.io
  kind: User
  name: system:admin
```


- Provide any name for the Subscription name

- "acm-policies" as the namespace

- Path should be "bootstrap/local-hub"

![Alt text](acm_sub.png "ACM Subscription")

Select "Deploy only to local cluster" 

![Alt text](acm_sub_2.png "ACM Subscription")


# Use with ArgoCD

Please see the section "INTEGRATING WITH OPENSHIFT GITOPS (ARGOCD)" at the link https://cloud.redhat.com/blog/generating-governance-policies-using-kustomize-and-gitops to enable policy-generator plugin. 

# Content

TESTED WITH OCP 4.12

## Cluster Configs

- Tolerates any tains for DNS daemon pods

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

- with LSO backend

- with thin backend

- Noobaa only deployment

- Migration Toolkit For Container installation 

- Node Healthcheck and Self Node Remediation installation (For Cloud Agnostic Installations)

- NMState installation and bridge configurtion 

- OCP Compliance installation with ocp-cis and ocp-cis-node profiles

- Logging/Log Forwarder installation and Configuration

- QUAY installation/configuration to the Hub cluster


