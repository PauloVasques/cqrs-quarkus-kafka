# Java and Kubernetes Project for DIO

Projeto desenvolvido para a plataforma DigitalInnovation One.

Abaixo informações e instruções de como rodar a aplicação.

## Aplicação

Simulação de um cenário de conta bancária onde o usuário adiciona uma transação de entrada ou saída, que será processada em um evento assíncrono e a arquitetura CQRS irá recalcular a conta bancária do usuário. O usuário também poderá solicitar seu saldo bancário.


## Deploying nos serviços externos

```
docker-compose up -d --build
```
Irá realizar o deploy de quatro docker containers no seu ambiente com PostgreSQL, Kafka and Zookepper (required by Kafka)

Depois do deploying do Kafka, é necessário [criar o tópico no cluster Kafka](https://kafka.apache.org/quickstart).

## Testando a aplicação

#### Executando um request CURL para criar uma transação de entrada
```
curl -X POST -H "Content-Type: application/json" -d @income-transaction.json http://localhost:8080/transactions
```
#### Executando um request CURL para criar uma transação de saída
```
curl -X POST -H "Content-Type: application/json" -d @expense-transaction.json http://localhost:8080/transactions
```
#### Executando um request CURL para consultar o saldo bancário
```
curl http://localhost:8081/balance\?accountId\=wesley | json_pp
```

### Referência

https://github.com/wesleyfuchter/cqrs-quarkus-kafka

