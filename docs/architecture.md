# Architecture Overview

The project follows a modular architecture pattern aimed at maintaining separation of concerns, scalability, and maintainability. It is structured into distinct layers, each serving a specific purpose in the application flow.

## 📁 Directory Structure 

###  Application Layer 

- **Services**: Contains service classes responsible for implementing business logic.
- **Interfaces**: Defines contracts for data access and operations.

###  Domain Layer 

- **Entities**: Defines core business entities like `Usuario`, `Cliente`, and `Pedido`.
- **Interfaces**: Defines interfaces for repositories, specifying how data should be accessed and manipulated.

### Infrastructure Layer 

- **Repositories**: Provides concrete implementations of repositories, adhering to the interfaces defined in the domain.
- **Context**: Database context configuration.
- **IoC**: Service configuration and Dependency Injection setup.

### Security Layer 

- **Configuration**: Contains configurations such as security settings (`SecurityConfig`) and token management (`TokenService`), including the use of `Bearer` token type.

### WebApi Layer 

- Acts as the presentation layer, exposing RESTful endpoints.
- **Controllers**: Handles incoming requests, delegates to services, and returns appropriate responses.

## 🔑 Key Components 

- **Services**: Implement business rules and orchestrate data access.
- **Entities**: Represent core business objects with properties and behavior.
- **Repositories**: Provide interfaces for data access operations, allowing flexibility in data storage implementations.
- **Controllers**: Serve as the entry points for API requests, enforcing security and validation rules.

## 🔐 Integration with JWT 

The architecture integrates JWT (JSON Web Token) for authentication and authorization purposes. Endpoints prefixed with "user" and "store" require `Bearer` type JWT tokens for access, managed by the `TokenService` configured in the root `Security` directory.
