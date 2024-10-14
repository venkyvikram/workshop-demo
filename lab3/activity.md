## 1: (Online Playground)
https://killercoda.com/playgrounds/scenario/kubernetes

## 2: Deploy Nginx in Kubernetes
1. Run the following command to deploy an Nginx (web server) application:
```
kubectl create deployment nginx --image=nginx
```

2. Expose the application so you can access it:
```
kubectl expose deployment nginx --port=80 --type=NodePort
```

3. We will create an RBAC policy that gives users only the ability to view Pods in the system
```
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  name: pod-viewer
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "list"]
```

4. Bind the role to a user to enforce the permissions
```
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: pod-viewer-binding
subjects:
- kind: User
  name: "student"
roleRef:
  kind: Role
  name: pod-viewer
```

5. Create a Network Policy that limits communication so only specific Pods can connect
```
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: restrict-access
spec:
  podSelector:
    matchLabels:
      app: nginx
  ingress:
  - from:
    - podSelector:
        matchLabels:
          app: frontend
```