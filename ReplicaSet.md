# Replica Set
    -> Fica acima do POD
    -> Cria e gerencia a quantidade de replicas de um POD
    -> Pode acontecer de não conseguir colocar a qtd de réplicas? Sim, pode haver falta de recursos.
    -> Quando um pod é eliminado, o ReplicaSet, cria um outro pod no lugar, para ter o numero de replicas selecionadas.
    -> Se tiver mais pod do que replicadas definidas, o ReplicaSet remove pod até ter a quantidade correta de réplicas.
    -> Ele sempre vai tentar ter a qtd de réplicas que foi definido
    -> Da escalabilidade, resiliencia, mas não atualiza a versão automaticamente. Precisa deletar para criar um novo com a atualização.