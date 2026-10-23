Voting App
Microsserviço responsável pelo registro e processamento de votos dentro do Sistema Distribuído de Eleições desenvolvido com Quarkus.

Este projeto faz parte da arquitetura distribuída do laboratório Quarkus da DIO e atua como responsável pela recepção, validação e persistência dos votos realizados pelos eleitores. Baseado no projeto Thiago Poiani disponível em lab-quarkus. 【1-151406】【2-30a0a5】

Arquitetura da Solução
┌─────────────────────────┐
│ election-management     │
│ Gerencia eleições       │
└─────────────┬───────────┘
              │
              ▼
┌─────────────────────────┐
│ voting-app             │
│ Recebe e valida votos  │
└─────────────┬───────────┘
              │
              ▼
┌─────────────────────────┐
│ result-app             │
│ Apuração dos votos     │
└─────────────────────────┘

Banco de Dados: MongoDB
Containerização: Docker
Framework: Quarkus
Responsabilidades
O microsserviço Voting App é responsável por:

Registrar votos de eleitores;
Validar se a eleição está ativa;
Garantir a integridade dos dados;
Persistir os votos no MongoDB;
Disponibilizar endpoints REST para operações de votação.
Tecnologias Utilizadas
Java
Quarkus
RESTEasy Reactive
MongoDB
Docker
OpenTelemetry
SmallRye Health
Maven
Extensões identificadas no projeto: RESTEasy Reactive, OpenTelemetry, SmallRye Health, Logging GELF e Context Propagation. 【1-151406】

Executando em Ambiente de Desenvolvimento
./mvnw compile quarkus:dev
Após iniciar a aplicação:

http://localhost:8080
Dev UI:

http://localhost:8080/q/dev
A interface Dev UI está disponível apenas em modo de desenvolvimento. 【1-151406】

Build da Aplicação
Pacote padrão:

./mvnw package
Execução:

java -jar target/quarkus-app/quarkus-run.jar
Empacotamento Uber Jar:

./mvnw package -Dquarkus.package.type=uber-jar
Execução:

java -jar target/*-runner.jar
*1-151406】

Executável N*tivo
Com GraalVM:

./mvnw package -Pnative```

Sem GraalVM local*

```bash
./mvnw package \
*Pnative \
-Dquarkus.native.container-build-true
Execução:

/target/voting-app-1.0. -SNAPSHOT-runner
1-151406】

Endpoints
egistrarVoto
POST /votes
``

Exemplo:

```json
{
 *"electionId": "1",
  "voterId": "100",
  "candidateId": "10"
}
## Consultar Votos por Eleição

`` http GET /votes/election/{electionId}


---

## Health*Check

Endpoint:

```http
GET*/q/health
Utilizado paramonitoramento da saúde da aplicação.

*--

Observ*bilidade
Este microsserviço possui suporte para:

OpenTelemetry
Lgs centralzados
Health Checks
Possbilitando monitoramento e rastreamnto distribuído. 1-151406】

Estrutura do Projeto
src
├── main
│   ├── java
│   │   ├── resource
│   │   ├── service
│   │   ├── repository
│   │   ├── dto
│   │   ├── entity
│   │   └── config
│   └── resources
└── test
## Aprendizados

Durante esteprojeto foram praticados conceitosde:

-*Microsserviços

APIs REST
Comuncaçãoentre Serviços
MongoDB
Quark*s
Docker
Observabilidade - Desenvolvimento Cloud Native
## Referências

Quarkus: https://quarkus.io
MongoDB: https://mongodb.com
Docker: https://docker.com -DIO: https://www.dio.me -Projeto Original https://github.com/thpoiani/lab-quarkus
Enzo Francisco

Desenvolvedor Back-End focado em Java, Microsserviços, Cloud Computing e Arquitetura de Software.