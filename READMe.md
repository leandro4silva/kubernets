# Cenario

- Temos uma aplicação executando em container
    - A execução em container traz algumas preocupações

- Temos varias aplicações executando em container
    - Mais algumas preocupações

# Problemas 

- E se um container falhar na execução?

- E se precisarmos de varios container executando a mesma aplicação?

- E se precisarmos de um fluxo elastico?

- E se forem varias aplicacoes com varios containers?

- E o controle de uso de recursos de um container?

# Escalabilidade 

- Horizontal
    - HPA: O Horizontal Pod Autoscaler (HPA) ajusta automaticamente a quantidade de réplicas de pods com base no uso de CPU, memória ou métricas personalizadas.
    ![alt text](image1.png)
- Vertical
    - VPA: O Vertical Pod Autoscaler (VPA) ajusta automaticamente os recursos (CPU e memória) solicitados pelos containers, sem alterar o número de pods.
     ![alt text](image2.png) 

# Quando optar pelo kubernets

- Se sua aplicação é composta por vários microservices, APIs, workers, filas, etc

- Escalabilidade automática (Aumentar pods qunado o tráfego cresce)

- Alta disponibilidade (K8s mantem sua aplicação no ar mesmo quando o container ou nó morre e faz rollback automático quando um deploy dá errado)

# Quando não usar kubernets

- Aplicação monolito simples

- Pouca carga

# Cluster Gerenciado
    - AWS (EKS), GCP (GKE), AZURE (AKS) - (Pagos)

# Cluster Não Gerenciado
    - On-Premises
    - Na sua máquina

# Tools
    - kubectl
    - lens
    - k9s
    - kind
    - minikube

# Commands

- Criar Cluster
```bash
kind create cluster --name=cluster-1
```

- Visualizar Nodes
```bash
kubectl get nodes
```

- Deletar Cluster
```bash
kind delete cluster --name=cluster-1
```

- Criar usando config
```bash
kind create cluster --config kind.yaml --name=cluster1
```

- Criar Namespace
```bash
kubectl create namespace first-app
```