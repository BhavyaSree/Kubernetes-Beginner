!!! Example "Deployment.yaml"

    ```yaml
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: myapp-deployment
      labels:
        tier: frontend
        app: nginx
    spec:
      selector: 
        matchLabels:
          app: myapp
          # label set on the selector and pod template should be same
      replicas: 6
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