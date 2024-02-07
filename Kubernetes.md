# Kubernetes

## Criação
 -> Criado pelo Google, como projeto privado Borg (2014)
 -> Em 2015, a Google abriu o código e doou para a Linux Foundation.
 -> Quando o projeto foi doado, ele foi renomeado para Kubernetes(K8S)
 -> Kubernetes vem do grego, sua tradução é timoneiro
 -> As 7 pontas do timão no logo, representa o nome inicial: Project 7 of 9

## Capacidades
    -> Permite executar aplicações de forma escalável e resiliente
    -> Permite escalar vertical e horizontalmente
    -> Service Discovery: Ponto de comunicação entre containers
    -> Gerenciamento de configuração baseado em arquivos e variáveis de ambientes
    -> Habilidade de usar Secrets/Dados Criptografados
    -> Self Healing
    -> Não é apenas um orquestrador de containers. 
    -> É capaz de ser otimizado
    -> Serve para execução de aplicação, mas também como solução de plataforma
    -> Facilita o ciclo de vida e o desenvolvimento de software
    -> Ferramente muito mais a frente que suas concorrentes no mercado
    -> Ferramenta de orquestração mais utilizadas pro mercado

## Arquitetura
    -> Cluster Kubernetes = Conjunto de Máquinas
    -> Uma máquina pode exercer um dos dois papéis: Control Plane e Worker Node
    -> Control Plane é quem gerencia o cluster Kubernetes (Maestro da Orquestra)
    -> Worker Node é quem executa os containers (Músico da Orquestra)
    -> Cada máquina tem seus elementos específicos

### Control Plane
    -> API Server - Faz a comunicação externa e interna com o cluster Kubernetes. É através dele que se comunica via API ou kubectl
    -> Scheduler - Recebe os elementos que devem ser criados pelo API Server e elege onde esse cara será executado (em qual Worker Node)
    -> ETCD - Banco chave e valor que é utilizado para armazenar informações do Kubernetes. Se quiser fazer backup de um cluster Kubernetes, faz backup do ETCD. Não se acessa as infos do etcd diretamente, usa o API Server pra isso.
    -> Controller Manager - Gerencia os controladores do cluster. O controlador é responsável por uma área do cluster kubernetes. Verifica os recursos no kubernetes e caso esses recursos sejam alterados, toma uma decisão. Ex: Replica Set, é um controlador que verifica a qtd de réplicas sendo executadas.
    -> Cloud Controller Manager - Gerencia os recursos de nuvem. Quando criar um serviço que precisa de um ip público, o CCM é quem gerencia.

### Worker Node
    -> Kube-Proxy - Faz a comunicação de rede do kubernetes
    -> Kubelet - Faz a comunicação do kubernetes com o container-runtime para executar o container. O container runtime pode ser qlq um que implementa o cri (Container Runtime Interface. Ex: Cri-o, ContainerD...)

### Interfaces do Kubernetes

#### CRI
    -> Container Runtime Interface
    -> Permite que o Kubernetes se comunique com containers por uma interface
    -> Antigamente o Kubernetes usava o Docker
    -> O Docker não implementa o CRI
    -> Como o Docker usa o ContainerD por baixo dos panos, é possível usar uma imagem docker com o Kubernetes

#### CNI
    -> Container Network Interface
    -> Faz a comunicação com o software que faz o gerenciamento de redes dos containers
    -> Provisiona o IP para o POD
    -> Ex: WaveNet, Calico, Flannel

#### CSI
    -> Container Storage Interface
    -> Faz com que o Kubernetes se comunique com serviços de storage de dados/volumes
    -> EX: AWS, Google, Azure, Longhorn(Rancher)

### Kubernetes HA
    -> Alta disponibilidade
    -> Precisa se preocupar com a disponibilidade do cluster.
    -> Necessário ter mais de 1 Control Plane no Kubernetes. O ideal é pelo menos 3.

### Como criar um cluster Kubernetes
    -> On Premise
    -> Como serviço: Cloud Provider, AKS, EKS, OKS, GKS
    -> Kubernetes Local: K3D, Minikube, Kind

#### Kubernetes como serviço
    -> Gerenciam o control plane, worker nodes
    -> Atualizações de Linux
    -> Melhor opção


  