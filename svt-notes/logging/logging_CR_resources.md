# Changing CPU and memory limits for ClusterLogging CR

```yaml
  
apiVersion: "logging.openshift.io/v1alpha1"
kind: "ClusterLogging"
metadata:
  name: "example"
spec:
  managementState: "Managed"
  logStore:
    type: "elasticsearch"
    elasticsearch:
      nodeCount: 1
      storage: {}
      redundancyPolicy: "ZeroRedundancy"
      resources:
        limits:
          cpu: 500m
          memory: 4Gi
  visualization:
    type: "kibana"
    kibana:
      replicas: 1
  curation:
    type: "curator"
    curator:
      schedule: "30 3 * * *"
  collection:
    logs:
      type: "fluentd"
      fluentd: {}
```
