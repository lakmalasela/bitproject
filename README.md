# Ceylon Engineering - BIT Final Year Project

A comprehensive engineering management system developed as a final year project for the Bachelor of Information Technology degree. This system streamlines critical operations for engineering projects including land planning, cost estimation, reservation management, and resource allocation.

##  Project Features

### Core Functions
- **Land Planning**: Plan and manage land allocation for engineering projects
- **Cost Estimation**: Calculate detailed project estimations with accurate cost breakdowns
- **Reservation Management**: Customer-compatible reservation system with progress tracking
- **Resource Allocation**: Manage equipment and employee deployment to project locations
- **User Management**: Role-based access control with different privilege levels
- **Reporting**: Comprehensive reporting system for project insights

### User Roles
- **Administrator**: Full system access and configuration
- **Quality Supervisor**: Oversee project quality and standards
- **Engineering Staff**: Manage day-to-day operations

## 🛠 Technology Stack

### Backend
- **Framework**: Spring Boot 2.5.0
- **Language**: Java 11
- **Database**: MySQL 8
- **ORM**: Spring Data JPA with Hibernate
- **Security**: Spring Security
- **Build Tool**: Gradle

### Frontend
- **Technology**: Vanilla JavaScript
- **Styling**: HTML5, CSS3
- **UI Components**: Custom-built components

### Additional Services
- **Email Service**: Gmail SMTP integration
- **SMS Service**: Twilio API integration
- **WebSocket**: Real-time communication

##  Prerequisites

Before setting up the project, ensure you have the following installed:

1. **Java Development Kit (JDK) 11** or higher
2. **MySQL Server 8.0** or higher
3. **Gradle 6.8+** (or use the included Gradle wrapper)
4. **Modern Web Browser** (Chrome, Firefox, Safari, Edge)

##  Setup Instructions

### 1. Database Setup

1. Install and start MySQL Server
2. Create the database:
   ```sql
   CREATE DATABASE ceylon_engineering;
   ```
3. Import the database schema:
   ```bash
   mysql -u root -p ceylon_engineering < DB/ceylon_engineeringM17.sql
   ```

### 2. Backend Configuration

1. Navigate to the backend directory:
   ```bash
   cd bitproject
   ```

2. Configure database connection in `src/main/resources/application.properties`:
   ```properties
   spring.datasource.url = jdbc:mysql://localhost:3306/ceylon_engineering?useSSL=true
   spring.datasource.username = root
   spring.datasource.password = your_mysql_password
   ```

3. Configure email settings (optional):
   ```properties
   spring.mail.username= your_email@gmail.com
   spring.mail.password= your_app_password
   ```

### 3. Running the Application

#### Option 1: Using Gradle Wrapper (Recommended)
```bash
# Build the project
./gradlew build

# Run the application
./gradlew bootRun
```

#### Option 2: Using Gradle
```bash
# Build the project
gradle build

# Run the application
gradle bootRun
```

#### Option 3: Running JAR directly
```bash
# Build the JAR file
./gradlew build

# Run the JAR
java -jar build/libs/bitproject-0.0.1-SNAPSHOT.jar
```

### 4. Accessing the Application

1. **Backend API**: `http://localhost:8080`
2. **Frontend**: The frontend is served from the same URL as it's integrated with Spring Boot
3. **API Documentation**: Access endpoints at `http://localhost:8080/api`

##  Default Login Credentials

### Administrator
- **Username**: Admin
- **Password**: 12345

### Quality Supervisor
- **Username**: Aravinda
- **Password**: arav3

### Supervisor
- **Username**: Nishantha
- **Password**: su123

## 📁 Project Structure

```
bitproject/
├── bitproject/                 # Backend Spring Boot Application
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/bitproject/
│   │   │   │   ├── controller/   # REST API Controllers
│   │   │   │   ├── model/        # Entity Models
│   │   │   │   ├── repository/   # JPA Repositories
│   │   │   │   ├── service/      # Business Logic
│   │   │   │   └── configuration/ # Security & Config
│   │   │   └── resources/
│   │   │       ├── static/       # Frontend Files
│   │   │       └── application.properties
│   │   └── test/                # Unit Tests
│   └── build.gradle             # Gradle Configuration
├── DB/                          # Database Schema
│   └── ceylon_engineeringM17.sql
├── ER/                          # Entity Relationship Diagrams
└── README.md                    # This file
```

## 🔧 Configuration Details

### Database Configuration
- **Database Name**: ceylon_engineering
- **Default Port**: 3306
- **Hibernate Dialect**: MySQL8Dialect
- **DDL Strategy**: Manual (SQL schema provided)

### Security Configuration
- **Session Management**: Spring Session
- **Authentication**: Form-based login
- **Authorization**: Role-based access control

### Email Configuration
- **SMTP Server**: smtp.gmail.com
- **Port**: 587 (TLS)
- **Authentication**: Required

## 🐛 Troubleshooting

### Common Issues

1. **Database Connection Error**
   - Ensure MySQL server is running
   - Verify database credentials in `application.properties`
   - Check if the database exists

2. **Port Already in Use**
   - Change the server port in `application.properties`:
     ```properties
     server.port=8081
     ```

3. **Build Failures**
   - Clear Gradle cache: `./gradlew clean`
   - Check Java version compatibility (requires Java 11+)

4. **Email Service Not Working**
   - Enable "Less secure app access" in Gmail settings
   - Use an App Password instead of regular password
   - Check SMTP configuration

##  Support

For any issues or questions regarding the project setup, please refer to the project documentation or contact the development team.

##  License

This project is developed as part of the BIT Final Year Project submission.

---

**Note**: This is an academic project. For production deployment, ensure proper security configurations and environment-specific settings.

