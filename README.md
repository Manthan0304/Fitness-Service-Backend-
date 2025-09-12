git push -u origin main --force
🏗️ Project Architecture Summary
Microservices:
API Gateway (8080) - OAuth2 security & routing
User Service (8081) - User management
Activity Service (8082) - Fitness tracking
AI Service (8083) - Gemini AI recommendations
Eureka Server (8761) - Service discovery
Config Server (8888) - Centralized configuration
Frontend:
React App (5173) - Material-UI interface
Infrastructure:
MongoDB - Activity & recommendation storage
RabbitMQ - Async message processing
Keycloak - OAuth2 authentication