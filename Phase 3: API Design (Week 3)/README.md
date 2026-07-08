# 📅 Phase 3: API Design (Week 3)

Learn how to design clean, scalable, and maintainable REST APIs using industry best practices.

---

# 📚 Learn

- REST API Best Practices
- HTTP Methods
- Pagination
- Filtering
- Sorting
- Searching
- API Versioning

---

# 🌐 REST API Best Practices

REST (Representational State Transfer) is a standard architectural style used to build web APIs. A REST API allows clients (web browsers, mobile apps, etc.) to communicate with a server using HTTP requests.

A good REST API should:

- Use meaningful resource names
- Use proper HTTP methods
- Return JSON responses
- Return appropriate HTTP status codes
- Be stateless
- Support pagination, filtering, sorting, and searching
- Be versioned for future updates

---

# 📌 HTTP Methods

## GET

Retrieves data from the server.

```http
GET /products
```

Example Response

```json
[
  {
    "id": 1,
    "name": "Laptop",
    "price": 65000
  },
  {
    "id": 2,
    "name": "Mouse",
    "price": 800
  }
]
```

---

## POST

Creates a new resource.

```http
POST /products
```

Request Body

```json
{
  "name": "Keyboard",
  "price": 1200
}
```

Response

```json
{
  "id": 3,
  "name": "Keyboard",
  "price": 1200
}
```

---

## PUT

Updates an existing resource.

```http
PUT /products/5
```

Request Body

```json
{
  "name": "Gaming Keyboard",
  "price": 2500
}
```

---

## DELETE

Deletes an existing resource.

```http
DELETE /products/5
```

Response

```http
204 No Content
```

---

# 📄 Pagination

Pagination divides large datasets into smaller pages to improve performance.

Example

```http
GET /products?page=1&limit=10
```

Explanation

- `page=1` → First page
- `limit=10` → Return only 10 records

Example Response

```json
{
  "count": 100,
  "next": "/products?page=2&limit=10",
  "previous": null,
  "results": [
    ...
  ]
}
```

Benefits

- Faster API responses
- Lower bandwidth usage
- Better user experience

---

# 🔍 Filtering

Filtering returns only the records that match a condition.

Example

```http
GET /products?category=laptop
```

More Examples

```http
GET /products?brand=Apple
```

```http
GET /products?price_lt=50000
```

Benefits

- Returns only required data
- Reduces unnecessary network traffic

---

# 📊 Sorting

Sorting arranges records in ascending or descending order.

Sort by Price

```http
GET /products?sort=price
```

Sort by Name

```http
GET /products?sort=name
```

Descending Order

```http
GET /products?sort=-price
```

> A minus (`-`) indicates descending order.

---

# 🔎 Searching

Searching allows users to find resources using keywords.

Example

```http
GET /products?q=iphone
```

Example Response

```json
[
  {
    "id": 5,
    "name": "iPhone 16",
    "price": 85000
  }
]
```

---

# 🔄 API Versioning

API versioning allows developers to introduce new features without breaking existing applications.

Version 1

```http
/api/v1/
```

Version 2

```http
/api/v2/
```

Example Endpoints

```http
GET /api/v1/products
```

```http
GET /api/v2/products
```

Benefits

- Backward compatibility
- Easier maintenance
- Safe feature upgrades

---

# 📝 REST API Summary

| HTTP Method | Endpoint | Description |
|--------------|----------|-------------|
| GET | `/products` | Retrieve all products |
| POST | `/products` | Create a new product |
| PUT | `/products/5` | Update product with ID 5 |
| DELETE | `/products/5` | Delete product with ID 5 |

---

# 🎯 Key Takeaways

By the end of this phase, you should understand:

- ✅ REST API Design Principles
- ✅ HTTP Methods (GET, POST, PUT, DELETE)
- ✅ Pagination
- ✅ Filtering
- ✅ Sorting
- ✅ Searching
- ✅ API Versioning
- ✅ Building clean and scalable REST APIs using Django REST Framework
