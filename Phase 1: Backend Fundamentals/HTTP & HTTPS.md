# 🌐 HTTP & HTTPS Complete Guide

> Complete beginner-to-advanced notes on HTTP and HTTPS with Python, Flask, Django, interview questions, and examples.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![HTTP](https://img.shields.io/badge/Protocol-HTTP-green)
![Backend](https://img.shields.io/badge/Backend-Fundamentals-orange)

---

# 📚 Table of Contents

- Introduction
- What is HTTP?
- HTTP Communication Flow
- HTTP Request
- HTTP Response
- Client & Server
- HTTP Methods
- Status Codes
- Headers
- Body
- URL Structure
- HTTPS
- SSL/TLS
- HTTP vs HTTPS
- Python HTTP Server
- Django Example
- Interview Questions
- Quick Revision

---

# 🎯 Learning Objectives

After completing these notes, you will understand:

- ✔ What HTTP is
- ✔ How client-server communication works
- ✔ HTTP Requests & Responses
- ✔ All HTTP Methods
- ✔ HTTP Status Codes
- ✔ HTTP Headers
- ✔ URL Structure
- ✔ HTTPS
- ✔ SSL/TLS Certificates
- ✔ Flask Examples
- ✔ Django Examples
- ✔ Backend Interview Questions

---

# 📖 What is HTTP?

HTTP (**HyperText Transfer Protocol**) is the communication protocol used between a client and a server.

Whenever you:

- Open a website
- Login to an application
- Call an API
- Submit a form

HTTP is being used.

---

# 🔄 HTTP Communication Flow

```text
Browser (Client)
      │
      │ HTTP Request
      ▼
Backend Server
      │
      │ HTTP Response
      ▼
Browser
```

---

# 🍕 Real-Life Example

```text
You
 │
 │ Order Pizza
 ▼
Restaurant
 │
 │ Pizza
 ▼
You
```

Client → Request

Server → Response

---

# 📦 HTTP Request Structure

```http
GET /products HTTP/1.1
Host: example.com
Content-Type: application/json
Authorization: Bearer Token
```

Components

- Request Line
- Headers
- Body (Optional)

---

# 📨 HTTP Response Structure

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
    "name":"Rahul",
    "age":22
}
```

---

# 🖥 Client vs Server

| Client | Server |
|----------|----------|
| Browser | Django |
| React | Flask |
| Mobile App | Node.js |
| Postman | Spring Boot |

---

# 🚀 HTTP Methods

| Method | Purpose |
|----------|----------|
| GET | Read Data |
| POST | Create Data |
| PUT | Replace Data |
| PATCH | Update Data |
| DELETE | Delete Data |

---

# GET Example

Request

```http
GET /users
```

Response

```json
[
    {
        "id":1,
        "name":"Rahul"
    }
]
```

## Flask Example

```python
from flask import Flask, jsonify

app = Flask(__name__)

@app.route("/users", methods=["GET"])
def get_users():
    return jsonify([
        {"id":1,"name":"Rahul"}
    ])

app.run(debug=True)
```

---

# POST Example

```http
POST /users
```

Body

```json
{
    "name":"Rahul"
}
```

```python
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route("/users", methods=["POST"])
def create_user():
    data = request.get_json()
    return jsonify(data)

app.run(debug=True)
```

---

# PUT Example

```http
PUT /users/1
```

```json
{
    "name":"Rahul",
    "age":24
}
```

---

# PATCH Example

```http
PATCH /users/1
```

```json
{
    "age":25
}
```

---

# DELETE Example

```http
DELETE /users/1
```

```json
{
    "message":"Deleted Successfully"
}
```

---

# 📊 HTTP Status Codes

| Code | Meaning |
|------|---------|
|200|OK|
|201|Created|
|204|No Content|
|400|Bad Request|
|401|Unauthorized|
|403|Forbidden|
|404|Not Found|
|405|Method Not Allowed|
|500|Internal Server Error|
|502|Bad Gateway|
|503|Service Unavailable|

---

# 📌 HTTP Headers

```http
Content-Type: application/json
Authorization: Bearer Token
Accept: application/json
Host: localhost
```

| Header | Purpose |
|---------|----------|
|Content-Type|Data Format|
|Authorization|Authentication|
|Accept|Expected Response|
|Host|Server Name|
|Cookie|Session Data|

---

# 📦 HTTP Body

```json
{
    "username":"Rahul",
    "password":"123456"
}
```

---

# 🌍 URL Structure

```
https://example.com/products/10?color=red
```

| Part | Meaning |
|------|----------|
|https|Protocol|
|example.com|Domain|
|products|Path|
|10|Resource ID|
|color=red|Query Parameter|

---

# 🔒 What is HTTPS?

HTTPS = HTTP + SSL/TLS Encryption

```
HTTP

No Encryption

❌ Unsafe
```

```
HTTPS

Encrypted

✅ Secure
```

---

# 🔐 SSL/TLS

```
Browser

↓

SSL Handshake

↓

Encrypted Connection

↓

Secure Communication
```

---

# ⚖ HTTP vs HTTPS

| HTTP | HTTPS |
|-------|--------|
|Port 80|Port 443|
|Not Secure|Secure|
|No Encryption|Encrypted|
|No SSL|SSL Required|

---

# 🐍 Python HTTP Server

```python
from http.server import HTTPServer, BaseHTTPRequestHandler

class MyServer(BaseHTTPRequestHandler):

    def do_GET(self):
        self.send_response(200)
        self.send_header("Content-type","text/plain")
        self.end_headers()
        self.wfile.write(b"Hello HTTP")

server = HTTPServer(("localhost",8000),MyServer)

server.serve_forever()
```

---

# Django Example

## urls.py

```python
urlpatterns = [
    path("hello/",views.hello)
]
```

## views.py

```python
from django.http import JsonResponse

def hello(request):
    return JsonResponse({
        "message":"Hello HTTP!"
    })
```

---

# 💼 Interview Questions

## What is HTTP?

HTTP is an application-layer protocol used for communication between clients and servers.

---

## What is HTTPS?

HTTPS is HTTP secured using SSL/TLS encryption.

---

## Difference between HTTP and HTTPS?

- HTTP → No Encryption
- HTTPS → Encrypted
- HTTP → Port 80
- HTTPS → Port 443

---

## What is GET?

Used to retrieve data.

---

## What is POST?

Used to create new resources.

---

## What are HTTP Status Codes?

Status codes indicate the result of an HTTP request.

Examples:

- 200 OK
- 404 Not Found
- 500 Internal Server Error

---

# ⚡ Quick Revision

- HTTP = Communication Protocol
- HTTPS = Secure HTTP
- Client → Browser
- Server → Django/Flask
- GET → Read
- POST → Create
- PUT → Replace
- PATCH → Update
- DELETE → Remove
- 200 → Success
- 404 → Not Found
- 500 → Server Error
- HTTP → Port 80
- HTTPS → Port 443

---

# 🎉 Congratulations!

You now understand the fundamentals of HTTP and HTTPS required for backend development and technical interviews.

⭐ If this repository helped you, consider giving it a star.
