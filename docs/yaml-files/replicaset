!!! Example "replicaset.yaml"

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: myapp-replicaset
  labels:
    app: myapp
spec:
  selector: 
    matchLabels:
      app: myapp
      # label set on the selector and pod template should be same
  replicas: 3
  template:
      metadata: 
        name: nginx-2
        labels: 
          app: myapp
      spec:
        containers:
          - name: nginx
            image: nginx
```