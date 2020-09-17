!!! Example "postgres-service.yaml"

    ```yaml
    apiVersion: v1
    kind: Service
    metadata:
      name: db
      # db name is given according to the code(host:db)
      labels:
        name: postgres-service
        app: demo-voting-app
    spec:
      ports:
      - port: 5432
        targetPort: 5432
        # No need of NodePort as it is an internal service
      selector:
        name: postgres-pod
        app: demo-voting-app
    ```
