![Status](https://img.shields.io/badge/Status-Finalizado-brightgreen)

# 📚 Fluxo de Reserva – Sistema de Reservas de Livros

Este projeto foi desenvolvido como parte de uma avaliação educacional com foco em arquitetura de microsserviços utilizando **Spring Boot**. Ele simula um sistema de biblioteca com funcionalidades de cadastro e reserva de livros.

---

## Estrutura do Projeto

O sistema é dividido em dois microsserviços:

| Serviço              | Descrição                                   |
|----------------------|---------------------------------------------|
| `book-service`       | Gerencia o catálogo de livros disponíveis.  |
| `reservation-service`| Gerencia as reservas feitas pelos usuários. |

Esses dois serviços foram organizados em um repositório monolítico para facilitar testes integrados, mas **também estão disponíveis individualmente**, caso deseje analisar separadamente:

- 🔗 [Repositório do book-service](https://github.com/GustavoZanardi15/book-service)
- 🔗 [Repositório do reservation-service](https://github.com/GustavoZanardi15/reservation-service)

---

## Estrutura de Diretórios

📁 fluxo-de-reserva/
├── 📁 book-service/
│ ├── 📁 src/
│ │ └── main/
│ │ ├── java/com/example/bookservice/
│ │ │ ├── controller/
│ │ │ ├── model/
│ │ │ ├── repository/
│ │ │ └── BookServiceApplication.java
│ │ └── resources/
│ │ └── application.properties
│ └── pom.xml
│
├── 📁 reservation-service/
│ ├── 📁 src/
│ │ └── main/
│ │ ├── java/com/example/reservationservice/
│ │ │ ├── controller/
│ │ │ ├── model/
│ │ │ ├── repository/
│ │ │ └── ReservationServiceApplication.java
│ │ └── resources/
│ │ └── application.properties
│ └── pom.xml
│
└── README.md


---

## 🛠 Tecnologias Utilizadas

- Java 17
- Spring Boot 3
- Spring Web
- Spring Data JPA
- Banco de dados H2 (em memória)
- Postman (para testes)
- Maven
- Git + GitHub

---

## Como Executar

### Pré-requisitos

- Java 17 instalado
- Maven instalado
- Uma IDE (IntelliJ, VSCode ou Eclipse)
- Postman instalado

### Passos

1. Clone o repositório:
```bash
git clone https://github.com/GustavoZanardi15/fluxo-de-reserva.git

Abra os dois diretórios (book-service e reservation-service) separadamente na sua IDE.
Execute a classe BookServiceApplication.java e ReservationServiceApplication.java.
Verifique se estão rodando nas portas padrão:
book-service: http://localhost:8081
reservation-service: http://localhost:8082

Integração Entre Serviços
O reservation-service se comunica com o book-service via REST usando RestTemplate, garantindo que apenas livros cadastrados possam ser reservados.

Como Testar com o Postman
1. Cadastrar um livro no book-service
POST http://localhost:8081/books
{
  "title": "Clean Code",
  "author": "Robert C. Martin",
  "isbn": "9780132350884"
}


Listar livros disponíveis
GET http://localhost:8081/books

Criar uma reserva no reservation-service
POST http://localhost:8082/reservations
{
  "bookId": 1,
  "user": "João da Silva"
}
A reserva só será registrada se o livro existir no book-service.

4. Listar todas as reservas
GET http://localhost:8082/reservations

Objetivo Educacional
Este projeto tem como objetivo demonstrar:
Arquitetura baseada em microsserviços
Separação de responsabilidades
Comunicação entre serviços via HTTP
Boas práticas com Spring Boot
Testes de API usando Postman


Este projeto está disponível de duas formas:
No repositório monolítico com ambos os serviços juntos:
🔗 fluxo-de-reserva

Separadamente, em seus respectivos repositórios:
🔗 book-service
🔗 reservation-service .
