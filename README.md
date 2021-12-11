# Jenkins CI/CD

Jenkins é uma ferramenta de CI/CD de codigo aberto, para automatizar a integração e entrega do codigo.

## Rodando o jenkins

Ao executar o `compose` (docker-compose.yml) irá subir o jenkins e a senha de primeiro acesso estará no fim do log.

```bash
docker-compose up --build
```

## ci-agent
A parte do `agent`, que esta comentada no `compose` (docker-compose), pode ser utilizada para fazer o deploy em outra maquina.

O Dockerfile esta escrito para fazer o deploy de uma estrutura via `compose` no agent.

Caso queira que o deploy seja feito na maquina `host` descomentar as linhas **11**/**12** e "expor" a API do docker no host.

Como alternativa pode utilizar o `agent` [oficial](https://hub.docker.com/r/jenkins/agent/) do jenkins.

# Remover containers

```bash
docker-compose down -v --rmi local
```


#### Referencias
- https://docs.docker.com/compose/compose-file/compose-file-v3/
- https://docs.docker.com/engine/reference/builder/
- https://docs.docker.com/compose/reference/up/
- https://docs.docker.com/compose/reference/down/
- https://hub.docker.com/r/jenkins/jenkins
- https://github.com/jenkinsci/docker/blob/master/README.md
- https://www.jenkins.io/doc/book/installing/docker/
- Complementar (Agents)
    - https://hub.docker.com/r/jenkins/agent/
    - https://www.jenkins.io/doc/book/using/using-agents/