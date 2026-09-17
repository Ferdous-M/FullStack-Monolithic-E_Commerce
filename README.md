# Full-Stack E-Commerce Project

This is a complete full-stack e-commerce application built with Spring Boot for the backend and React + Vite for the frontend.

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
│   │       │   ├── MediaApplication.java      
│   │       │   ├── controllers/SocialController.java  
│   │       │   ├── models/                  
│   │       │   ├── repositories/            
│   │       │   └── services/SocialService.java   
│   │       └── resources/application.properties  
│   └── pom.xml                                  
│
├── ecom-frontend/                  
│   ├── src/
│   │   ├── components/        
│   │   ├── hooks/              
│   │   ├── store/             
│   │   ├── api/api.js          
│   │   ├── App.jsx             
│   │   ├── index.css           
│   │   └── main.jsx           
│   ├── package.json             
│   ├── vite.config.js           
│   └── index.html               
│
└── README.md                    
```




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


