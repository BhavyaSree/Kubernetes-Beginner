!!! Example "service-definition.yaml"

```yaml
apiVersion: v1
kind: Service
metadata:
  name: myapp-service
spec:
  type: NodePort
  ports:
    - targetPort: 80
      port: 80
      nodePort: 30008
  # service should be linked to a POD inorder to access
  selector: 
  # to select a POD, below are POD labels
    app: myapp
    type: front-end
```