# Kubernetes

## Orchestration Tool

여러 개의 컨테이너들을 관리하기 위한 툴

여러가지의 Orchestration Tool 이 있지만 효용성에서 Kubernetes가 높음

HA \( High availability \), FA \( Failover \) 을 지원하여 서버 구축으로서 제격

## 예제

{% code title="kube.yml" %}
```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-nginx
  labels:
    run: my-nginx
spec:
  ports:
  - port: 80
    protocol: TCP
  selector:
    run: my-nginx
---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-nginx
spec:
  selector:
    matchLabels:
      run: my-nginx
  replicas: 2
  template:
    metadata:
      labels:
        run: my-nginx
    spec:
      containers:
      - name: my-nginx
        image: nginx
        ports:
        - containerPort: 80
```
{% endcode %}

