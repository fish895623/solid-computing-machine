# Kubernetes

## Orchestration Tool

여러 개의 컨테이너들을 관리하기 위한 툴

여러가지의 Orchestration Tool 이 있지만 효용성에서 Kubernetes가 높음

HA \( High availability \), FA \( Failover \) 을 지원하여 서버 구축으로서 제격

## 예제

**`kube.yml`**

```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-nginx-service # 서비스 이름 지정
  labels:
    run: my-nginx
spec:
  ports: # 로드밸런서를 통해 외부로 노출할 포트 지정
  - port: 80
    protocol: TCP
    targetPort: 80
  selector:
    run: my-nginx
  type: LoadBalancer
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
        image: nginx # 도커 이미지
        ports:
        - containerPort: 80 # 외부로 노출할 컨테이너 포트
        resources: # 자원 제한
          limits:
            cpu: 10m
            memory: 100Mi
```

아래 명령어를 실행하면 nginx가 실행됨

```bash
kubectl apply -f kube.yml
```

노드에 서비스가 올라갔음

```bash
kubectl get services
# NAME                 TYPE           CLUSTER-IP     EXTERNAL-IP      PORT(S)          AGE
# kubernetes           ClusterIP      10.0.0.1       <none>           443/TCP          19h
# my-nginx             LoadBalancer   10.0.98.140    ***.***.***.***  80:30488/TCP     4m12s
```

브라우저에 EXTERNAL-IP 를 입력하면 nginx가 켜짐
