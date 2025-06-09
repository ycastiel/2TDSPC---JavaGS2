# 🌐 SafeZone Admin

Sistema administrativo da plataforma **SafeZone**, desenvolvido com Spring Boot + Thymeleaf, integrando funcionalidades avançadas como:

- Integração com IA (Spring AI)
- Comunicação assíncrona com RabbitMQ
- Segurança com OAuth2 (Login via GitHub)
- Banco de dados Oracle
- Testes automatizados
- Estilo clean e responsivo com CSS modularizado

---

## 🔧 Como executar o projeto localmente

### 1. Pré-requisitos

- Java 17+
- Maven
- Docker + Docker Compose
- Oracle DB (acesso FIAP)
- RabbitMQ via Docker (instruções abaixo)

### 2. Subir RabbitMQ com Docker

Crie um arquivo `docker-compose.yml` na raiz do projeto com:

```yml
services:
  rabbitmq:
    image: rabbitmq:3-management
    ports:
      - "5672:5672"
      - "15672:15672"
    environment:
      RABBITMQ_DEFAULT_USER: guest
      RABBITMQ_DEFAULT_PASS: guest

Execute: docker compose up -d

Acesse o painel: http://localhost:15672
Login: guest • Senha: guest

Rodar o projeto: ./mvnw spring-boot:run

Acesso da plataforma - 
Acesse via: http://localhost:8080

Faça login via GitHub OAuth2

Para rodar os testes automatizados -
./mvnw test

Estrutura de testes:

Testes de serviço (JUnit + Mockito)

Testes de integração de controller

Cobertura: Abrigo e Alerta (CRUD + IA + RabbitMQ)

✅ Spring AI + OpenAI (via OpenRouter)
Recomendações inteligentes ao salvar alertas.
Configuração via application.properties:

properties
Copiar
Editar
spring.ai.openai.api-key=sk-xxxxx
spring.ai.openai.base-url=https://openrouter.ai/api/v1
spring.ai.openai.chat.model=openrouter/openai/gpt-3.5-turbo
✅ RabbitMQ
Sender: RabbitMQSender

Listener: RabbitMQListener

Fila: alerta.fila

🧪 Funcionalidades principais
CRUD de Abrigos e Alertas

IA recomendadora para alertas críticos

Testes com cobertura completa

Login OAuth2 (GitHub)

Estilização moderna com CSS por domínio (alerta.css, abrigo.css...)

📂 Estrutura de pastas
bash
Copiar
Editar
src/
 └── main/
      ├── java/com.safezone.admin/
      │    ├── controller/
      │    ├── service/
      │    ├── repository/
      │    ├── config/
      │    └── model/
      └── resources/
           ├── static.css.*
           └── template.*
