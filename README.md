# iac-aws-eks-fargate 
O objetivo desse projeto é criar um cluster EKS com Fargate via código

# Setup do ambiente
Instale os seguintes itens em sua maquina:
1.	Instalar o awscli
2.  Instalar o eksctl
3.	Instalar o Docker

# Criando o cluster
1. Abra o prompt de comando
2. Acesse a pasta raiz do projeto
3. Rode o comando: docker build -t deploy -f devops/iac/deploy/Dockerfile .
4. Rode o comando para validar o terraform: docker run \
	-e AWS_ACCESS_KEY_ID="your_access_key" \
	-e AWS_SECRET_ACCESS_KEY="your_secret_access_key" \
	-e AWS_REGION="your_region" \
	-e ENV="dev" \
	-e ENV_VERSION="v1" \
    -e FARGATE_VERSION="1.21" \
    -e NAME="k8s-rocketseat" \
	-e PROJECT_NAME="k8s" \
    -e PRODUCT_NAME="k8s" \
	-e CREATED_BY="devops-tools" \
	-e OWNER="squad-rocketseat" \
	-e ROLE="cluster" \
	-e TIER="gold" \
	-e CLUSTER_REGION="us-east-1" \
	deploy

# Destruindo o cluster
1. Abra o prompt de comando
2. Acesse a pasta raiz do projeto
3. Rode o comando: docker build -t destroy -f devops/iac/destroy/Dockerfile .
4. Rode o comando para validar o terraform: docker run \
	-e AWS_ACCESS_KEY_ID="your_access_key" \
	-e AWS_SECRET_ACCESS_KEY="your_secret_access_key" \
	-e AWS_REGION="your_region" \
	-e ENV="dev" \
	-e ENV_VERSION="v1" \
    -e FARGATE_VERSION="1.21" \
    -e NAME="k8s-rocketseat" \
	-e PROJECT_NAME="k8s" \
    -e PRODUCT_NAME="k8s" \
	-e CREATED_BY="devops-tools" \
	-e OWNER="squad-rocketseat" \
	-e ROLE="cluster" \
	-e TIER="gold" \
	-e CLUSTER_REGION="us-east-1" \
	destroy