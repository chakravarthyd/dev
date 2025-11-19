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

---
apiVersion: v1
kind: Pod
metadata:
  name: nodeport-pod
  labels:
    apps: test
spec:
  containers:
  - name: cont1
    image: nginx
    ports:
      - containerPort: 80    
