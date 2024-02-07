# K3D e Kubectl

## Criar cluster
  k3d cluster create cluster-estudo --servers 3 --agents 3 -p "8080:30000@loadbalancer" 

    -> Cria um cluster com 3 control planes, 3 nodes e binda a porta 8080 da maquina para o 30000, focado no container que será o load balancer.

  k3d cluster create meucluster --no-lb
    
    -> Cria um cluster sem o load balancer.
    -> O load balancer faz o balanceamento entre os pods

## Listar clusters
  k3d cluster list

## Ver nodes
  kubectl get nodes

## Criar pod
    kubectl apply -f pod.yaml -> É idempotente, cria, atualiza
    kubectl create -f pod.yamk -> Só cria, não atualiza

## Port bind
    kubectl port-forward pod/podname portamaquina:portapod

## Ver pod
    kubectl get pods
    kubectl get po -o wide -> Traz mais informações

## Deletar pod
    kubectl delete pod meupod 

