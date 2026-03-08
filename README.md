# Twitch Data Aggregation Platform

Spring Boot | React | MySQL | AWS | Docker

A full stack web application that aggregates Twitch data (streams, videos, clips) through the Twitch API and provides search and personalized recommendations.

The system consists of a Spring Boot backend and a React frontend. It supports RESTful APIs, persistent storage with MySQL, caching optimization, and cloud deployment.

---

## System Architecture

The application follows a layered backend architecture.

Client  
→ React Frontend  
→ Spring Boot REST Controllers  
→ Service Layer  
→ Repository Layer  
→ MySQL Database  

External Twitch data is retrieved through the Twitch API using an OpenFeign HTTP client.

Caching and authentication are integrated using Spring Boot infrastructure components.

---

## Tech Stack

### Backend
- Java  
- Spring Boot  
- Spring Security  
- Spring Data JDBC  
- OpenFeign HTTP Client  
- Caffeine Cache  

### Frontend
- React  
- JavaScript  
- HTML / CSS  
- Ant Design  

### Database
- MySQL  
- Amazon RDS  

### Infrastructure
- Docker  
- AWS App Runner  

### External API
- Twitch API  

---

## Key Features

### Twitch Data Aggregation
The backend retrieves Twitch resources including streams, videos, and clips through the Twitch API.

Aggregated data is processed and served through RESTful APIs, supporting more than **1,000+ Twitch data items**.

---

### RESTful API Backend
Spring Boot controllers expose REST endpoints for:

- searching Twitch resources  
- managing user favorites  
- retrieving personalized recommendations  
- handling user authentication  

The API layer separates controller logic from business logic through service classes.

---

### Database Storage
MySQL is used for persistent storage and supports CRUD operations for:

- users  
- favorite records  
- Twitch resource metadata  

The database is hosted on **Amazon RDS** for scalability and reliability.

---

### Frontend Interface
The frontend is implemented using **React and Ant Design**.

Key user interactions include:

- searching Twitch resources  
- user login and authentication  
- managing favorite collections  

The frontend communicates with backend APIs through HTTP requests.

---

### Backend Caching
A caching layer using **Caffeine** reduces redundant Twitch API calls and improves system response performance.

Frequently accessed Twitch resource data is cached in memory.

---

### Cloud Deployment
The application is containerized using **Docker** and deployed to **AWS App Runner**.

The backend service runs in a containerized environment and connects to the MySQL database hosted on Amazon RDS.

---

## Project Structure

The backend follows a layered architecture separating API endpoints, business logic, and data access.

### Backend (Spring Boot)

```
twitch
├── controller
│   ├── ItemController
│   ├── GameController
│   ├── FavoriteController
│   ├── RecommendationController
│   └── UserController
│
├── service
│   ├── ItemService
│   ├── TwitchService
│   ├── FavoriteService
│   ├── RecommendationService
│   └── UserService
│
├── repository
│   ├── ItemRepository
│   ├── FavoriteRecordRepository
│   └── UserRepository
│
├── client
│   └── TwitchClient (Feign HTTP client for Twitch API)
│
├── config
│   ├── SecurityFilterChain
│   ├── AppConfig
│   └── PasswordEncoder
│
└── model
    ├── User
    ├── Item
    └── FavoriteRecord
```
The frontend communicates with the backend through RESTful APIs to retrieve Twitch resources and manage user interactions.
### Frontend (React)

```
twitchfe
├── src
│   ├── components
│   │   ├── Home
│   │   ├── Login
│   │   ├── Register
│   │   ├── MenuItem
│   │   └── PageHeader
│   │
│   ├── pages
│   │   ├── SearchPage
│   │   ├── FavoritePage
│   │   └── RecommendationPage
│   │
│   └── utils
│       ├── api.js
│       └── helper functions
```


## Future Improvements

Potential improvements include:

- improving recommendation algorithms  
- adding pagination and filtering for search results  
- improving frontend performance and UI responsiveness  
- extending user interaction signals for recommendation generation
