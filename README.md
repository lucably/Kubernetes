# Kubernetes

Estudo completo de Kubernetes(K8s)

# Cluster

o Cluster é formado por um "Nó Master" e tendo vários outros "Node", cada "Node" pode ser um computador e o "Nó Master" o computador Master. Dentro de cada Node, possui N Pods. O Computador Master (Nó Master) controla o que os outros Node irá processar.
Um Node pode ter por exemplo 3 aplicações:

1. Frontend
2. Backend
3. Db

No qual, essas 3 aplicações fique em um unico Pod e neste mesmo Pod divida 3 container, 1 para o Front, outro para Back e para o Db.
O Pod não executa a aplicação ele contem os container para que possa fazer a orquestração.

<div align="center">
    <img src="./assets/exemplo_Cluster.png"/>
</div>

Trabalhamos com arquivos YAML ou JSON.

# Kube Scheduler

Ele observa os Pods recem criados em nenhum Node atribuido, ai ele seleciona um Node para executa-lo.
Ele leva em consideração para tomar a decisão baseado nos recursos individuais, coletivos, permissoes, locatidade, recursos de hardware e software, se um Node estiver sobrecarregado o Scheduler ele tende a colocar em um outro Node.

<div align="center">
    <img src="./assets/exemplo_Schedule.png"/>
</div>

# Kubelet

Ele executa em cada Node, ele tem um Agente chamado Kubelet, ele é como se fosse um fiscal verificando se um container esta sendo executando dentro de um Pod, pois nenhum container pode executar fora de um Pod. Ele só gerenciar container criados pelo Kubernetes.

<div align="center">
    <img src="./assets/exemplo_Kubelet.png"/>
</div>

# Container Runtime Interface (CRI)

Ele é uma interface de plug-in que habilita o KUBELET ao usar uma variedade de container Runtime.
Lembrando que o Kubernetes não executa nenhum container.

O Kubelet entra em contato com o Runtime e o Runtime executa os containers, sempre precisa de um Runtime.

<div align="center">
    <img src="./assets/exemplo_Runtime.png"/>
</div>

# Minikube

Para realizar os testes precisara ter instalado o minikube e que ele esteja rodando.

Minikube => O Minikube é uma implementação leve do Kubernetes que cria uma VM em sua máquina local e implanta um cluster simples contendo apenas um nó.

Comando para execução: minikube start

# ReplicaSet

Controla o aumento e reduz as quanitdades de PODs.

# Comandos

1. CRIAÇÃO de um Pod atraves de um arquivo => kubectl (create ou apply) -f {ARQUIVO.yml}

2. DELETAR um pod => kubectl delete pods {ARQUIVO.yml}

3. VISUALIZAR pods => kubectl get pods

4. VISUALIZAR replicasets => kubectl get replicasets
