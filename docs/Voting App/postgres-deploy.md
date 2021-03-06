!!! Example "postgres-deploy.yaml"

    ```yaml
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: postgres-deploy
      labels:
        name: postgres-deploy
        app: demo-voting-app
    spec:
      replicas: 1
      selector:
        matchLabels:
          name: postgres-pod
          app: demo-voting-app    
      template: 
        metadata:
          name: postgres-pod
          labels:
            name: postgres-pod
            app: demo-voting-app
        spec:
          containers:
            - name: postgres
              image: postgres
              ports:
                - containerPort: 5432
                # 5432 is the default port for postgres image
              # environment variables to specify username and password for postgres
              env:
                - name: POSTGRES_USER
                  value: "postgres"
                - name: POSTGRES_PASSWORD
                  value: "postgres"
    ```