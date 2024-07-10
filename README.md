# planner-application-version-2

# Planner Application

Planner Application é uma aplicação desenvolvida em Java com Spring Boot, que permite gerenciar viagens e participantes. A aplicação fornece endpoints para criar, atualizar e visualizar viagens, além de gerenciar a confirmação e o convite de participantes.

## Funcionalidades

- **Gerenciamento de Viagens**: Criação, atualização e visualização de detalhes de viagens.
- **Gerenciamento de Participantes**: Convite e confirmação de participação em viagens.
- **Envio de Emails de Confirmação**: Envio de emails aos participantes confirmados.

## Estrutura do Projeto

```plaintext
planner-application
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── planner
│   │   │           ├── participant
│   │   │           │   ├── Participant.java
│   │   │           │   ├── ParticipantController.java
│   │   │           │   ├── ParticipantCreateResponse.java
│   │   │           │   ├── ParticipantData.java
│   │   │           │   └── ParticipantRepository.java
│   │   │           ├── trip
│   │   │           │   ├── Trip.java
│   │   │           │   ├── TripController.java
│   │   │           │   ├── TripCreateResponse.java
│   │   │           │   ├── TripRepository.java
│   │   │           │   └── TripRequestPayload.java
│   │   │           └── PlannerApplication.java
│   │   └── resources
│   │       └── application.properties
└── pom.xml
Endpoints
Viagens
Criar uma nova viagem
http

POST /trips
Payload:
json

{
    "destination": "string",
    "starts_at": "string (ISO_DATE_TIME)",
    "ends_at": "string (ISO_DATE_TIME)",
    "emails_to_invite": ["string"],
    "owner_email": "string",
    "owner_name": "string"
}
Obter detalhes de uma viagem
http

GET /trips/{id}
Atualizar uma viagem
http

PUT /trips/{id}
Payload:
json

{
    "destination": "string",
    "starts_at": "string (ISO_DATE_TIME)",
    "ends_at": "string (ISO_DATE_TIME)",
    "emails_to_invite": ["string"],
    "owner_email": "string",
    "owner_name": "string"
}
Confirmar uma viagem
http

GET /trips/{id}/confirm
Obter todos os participantes de uma viagem
http

GET /trips/{id}/participants
Participantes
Confirmar um participante
http

POST /participants/{id}/confirm
Payload:
json

{
    "name": "string",
    "email": "string"
}
Convidar um participante
http

POST /trips/{id}/invite
Payload:
json

{
    "name": "string",
    "email": "string"
}
Requisitos
Java 17 ou superior
Maven
Banco de dados compatível com JPA (por exemplo, H2, PostgreSQL, MySQL)

