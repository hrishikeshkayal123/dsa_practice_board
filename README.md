# 🧠 DSA Practice Board (Kotlin Execution Platform)

A lightweight **LeetCode-style coding platform** built for practicing Data Structures & Algorithms with **real-time Kotlin execution**.

---

## 🚀 Features

* 🧩 15 curated **Interval-based DSA problems**
* 📝 Interactive **Monaco Editor (VS Code-like)**
* ▶️ **Run code** with real backend execution
* 🧪 Expandable **solutions for learning**
* 🧠 Smart **Kotlin code normalization**
* 🔍 **Brace validation & syntax checks**
* 🌐 Full-stack setup (Frontend + Backend)

---

## 🏗️ Tech Stack

### 🔹 Frontend

* HTML5 + CSS3
* Vanilla JavaScript
* Monaco Editor (VS Code engine)

### 🔹 Backend

* Node.js (Express)
* HTTPS server (self-signed SSL)
* CORS-enabled API layer

### 🔹 Code Execution

* JDoodle API (Kotlin runtime)
* JVM-compatible code transformation layer

---

## 📁 Project Structure

```
project-root/
│
├── server.js                # Node backend (API + HTTPS server)
├── key.pem / cert.pem       # SSL certificates
├── public/
│   └── index.html           # Main UI
│
└── README.md
```

---

## ⚙️ Setup Instructions

### 1️⃣ Install Dependencies

```bash
npm init -y
npm install express cors node-fetch
```

---

### 2️⃣ Generate SSL Certificate

Using OpenSSL or mkcert:

```bash
openssl req -nodes -new -x509 -keyout key.pem -out cert.pem -days 365
```

---

### 3️⃣ Run Server

```bash
node server.js
```

---

### 4️⃣ Open Application

```text
https://localhost:3000
```

⚠️ Accept the self-signed certificate warning in browser.

---

## 🔄 Data Flow (End-to-End)

### 🧭 Execution Flow

```
User (Browser UI)
    ↓
Monaco Editor (User writes Kotlin code)
    ↓
runCode() → POST /run
    ↓
Node.js Backend (Express)
    ↓
Code Normalization Layer
    ↓
JDoodle API (Kotlin execution)
    ↓
Execution Result
    ↓
Frontend Output Console
```

---

## 🧠 Kotlin Execution Handling (Key Insight)

JDoodle expects a **Java-style entry point**, but Kotlin compiles differently.

### ❗ Problem

```kotlin
fun main() {
    println("Hello")
}
```

Generates:

```
MainKt.class
```

But JDoodle runs:

```
java JDoodle
```

---

### ✅ Solution (Implemented)

User code is transformed into:

```kotlin
class JDoodle {
    companion object {
        @JvmStatic
        fun main(args: Array<String>) {
            // user code here
        }
    }
}
```

This ensures:

* JVM-compatible execution
* Successful runtime invocation

---

## 🧪 Example Execution

### Input

```kotlin
fun main() {
    println("Hello Kotlin")
}
```

### Output

```
Hello Kotlin
```

---

## ⚠️ Known Limitations

* JDoodle dependency (external API)
* No stdin-based test case system (yet)
* Basic syntax validation (not full compiler-level)
* Kotlin-only support

---

## 🔮 Future Improvements

* ✅ Test case runner (stdin support)
* ✅ Multiple language support (Java, Python)
* ✅ Code templates per problem
* ✅ Execution time & memory stats
* ✅ Docker-based local execution engine (replace JDoodle)
* ✅ User progress tracking

---

## 🧠 Learning Focus

This project demonstrates:

* Full-stack integration
* Code editor embedding (Monaco)
* API design & execution pipelines
* Runtime adaptation (Kotlin → JVM)
* Debugging real-world issues (CORS, SSL, execution mismatch)

---

## 👨‍💻 Author

Built as a **hands-on DSA + System Design practice tool**

---

## 📌 License

MIT License
