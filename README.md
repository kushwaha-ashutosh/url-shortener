# 🔗 URL Shortener Service

A lightweight URL shortening service built with **Java Spring Boot** and **MySQL** that converts long URLs into compact, shareable links — and redirects users back to the original destination instantly.

---

## ✨ Features

- 🔗 **Short URL generation** — convert any long URL into a compact code
- ↩️ **Seamless redirection** — users are forwarded to the original URL automatically
- ⚡ **Efficient URL lookup** — fast database queries for low-latency redirects
- 🗄️ **Persistent storage** — all URL mappings stored reliably in MySQL
- 🌐 **RESTful API** — clean, standard endpoints for easy integration

---

## 🏗️ System Architecture

```
Client
   │
   │  POST /shorten  ──────────────────────────────────┐
   │                                                    ▼
   │                                         Short URL Generator
   │                                                    │
   │                                                    ▼
   │                                               Database
   │                                             (MySQL)
   │
   │  GET /{shortCode}  ────────────────────────────────┐
   │                                                    ▼
   │                                          URL Shortener API
   │                                                    │
   │                                                    ▼
   └──────────────────────────────────── Redirect to Original URL
```

---

## ⚙️ Tech Stack

| Layer       | Technology         |
|-------------|--------------------|
| Backend     | Java / Spring Boot |
| Database    | MySQL              |
| API         | REST               |
| Build Tool  | Maven              |

---

## 🔗 API Reference

### Create a Short URL

```http
POST /shorten
Content-Type: application/json
```

**Request Body**
```json
{
  "url": "https://example.com/some/very/long/path"
}
```

**Response**
```json
{
  "shortUrl": "abc123"
}
```

---

### Redirect to Original URL

```http
GET /{shortCode}
```

| Parameter   | Type     | Description                          |
|-------------|----------|--------------------------------------|
| `shortCode` | `string` | The short code generated at creation |

**Response:** `302 Found` — redirects to the original URL.

---

## 📦 Getting Started

### Prerequisites

- Java 11+
- Maven 3.6+
- MySQL 8+

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/kushwaha-ashutosh/url-shortener.git
   ```

2. **Navigate to the project directory**
   ```bash
   cd url-shortener
   ```

3. **Configure the database**

   Update `src/main/resources/application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/urlshortener
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   ```

4. **Build & run the application**
   ```bash
   mvn spring-boot:run
   ```

5. **Test it out**
   ```bash
   curl -X POST http://localhost:8080/shorten \
     -H "Content-Type: application/json" \
     -d '{"url": "https://example.com"}'
   ```

---

## 💡 Key Concepts Demonstrated

- **URL encoding & hashing** — generating unique, collision-resistant short codes
- **REST API design** — clean endpoint structure with proper HTTP semantics
- **Database mapping** — persisting and querying short-to-long URL relationships
- **Redirect mechanics** — HTTP 302 redirection for transparent forwarding
- **Scalable link resolution** — architecture ready for high-throughput lookups

---

## 📁 Project Structure

```
url-shortener/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/urlshortener/
│   │   │       ├── config/          # App configuration
│   │   │       ├── controller/      # REST controllers
│   │   │       ├── model/           # URL entity model
│   │   │       ├── repository/      # Database access layer
│   │   │       └── service/         # URL generation logic
│   │   └── resources/
│   │       └── application.properties
│   └── test/
├── pom.xml
└── README.md
```

---

## 📈 Roadmap

- [ ] URL analytics & click tracking
- [ ] Redis caching for high-traffic short codes
- [ ] Rate limiting per IP / API key
- [ ] Custom user-defined short URLs
- [ ] Link expiration / TTL support
- [ ] Microservices architecture
- [ ] Dashboard UI for managing links

---

## 🤝 Contributing

Contributions are welcome! Here's how:

1. Fork the repository
2. Create your branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

Feel free to open an issue for bug reports or feature suggestions.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<p align="center">
  Made with ❤️ by <a href="https://github.com/kushwaha-ashutosh">Ashutosh Kushwaha</a>
</p>
