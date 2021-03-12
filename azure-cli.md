# Azure-Cli

## Azure-Cli 설치

Azure 제어하기 위한 Cli Command Line Interface 툴 설치

[Download Azure-Cli](https://aka.ms/installazurecliwindows)

## Azure 로그인 방법

```bash
az login
```

---

## AKS 제어 방법

### 컨트롤러 설치

아래 명령어를 통해 kubectl ( kubernetes control ) 설치한다.

```bash
az aks install-cli
```

### 클러스터 접속

```bash
az aks get-credentials --resource-group "리소스 그룹 이름" --name "클러스터 이름"
```
