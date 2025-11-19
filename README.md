apiVersion: v1
kind: Service
metadata:
  name: nodeport-demo
spec:
  type: NodePort
  selector:
    apps: test
  ports:
    - name: http
      port: 80
      nodePort: 30750    
