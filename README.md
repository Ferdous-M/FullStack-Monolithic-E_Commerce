# Full-Stack E-Commerce Project

A complete full-stack e-commerce application built with Spring Boot for the backend and React + Vite for the frontend.

## 📖 Project Overview

This project implements a full-featured e-commerce platform with:
- User authentication and authorization
- Product catalog management
- Shopping cart functionality
- Admin dashboard for managing products, categories, and sellers
- Payment integration (Stripe + PayPal)
- Order management system

## 🏗️ Technology Stack

### Backend
- **Framework**: Spring Boot 3.2.x
- **Language**: Java 24
- **Database**: H2 in-memory database (development), expandable to PostgreSQL/MySQL
- **ORM**: Spring Data JPA with Lombok
- **Security**: Spring Security with JWT/Cookie-based auth
- **Build Tool**: Maven
- **Key Dependencies**:
  - Spring Boot Starter Data JPA
  - Spring Boot Starter WebMvc
  - Spring Boot Starter Test
  - Lombok
  - H2 Database

### Frontend
- **Framework**: React 19
- **Build Tool**: Vite 7
- **Styling**: Tailwind CSS 4, MUI (Material-UI) 7, Emotion
- **State Management**: Redux Toolkit 9
- **Routing**: React Router DOM 7
- **HTTP**: Axios 1.13
- **Notifications**: React Hot Toast 2
- **Carousel**: Swiper 12
- **Icons**: React Icons 5

## 📂 Directory Structure

```
spring-boot-course/
├── media/                          # Spring Boot Backend
│   ├── src/
│   │   └── main/
│   │       ├── java/com/social/media/
│   │       │   ├── MediaApplication.java      # Main Spring Boot app
│   │       │   ├── controllers/SocialController.java   # REST API endpoints
│   │       │   ├── models/                  # JPA entities (SocialUser, SocialGroup, SocialProfile, Post)
│   │       │   ├── repositories/            # Spring Data JPA repositories
│   │       │   └── services/SocialService.java   # Business logic
│   │       └── resources/application.properties  # H2 config, SQL logging
│   └── pom.xml                                  # Maven dependencies
│
├── ecom-frontend/                  # React + Vite Frontend
│   ├── src/
│   │   ├── components/          # Reusable UI components
│   │   ├── hooks/              # Custom React hooks
│   │   ├── store/              # Redux store + reducers
│   │   ├── api/api.js          # Axios instance with backend URL
│   │   ├── App.jsx             # Main app with routing
│   │   ├── index.css           # Global styles
│   │   └── main.jsx            # Entry point
│   ├── package.json             # npm dependencies
│   ├── vite.config.js           # Vite config with React plugin
│   └── index.html               # HTML template
│
└── README.md                    # This file - Project overview and setup
```

## 🚀 Getting Started

### Prerequisites
- **Java 24** (JDK) installed
- **Maven** 3.8+ for backend
- **Node.js 20+** and **npm** for frontend
- Modern browser (Chrome, Firefox, Edge, Safari)

### Backend Setup

1. Navigate to the media module:
   ```bash
   cd media
   ```

2. Build and run with Maven:
   ```bash
   # Using Maven wrapper
   ./mvnw spring-boot:run
   
   # Or with Maven directly
   mvn spring-boot:run
   ```

3. The application will start at `http://localhost:8080`
   - H2 Console: `http://localhost:8080/h2-console`
   - JDBC URL: `jdbc:h2:mem:test`
   - Username: `sa`, Password: (blank)

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd ecom-frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

4. The app will be available at `http://localhost:5173` (Vite default)

### Environment Variables

Create a `.env` file in `ecom-frontend/` if needed:

```
VITE_BACK_END_URL=http://localhost:8080/api
```

The frontend Axios instance (`src/api/api.js`) automatically reads `VITE_BACK_END_URL` from environment variables.

## 🔧 Available Scripts

### Backend (media/)
| Script | Description |
| --- | --- |
| `./mvnw spring-boot:run` | Run Spring Boot application |
| `mvn test` | Run all tests |
| `mvn clean package` | Build JAR package |

### Frontend (ecom-frontend/)
| Script | Description |
| --- | --- |
| `npm run dev` | Start Vite dev server with HMR |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build locally |
| `npm run lint` | Run ESLint |

## 🌐 API Endpoints (Backend)

### User Management
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/social/users` | Get all users |
| `POST` | `/api/social/users` | Create a new user |
| `DELETE` | `/api/social/users/{userId}` | Delete a user by ID |

### Authentication
- Login/Register routes are handled via React Router in the frontend
- Cookies are used for session management (`withCredentials: true`)

## 🗄️ Database Schema

The application uses H2 in-memory database with the following entities:

- **SocialUser**: Core user entity with posts, groups, and social profile
- **SocialGroup**: User groups for categorization/authorization
- **SocialProfile**: Extended user profile with description
- **Post**: User posts/blog entries

Relationships:
- User ↔️ Group: Many-to-Many (join table `user_group`)
- User ↔️ Profile: One-to-One
- User ↔️ Posts: One-to-Many (user has many posts)

## 📦 Project Configuration

### Backend (`media/pom.xml`)
- Spring Boot 4.0.1 parent
- Spring Boot Starter Data JPA
- Spring Boot Starter WebMvc
- H2 database (runtime scope)
- Lombok (optional)
- Spring Boot Starter Test (test scope)

### Frontend (`ecom-frontend/package.json`)
- React 19 with React DOM 19
- Vite 7 with React plugin
- Tailwind CSS 4 with MUI v7
- Redux Toolkit 9 with React Redux 9
- Axios 1.13 for API calls
- React Router DOM 7 for routing
- Various UI libraries (Emotion, Headless UI, Stripe, PayPal, Swiper)

## 🛠️ Development Notes

- The backend uses `@RestController` for REST APIs with `@GetMapping`, `@PostMapping`, `@DeleteMapping`
- JPA entities use Lombok `@Data`, `@NoArgsConstructor`, `@AllArgsConstructor`
- H2 console is enabled (`spring.h2.console.enabled=true`) for development
- SQL logging is enabled (`spring.jpa.show-sql=true`) for debugging
- Frontend uses cookies with `withCredentials: true` for authenticated requests
- Admin routes are protected via `PrivateRoute` component with `adminOnly` permission

## 📝 License

This project is for educational purposes as part of a Spring Boot course.

---

**Need help?** Check the individual module README files or open an issue.