
use the yaml files under preparation directory for bootstrap

# Use with ArgoCD
https://gexperts.com/wp/bootstrapping-openshift-gitops-with-rhacm/
# Content

#Sample configmap to use at templates in order differentiate configs as per the cluster

```yaml
apiVersion: v1
data:
  ingressdefaultcount: "1"
  monitoring-sc: ocs-external-storagecluster-ceph-rbd
immutable: false
kind: ConfigMap
metadata:
  name: local-cluster
  namespace: acm-policies
```


