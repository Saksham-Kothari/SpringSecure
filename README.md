```markdown
# SpringSecure

SpringSecure is a **Spring Boot application** that demonstrates how to **secure APIs using Spring Security**.  
The project focuses on **authentication, authorization, and protecting endpoints** using modern Spring Security configuration.

---

## 🔐 What This Project Does

- Secures API endpoints using **Spring Security**
- Allows **public and protected routes**
- Uses **Basic Authentication**
- Demonstrates **role-based access control**
- Encodes passwords securely using **BCrypt**
- Shows how **SecurityFilterChain** works in Spring Boot 3+

---

## 🛠 Tech Stack

- Java 17+
- Spring Boot
- Spring Security
- Maven

---

## 📁 Project Structure

```

SpringSecure
├── config        → Security configuration
├── controller    → API endpoints
├── service       → Business logic / user handling
├── model         → Entity classes
├── resources
│   └── application.properties
└── pom.xml

````

---

## ▶ How to Run the Project

1. **Clone the repository**
   ```bash
   git clone https://github.com/Saksham-Kothari/SpringSecure.git
   cd SpringSecure
````

2. **Run the application**

   ```bash
   mvn spring-boot:run
   ```

3. Open browser or Postman:

   ```
   http://localhost:8080
   ```

---

## 🔑 Security Configuration (Simple Explanation)

Spring Security uses a **filter chain** to intercept requests.

* Public URLs are allowed without login
* Protected URLs require authentication
* Authentication is done using **HTTP Basic**
* Passwords are encrypted using **BCrypt**

### Example Security Config

```java
@Bean
public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {
    http
        .csrf().disable()
        .authorizeHttpRequests(auth -> auth
            .requestMatchers("/public/**").permitAll()
            .anyRequest().authenticated()
        )
        .httpBasic();

    return http.build();
}
```

---

## 👤 Default Login (for testing)

```properties
spring.security.user.name=admin
spring.security.user.password=admin123
spring.security.user.roles=ADMIN
```

---

## 📌 API Examples

### Public Endpoint (No Login Required)

```
GET /public/hello
```

### Protected Endpoint (Login Required)

```
GET /api/user
```

Authorization Header:

```
Basic base64(username:password)
```

---

## 🧠 Key Concepts Covered

* Authentication vs Authorization
* Security Filter Chain
* Role-based access
* Password encoding
* Securing REST APIs

---

## 🎯 Why This Project is Good for Interviews

* Uses **latest Spring Security (no deprecated WebSecurityConfigurerAdapter)**
* Clean and simple security setup
* Shows understanding of **real-world API security**
* Easy to extend with **JWT or OAuth2**

---

## 🚀 Future Improvements

* JWT Authentication
* Database-based users
* Role & permission management
* OAuth2 login

---

## 📄 License

MIT License

---

## 👨‍💻 Author

**Saksham Kothari**

---

```
