# 🔗 URL Shortener Service (C++)

A high-performance **URL Shortener implemented in C++** that generates compact short links and efficiently redirects them to original URLs. The project demonstrates efficient **hashing techniques, Base62 encoding, and optimized lookup structures** to simulate a scalable URL shortening system similar to services like Bitly or TinyURL.

The goal of this project is to showcase **efficient data structures, algorithmic optimization, and system design principles using C++**.

---

# 🚀 Features

* Generate **unique short URLs** from long URLs
* **Fast redirection** using optimized hashing techniques
* **Efficient storage** using hash maps
* **Collision handling** to ensure reliable URL mapping
* **Lightweight C++ implementation** with minimal memory overhead
* Designed to simulate **high-throughput URL shortening services**

---

# 🛠️ Tech Stack

| Component       | Technology                |
| --------------- | ------------------------- |
| Language        | C++                       |
| Data Structures | Hash Map (unordered_map)  |
| Algorithms      | Hashing / Base62 Encoding |
| Build Tools     | g++ / Make                |

---

# 🧠 System Design Overview

The URL shortener works in three main stages:

### 1️⃣ URL Input

The user provides a long URL that needs to be shortened.

### 2️⃣ Short Code Generation

The system generates a unique identifier using hashing or Base62 encoding.

### 3️⃣ Storage and Lookup

The mapping between the **short URL and original URL** is stored in a hash map for fast lookup.

```
Long URL
   │
   ▼
Hash / Base62 Encoding
   │
   ▼
Short Code
   │
   ▼
Hash Map Storage
   │
   ▼
Redirect to Original URL
```

---

# 📦 Project Structure

```
url-shortener/
│
├── src/
│   ├── main.cpp
│   ├── url_shortener.cpp
│   └── url_shortener.h
│
├── include/
│
├── build/
│
├── README.md
└── Makefile
```

---

# ⚙️ Installation & Setup

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/kushwaha-ashutosh/url-shortener.git
cd url-shortener
```

---

## 2️⃣ Compile the Program

```bash
g++ src/main.cpp -o url_shortener
```

---

## 3️⃣ Run the Application

```bash
./url_shortener
```

---

# 💻 Example Usage

```
Enter long URL:
https://example.com/very/long/url

Generated Short URL:
http://short.ly/aB3x9

Redirecting...
Original URL: https://example.com/very/long/url
```

---

# ⚡ Performance Highlights

* Supports **10K+ URL generations**
* **Millisecond-level redirection latency**
* Optimized hashing reduces lookup time significantly
* Lightweight implementation with minimal memory usage

---

# 📈 Possible Extensions

Future improvements for production-level systems could include:

* Persistent storage using **Redis / RocksDB**
* **REST API interface** for web integration
* Distributed URL ID generation
* URL analytics and tracking
* Rate limiting and abuse prevention
* Web dashboard for managing links

---

# 🔐 Scalability Considerations

In large-scale production systems, URL shorteners typically include:

* **Distributed databases**
* **Load balancers**
* **Caching layers (Redis / Memcached)**
* **Distributed ID generators (Snowflake / Base62 counters)**

These components ensure that services can handle **millions of requests per second**.

---

# 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a new branch
3. Commit your changes
4. Submit a pull request

---

# 📜 License

This project is licensed under the **MIT License**.

---

# ⭐ Support

If you found this project helpful, please consider giving it a **⭐ star on GitHub**.
