LOGITRACK:

***O sistema***
- Sistema de monitoramento de robôs logísticos inteligentes, desenvolvido em Java Spring Boot. O projeto simula:
- Registro de robôs logísticos
- Gerenciamento de entregas
- Registro de eventos sensoriais
- Comunicação via API REST

O objetivo é fornecer uma base para simulação, rastreamento e gerenciamento de robôs em operações logísticas.

***Estrutura:***

src/
├── main/
│ ├── java/com/ags/logitrack/
│ │ ├── LogitrackApplication.java # Classe principal (Spring Boot)
│ │ ├── config/ # Configurações (CORS, inicialização de dados)
│ │ ├── controller/ # Controladores REST
│ │ ├── model/ # Modelos de domínio (Robô, Entrega, Evento)
│ │ ├── repository/ # Repositórios Spring Data JPA
│ │ └── service/ # Regras de negócio
│ └── resources/
│ └── application.properties # Configurações da aplicação
└── test/java/com/ags/logitrack/ # Testes unitários

***Tecnologias Utilizadas:***

- Java 17+
- Spring Boot (Web, Data JPA)
- H2 Database (banco em memória para simulações)
- Maven (gerenciamento de dependências)
