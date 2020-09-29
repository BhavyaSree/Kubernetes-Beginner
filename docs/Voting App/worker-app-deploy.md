!!! Example "redis-pod.yaml"

    ```yaml
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: worker-app-deploy
      labels:
        name: worker-app-deploy
        app: demo-voting-app
    spec:
      replicas: 1
      selector:
        matchLabels:
          name: worker-app-pod
          app: demo-voting-app    
      template: 
        metadata:
          name: worker-app-pod
          labels:
            name: worker-app-pod
            app: demo-voting-app
        spec:
          containers:
            - name: worker-app
              image: kodekloud/examplevotingapp_worker:v1
    ```         

    