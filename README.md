Fitness Tracker Microservices Application

A fitness tracking platform built using Spring Boot microservices with a React-based frontend. The system is designed to provide modular services for user management, activity tracking, and intelligent recommendations.

🏗️ Architecture

This project follows a microservices-based design with the following key modules:

Backend Services

API Gateway (8080): Entry point for all requests, secured with OAuth2

User Service (8081): Handles user profiles and authentication

Activity Service (8082): Manages fitness activities and storage

Recommendation Service (8083): Generates fitness suggestions with AI

Eureka Server (8761): Service discovery and registration

Config Server (8888): Centralized configuration

Frontend

React (5173): Modern web client built with Material-UI

🚀 Features

Secure authentication and authorization (OAuth2 / Keycloak)

Activity logging and management

Personalized fitness recommendations (AI-powered)

Real-time asynchronous processing with RabbitMQ

Service discovery and centralized configuration

Modern React-based frontend with Material-UI

🛠️ Tech Stack
Backend

Spring Boot 3.x – Core microservices framework

Spring Security (OAuth2) – Authentication and authorization

Spring Cloud Gateway & Config – API routing & centralized config

Netflix Eureka – Service discovery

MongoDB – Data persistence

RabbitMQ – Message broker

AI Model Integration (Gemini/LLM API) – Personalized recommendations

Frontend

React 18 – UI framework

Material-UI – Components and styling

Redux Toolkit – State management

React Router – Routing

OAuth2 PKCE Flow – Authentication

📊 Flow Overview

User signs in via OAuth2 (Keycloak).

Activities are created and sent to the backend.

API Gateway routes the request to the correct service.

Activity Service validates and stores the activity in MongoDB.

Events are published to RabbitMQ for asynchronous processing.

Recommendation Service analyzes activities and generates suggestions.

Results are stored and delivered back to the user via frontend.

🗄️ Databases

Users: Profiles and authentication data

Activities: Logged fitness activities

Recommendations: AI-generated fitness advice

🔧 Setup & Configuration
Requirements

Java 17+

Node.js 18+

MongoDB

RabbitMQ

Keycloak (OAuth2 provider)

Running the System

Start required infrastructure (MongoDB, RabbitMQ, Keycloak).

Start Config Server.

Start Eureka Server.

Run each microservice.

Launch React frontend.

📝 API Endpoints (Sample)
User Service

GET /api/users/{userId} → Fetch user profile

POST /api/users/register → Register a new user

Activity Service

POST /api/activities → Add activity

GET /api/activities → Fetch all activities

Recommendation Service

GET /api/recommendations/user/{userId} → Fetch recommendations for a user

🔒 Security

OAuth2 + JWT-based authentication

Keycloak for identity management

CORS-enabled frontend integration

Secure service-to-service communication

📈 Monitoring

Health checks for all services

Centralized logs

Eureka-based service discovery

Config Server for environment-specific configs

✨ This project demonstrates cloud-native microservices architecture combined with AI-driven personalization, showing how modern backend and frontend technologies can work together in a scalable fitness tracking solution.
