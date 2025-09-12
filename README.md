# Fitness Tracker Microservices Application

A comprehensive fitness tracking application built with Spring Boot microservices architecture, featuring AI-powered recommendations and modern web technologies.

## 🏗️ Architecture Overview

This application follows a microservices architecture pattern with the following components:

### Backend Services
- **API Gateway** (Port 8080) - Central entry point with OAuth2 security
- **User Service** (Port 8081) - User management and authentication
- **Activity Service** (Port 8082) - Fitness activity tracking and storage
- **AI Service** (Port 8083) - AI-powered fitness recommendations using Gemini API
- **Eureka Server** (Port 8761) - Service discovery and registration
- **Config Server** (Port 8888) - Centralized configuration management

### Frontend
- **React Application** (Port 5173) - Modern web interface with Material-UI

## 🚀 Key Features

- **User Authentication**: OAuth2 integration with Keycloak
- **Activity Tracking**: Record and manage fitness activities
- **AI Recommendations**: Intelligent fitness suggestions using Google Gemini AI
- **Real-time Processing**: Asynchronous message processing with RabbitMQ
- **Service Discovery**: Automatic service registration and discovery
- **Centralized Configuration**: Environment-specific configuration management

## 🛠️ Technology Stack

### Backend
- **Spring Boot 3.x** - Microservices framework
- **Spring Security** - OAuth2 authentication
- **Spring Cloud Gateway** - API gateway
- **Spring Cloud Config** - Configuration management
- **Netflix Eureka** - Service discovery
- **MongoDB** - NoSQL database
- **RabbitMQ** - Message broker
- **Google Gemini AI** - AI recommendations

### Frontend
- **React 18** - Frontend framework
- **Material-UI** - UI component library
- **Redux Toolkit** - State management
- **React Router** - Client-side routing
- **OAuth2 PKCE** - Authentication flow

## 📊 Application Flow

1. **User Authentication**: Users authenticate via Keycloak OAuth2
2. **Activity Creation**: Users create fitness activities through the React frontend
3. **API Gateway**: Routes requests to appropriate microservices
4. **Activity Processing**: Activity Service validates and stores activities in MongoDB
5. **Message Publishing**: Activities are published to RabbitMQ for AI processing
6. **AI Analysis**: AI Service processes activities and generates recommendations
7. **Recommendation Storage**: AI recommendations are stored and served to users

## 🗄️ Database Schema

- **Activity Database**: Stores user fitness activities
- **Recommendation Database**: Stores AI-generated recommendations
- **User Database**: Stores user profiles and authentication data

## 🔧 Configuration

The application uses Spring Cloud Config for centralized configuration:
- Service-specific configurations in `configserver/src/main/resources/config/`
- Environment variables for sensitive data (API keys, database URLs)

## 🚦 Getting Started

### Prerequisites
- Java 17+
- Node.js 18+
- MongoDB
- RabbitMQ
- Keycloak (for OAuth2)

### Running the Application
1. Start infrastructure services (MongoDB, RabbitMQ, Keycloak)
2. Start Config Server (Port 8888)
3. Start Eureka Server (Port 8761)
4. Start microservices in any order
5. Start React frontend (Port 5173)

## 📝 API Endpoints

### User Service
- `GET /api/users/{userId}` - Get user profile
- `POST /api/users/register` - Register new user
- `GET /api/users/{userId}/validate` - Validate user existence

### Activity Service
- `POST /api/activities` - Create new activity
- `GET /api/activities` - Get user activities
- `GET /api/activities/{activityId}` - Get specific activity

### AI Service
- `GET /api/recommendations/user/{userId}` - Get user recommendations
- `GET /api/recommendations/activity/{activityId}` - Get activity-specific recommendations

## 🔒 Security

- OAuth2 authentication with Keycloak
- JWT token validation
- CORS configuration for frontend integration
- Service-to-service communication security

## 📈 Monitoring & Observability

- Service discovery through Eureka
- Centralized logging
- Health check endpoints
- Configuration management

This application demonstrates modern microservices patterns, cloud-native development practices, and integration of AI services in a real-world fitness tracking scenario.