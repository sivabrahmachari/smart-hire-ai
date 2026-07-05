Decision #001

Topic: Where should JWT validation happen?

Decision: The API Gateway will validate JWTs locally using the signing key (Phase 1).

Reason:

Reduces network calls.
Avoids making every request dependent on the Auth Service.
Improves latency and scalability.
Matches common production architectures.

Future Evolution: We can migrate to asymmetric keys (RS256) and OAuth2/OpenID Connect if Smart Hire AI grows into a larger platform.

Decision #002 – Why Spring Security is not added initially

Decision

Spring Security will not be included in the first version of the API Gateway.

Reason

The first milestone is to ensure the Gateway starts successfully and routes requests correctly.
Security will be introduced after the routing layer is stable.

Benefits

Easier debugging.
Smaller initial codebase.
Clear separation of milestones.
Better learning progression.

Future

Add Spring Security.
Implement JWT validation.
Add Role-Based Authorization.
Configure CORS.
Add Rate Limiting.

# Smart Hire AI - API Gateway

## Overview

API Gateway is the single entry point for all client requests in the Smart Hire AI platform.

## Responsibilities

- Route incoming requests to microservices
- Validate JWT tokens (Upcoming)
- Request logging (Upcoming)
- Global exception handling (Upcoming)
- CORS configuration (Upcoming)
- Rate limiting (Upcoming)
- Circuit breaker (Upcoming)
- Load balancing (Upcoming)

## Technology Stack

- Java 17
- Spring Boot 3.5.x
- Spring Cloud Gateway (WebFlux)
- Spring Boot Actuator
- Maven
- Docker (Infrastructure)

## Current Status

- Parent Maven integration ✅
- Spring Cloud Gateway configured ✅
- Actuator configured ✅
- Health endpoint working ✅
- Auth service routing working ✅

## Port

8080

## Next Features

- JWT Filter
- Global Logging Filter
- Global Exception Handler
- CORS Configuration
- Rate Limiting
- Service Discovery