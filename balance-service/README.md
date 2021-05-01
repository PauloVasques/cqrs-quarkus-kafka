# balance-service project

Este projeto utiliza Quarkus, um Supersonic Subatomic Java Framework.

Para saber mais sobre o Quarkus: https://quarkus.io/

## Rodando a aplicação em modo Dev

```
./mvnw quarkus:dev
```

## Empacotando e rodando a aplicação

Packing `./mvnw package`.
Irá gerar o arquivo `balance-service-1.0-SNAPSHOT-runner.jar` no diretório `/target`.

A aplicação será então executada com o comando  `java -jar target/balance-service-1.0-SNAPSHOT-runner.jar`.

## Criando um executável nativo

`./mvnw package -Pnative`

Ou, caso não tenha o GraalVM instalado, para rodar o executável nativo em um container: `./mvnw package -Pnative -Dquarkus.native.container-build=true`.

Para rodar o executável nativo: `./target/balance-service-1.0-SNAPSHOT-runner`

Para saber mais sobre executáveis nativos: https://quarkus.io/guides/building-native-image.