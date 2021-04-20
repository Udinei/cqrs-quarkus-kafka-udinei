# balance-service project

This project uses Quarkus, the Supersonic Subatomic Java Framework.


# Estrutura do projeto
- balance-service
    - gradle
    - src
        - main
            - docker
            - kotlin
              - banckaccount
                 - balance
            - resources
              - META-INF
        - test	

# Build da aplicação

<pre>gradle quarkusBuild</pre>

O arquivo <code>balance-service-1.0-SNAPSHOT-runner.jar</code> sera gerado
Para executar a aplicação com o jar gerado execute:

<pre>java -jar build/balance-service-1.0-SNAPSHOT-runner.jar</pre>

# Executando a aplicação em modo de desenvolvimento
Para tanto a estrutura de infra já deve estar rodando, com a execução do arquivo docker-compose.yml.
Na pasta do balance-service executar:
<pre>gradle quarkusDev</pre>
