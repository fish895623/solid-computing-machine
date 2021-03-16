# Azure-Cli

## Azure-Cli 설치

### Chocolatey 를 이용한 설치 \(추천\)

powershell 을 관리자 권한으로 실행하여 아래 스크립트들을 azure-cli 설치도구를 설치한다.

\(단축키 WIN + X, A\)

```text
Set-ExecutionPolicy AllSigned
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

아래 명령어를 입력해 azure-cli 툴을 설치한다.

```bash
choco install azure-cli -y
```

### 직접 설치파일을 다운로드 하여 설치

Azure 제어하기 위한 Cli Command Line Interface 툴 설치

[Download Azure-Cli](https://aka.ms/installazurecliwindows)

## Azure 로그인 방법

```bash
az login
```

## AKS 제어 방법

### 컨트롤러 설치

아래 명령어를 통해 kubectl \( kubernetes control \) 설치한다.

```bash
az aks install-cli
```

### 클러스터 접속

```bash
az aks get-credentials --resource-group "리소스 그룹 이름" --name "클러스터 이름"
```

