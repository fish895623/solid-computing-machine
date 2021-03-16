# AKS

## 로그인

[azure](https://portal.azure.com/) 사이트에 들어가 로그인 해준다.

## 쿠버네티스 클러스터 생성

![image](.gitbook/assets/aks/00-ShowPortalMenu.png)

위의 버튼을 누르면 아래의 리스트가 뜸

![image](.gitbook/assets/aks/01-OpenMenu.png)

![image](.gitbook/assets/aks/02-SelectKubernetesService.png)

쿠버네티스 서비스에 진입

쿠버네티스 쿨러스터를 추가

![image](.gitbook/assets/aks/03-CreateNewKubernetes.png)

자신이 원하는 ResourceGroup 이름을 설정 (나중에 azure-cli 에 필요함)

![image](.gitbook/assets/aks/04-CreateResourceGroup.png)

자신이 원하는 Kubernetes Cluster 이름 설정 (나중에 azure-cli 에 필요함)

한국 서버로 설정

![image](.gitbook/assets/aks/05-ClusterLocation.png)

노드 수가 1개일 경우 학생플랜은 무료이므로 1개로 수정

![image](.gitbook/assets/aks/06-ChangeNodeAndCheck.png)

검토 및 만들기를 눌러 생성가능한지 확인

![image](.gitbook/assets/aks/07-SaveIfValidationPass.png)

몇분후 Kubernetes Cluster 완성

![image](.gitbook/assets/aks/08-Finish.png)
