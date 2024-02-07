# POD

    -> É o menor objeto do cluster kubernetes.
    -> É nele onde os containers podem ser executados (1+ containers).
    -> Pode criar várias réplicas do POD.
    -> 1 aplicação sua por POD. Mas pode usar Sidecars e outros recursos juntos.
    -> POD só tem o papel de executar, não tem papel de resiliência ou escalabilidade
    -> NAKED POD = POD sendo executado de maneira independente. Usado só para testes e troubleshooting.

## Criando POD via yaml:
    -> Possui 4 campos:
            apiVersion: 
            kind:
            metadata:
            spec:

    -> Objetos e suas versões:
        kubectl api-resources

    