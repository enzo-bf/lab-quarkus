Sistema Distribuído de Eleições com Quarkus
📖 Sobre o Projeto
Este projeto consiste no desenvolvimento de um sistema distribuído e escalável para gerenciamento de eleições utilizando Java, Quarkus, MongoDB e Docker.

A aplicação é composta por múltiplos microsserviços responsáveis pelo gerenciamento das eleições, registro de votos e consulta de resultados, demonstrando conceitos modernos de arquitetura distribuída e aplicações cloud-native.

🚀 Tecnologias Utilizadas
Java
Quarkus
MongoDB
Docker
Docker Compose
REST APIs
Maven
OpenTelemetry
SmallRye Health
🏗 Arquitetura da Solução
┌─────────────────────────────┐
│ Election Management         │
│ Gerenciamento de Eleições   │
└─────────────┬───────────────┘
              │
              ▼
┌─────────────────────────────┐
│ Voting App                  │
│ Registro de Votos           │
└─────────────┬───────────────┘
              │
              ▼
┌─────────────────────────────┐
│ Result App                  │
│ Consulta de Resultados      │
└─────────────────────────────┘

               │
               ▼

          MongoDB
📂 Estrutura do Projeto
lab-quarkus
│
├── election-management
│
├── voting-app
│
├── result-app
│
├── docker-compose.yml
│
└── README.md
🔧 Microsserviços
Election Management
Responsável por:

Criar eleições
Atualizar eleições
Encerrar eleições
Consultar eleições
Gerenciar candidatos
Voting App
Responsável por:

Receber votos
Validar eleições ativas
Registrar votos
Garantir integridade das informações
Result App
Responsável por:

Apurar resultados
Totalizar votos
Exibir estatísticas
Apresentar vencedores
🐳 Executando com Docker
Subir ambiente:

docker compose up -d
Verificar containers:

docker ps
Parar ambiente:

docker compose down
▶️ Executando Localmente
Entrar em um dos microsserviços:

cd voting-app
Executar em modo desenvolvimento:

./mvnw compile quarkus:dev
A aplicação ficará disponível em:

http://localhost:8080
🔍 Conceitos Praticados
Durante este projeto foram explorados conceitos como:

Microsserviços
APIs REST
Arquitetura Distribuída
MongoDB
Docker
Quarkus
Desenvolvimento Cloud Native
Observabilidade
Monitoramento de Aplicações
📚 Aprendizados
Este laboratório proporcionou experiência prática no desenvolvimento de aplicações modernas utilizando o framework Quarkus, permitindo compreender como aplicações distribuídas podem ser construídas, implantadas e escaladas utilizando tecnologias amplamente adotadas pelo mercado.

💡 Melhorias Futuras
Implementação de autenticação JWT
Integração com Keycloak
Dashboard para acompanhamento das eleições
Integração com mensageria (Kafka)
Deploy em Kubernetes
Pipeline CI/CD
📸 Demonstração
Adicionar aqui imagens da aplicação, diagramas ou capturas de tela do ambiente em execução.

👨‍💻 Autor
Enzo Francisco

Desenvolvedor Back-End apaixonado por Java, Microsserviços, Cloud Computing e Arquitetura de Software.

🔗 Referências
https://quarkus.io
https://www.mongodb.com
https://www.docker.com
https://github.com/thpoiani/lab-quarkus
