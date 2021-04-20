# Projeto transaction-service

This project uses Quarkus, the Supersonic Subatomic Java Framework.

# Stack
- Java 15
- Quarkus
- Kotlin 1.3.61
- Docker
- Docker compose
- Kafka 2.1.0
- mongoDB
- PostgreSQL
- Zookeeper
- Gradle 6.8

# Estrutura do projeto
- transaction-service
    - gradle
    - src
        - main
            - docker
            - kotlin
                - bankaccount
                    - transaction
            - resources
                - db
                    - migration
                - META-INF
                    - resource
        - native-test
        - test

# Configurar BD local
No arquivo Applications.properties informar:
banco, usuario, e senha local do PostgreSql

# Build da aplicação

<pre>gradle quarkusBuild</pre>

O arquivo <code>transaction-service-1.0-SNAPSHOT-runner.jar</code> será gerado
Para executar a aplicação com o jar gerado execute<code>java -jar build/transaction-service-1.0-SNAPSHOT-runner.jar</code>

# Start da aplicação em tempo de desenvolvimento
Na pasta transaction-service executar:
<pre>gradle quarkusDev</pre>

O Flyway vai executar o arquivo <code>init.sql</code> que contém o sql abaixo:
<pre>
CREATE DATABASE bankaccount;
CREATE USER bankaccount WITH ENCRYPTED PASSWORD 'bankaccount';
GRANT ALL PRIVILEGES ON DATABASE bankaccount TO bankaccount;
</pre>

criando o BD "bankaccount" no PostgreSQL, usuario, senha e privilegios
A conexão d Database (executando no intelliJ) do flyway  deve ser:
<pre>Virtual ISO-92 SQL</pre>

O flyway vai executar o sql da migration que esta em:
<code>resources -> bd -> migration -> V1.0.0__transactions_schema.sql</code>
e criar a tabela abaixo:
<pre>
CREATE TABLE transactions (
id varchar not null primary key,
account_id varchar not null,
description varchar not null,
type varchar not null,
value decimal not null
);
</pre>


# Referências
*[Flyway](https://quarkus.io/guides/flyway)
*[kafka](https://kafka.apache.org/quickstart)


