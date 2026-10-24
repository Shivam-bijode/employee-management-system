# Employee Management System

Full-stack web application to manage employee records, with secure login and role-based access for Admin and Employee users.

🔗 **Live demo:** https://employee-management-system-wheat-eta.vercel.app

👤 **Demo login (Admin):** Username `demo` | Password `[demo-password]`

> ⏳ The backend runs on a free hosting plan. If the app has been idle, the first request can take up to 2-3 minutes while the server wakes up. Please wait and retry.

## Features
- Register and log in with JWT-based authentication
- Role-based access control: **ADMIN** can add, edit and delete employees, **EMPLOYEE** can view
- Employee management (create, read, update, delete) through a REST API
- Passwords stored as BCrypt hashes
- CORS-configured backend connected to a separately hosted frontend
- Dockerized backend, deployed on the cloud

## Tech Stack
| Layer | Technology |
|---|---|
| Backend | Java, Spring Boot, Spring Security, Spring Data JPA, JWT, Maven |
| Database | MySQL (Aiven) |
| Frontend | [React / HTML-CSS-JS] |
| Deployment | Render (Docker), Vercel |

## Architecture
```
Frontend (Vercel)  →  REST API (Spring Boot on Render)  →  MySQL (Aiven)
                          JWT authentication
```

## Run locally

### Prerequisites
- Java 17+ (or the version in your `pom.xml`)
- MySQL running locally
- Node.js (for the frontend)

### Backend
```bash
git clone https://github.com/Shivam-bijode/Employee-management-System.git
cd Employee-management-System
```

Set these environment variables:
```
DB_URL=jdbc:mysql://localhost:3306/employee_management
DB_USERNAME=your_mysql_user
DB_PASSWORD=your_mysql_password
```

Then start the app:
```bash
./mvnw spring-boot:run
```
The API runs on `http://localhost:8081` by default (or the port in the `PORT` variable).

### Frontend
```bash
cd [frontend-folder-name]
npm install
npm run dev
```

### Docker
```bash
docker build -t employee-management .
docker run -p 8081:8081 \
  -e DB_URL=... -e DB_USERNAME=... -e DB_PASSWORD=... \
  employee-management
```

## User roles
| Role | Permissions |
|---|---|
| ADMIN | View, add, edit and delete employees |
| EMPLOYEE | View employees |

## Screenshots
![Login](screenshots/login.png)
![Dashboard](screenshots/dashboard.png)

## Author
**Shivam Bijode**
GitHub: [Shivam-bijode](https://github.com/Shivam-bijode)
LinkedIn: [your-linkedin-link]
