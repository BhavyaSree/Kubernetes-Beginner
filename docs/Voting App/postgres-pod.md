!!! Example "postgres-pod.yaml"

    ```yaml
    apiVersion: v1
    kind: Pod
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