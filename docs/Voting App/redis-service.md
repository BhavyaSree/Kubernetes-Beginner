!!! Example "redis-service.yaml"

    ```yaml
    apiVersion: v1
    kind: Service
    metadata:
      name: redis
      labels:
        name: redis-service
        app: demo-voting-app
    spec:
      ports:
      - port: 6379
        targetPort: 6379
        # No need of NodePort as it is an internal service
      selector:
        name: redis-pod
        app: demo-voting-app
    ```